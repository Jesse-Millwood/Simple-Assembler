Simple Assembler
=================

The SimpleAssembler python script can be run from the command line with the switches '-i'(--inFILE) and '-o'(--outFILE) for input file and output file respectively. The input file should have the instructions one after another as they are in the sample Instructions.dat file. This is the file it looks for if no input file is specified. The default output file behavior is to output a dat and coe file. 

The switch -t or --type is used to specify the type of the output file. If 'coe' is used the output file will have a header and radix information common in Xilinx Coefficient files. It will also have comments that correspond to the contents of the input file. The 'dat' type is just the binary contents of the memory addresses, one after the other, no comments. The 'both' specifier for the type switch will output both of these. The 'debug' specifier outputs information to the terminal window.

A sample implementation of this script would be to make the script an executable by performing `chmod +x SimpleAssembler`. Then copying it to a directory on your `$PATH`. Then open up a terminal and cd to the directory containing your `Instructions.dat` file. Perform:  
`SimpleAssembler -i Instructions.dat -o Encoding -t coe`  
This will take the `Instructions.dat` file as an input, convert it to the Xilinx Coefficient file format and save it as Encoding.coe.

The following are the instructions implemented so far

|Instruction | Encoding          |
|------------|:-----------------:|
|Load M,R 	 |000000pr, mmmmmmmm |
|STOR R,M 	 |000001pr, mmmmmmmm |
|ADD R 		 |1000000r           |  
|SUB R 		 |1001000r           | 
|LSL R 		 |1010000r           |  
|LSR R 		 |1011000r           |  
|XOR R 		 |1100000r           | 
|COM R 		 |1101000r           | 
|NEG R 		 |1110000r           |  
|CLR R 		 |1111000r           | 
|OUT R,P 	 |000010ir           | 
|IN P,R 	 |000011ir           | 
|BCDO R      |0100000r           | 
|DEB i,R     |001000ir 			 |


In the input file, memory locations can be initialized by typing the memory address and desired contents of the that memory address separated by a colon.  
The following example would initialize memory location 230 to the value 10:  
`230:10`

Blocks of code can also be specified to start at certain memory addresses with the 'BEGIN' directive. The following would start the instructions at memory location: 100 and end at 105.  
    BEGIN:100    
    LOAD 200,A  
    LOAD 201,B  
    BCDO A  
    BCDO B

