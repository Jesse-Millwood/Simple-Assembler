Simple Assembler
=================

The SimpleAssembler python script can be run from the command line with the switches '-i' and '-o' for input file and output file respectively. The input file should have the instructions one after another as they are in the sample Instructions.dat file. This is the file it looks for if no input file is specified. The output file is named Encoding.dat. 

The following are the instructions implemented so far

|Instruction | Encoding          |
|------------|------------------:|
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