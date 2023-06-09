### Ex. No. 3
### Date:8.4.23
# Implementation of half adder and full adder circuit using Verilog HDL
## Aim :
To design and implement half adder and full adder circuit using Verilog HDL and verify its truth table.
## Components Required:
1.	Laptop with Quartus software and modelsim software.
## Theory:
Adders are digital circuits that carry out addition of numbers.
### 1.	Half Adder
Half adder is a combinational circuit that performs simple addition of two binary numbers. The input variables designate the augend and addend bits; the output variables produce the sum and carry. It is necessary to specify two output variables because the result may consist of two binary digits.
#### Truth table
 ![image](https://github.com/rvinifa/Adder/assets/133735746/469bd63c-0a45-4d7a-a68a-b68bb36c637a)

Sum = A’B+AB’ = A  ![image](https://github.com/rvinifa/Adder/assets/133735746/aac88cdf-2255-4bff-971b-a3657a2c19e3)
     B
Carry=AB
#### Logic Diagram
 ![image](https://github.com/rvinifa/Adder/assets/133735746/c65758e5-f597-4204-8ab1-41575bd0c3e3)

### 2.	Full Adder
Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry. 
#### Truth table
  .![image](https://github.com/rvinifa/Adder/assets/133735746/f8301e61-a457-4c1b-97fd-1adcb039df01)

#### K-map Simplification
 ![image](https://github.com/rvinifa/Adder/assets/133735746/03a38bcf-2642-4391-8424-7011b94e6002)

Sum =A’B’Cin+A’BCin’+ABCin+AB’Cin’=A ![image](https://github.com/rvinifa/Adder/assets/133735746/d522a34d-a1e9-4d96-9b19-3cbc259cb7e2)
 B ![image](https://github.com/rvinifa/Adder/assets/133735746/f52fbe53-60e0-4c19-b728-7efb11d08248)
 Cin
Carry = AB + ACin+BCin
#### Logic Diagram
 ![image](https://github.com/rvinifa/Adder/assets/133735746/982f8574-d184-49fa-a66a-4201ea48c58d)

## Procedure:
1.	Type the program in Quartus software.
2.	Compile and run the program.
3.	Generate the RTL schematic and save the logic diagram.
4.	Create nodes for inputs and outputs to generate the timing diagram.
5.	For different input combinations, generate the timing diagram.


## Program:
### Half Adder:
```
module exp3a(A,B,S,C);
input A,B;
output S,C;
xor(S,A,B);
and(C,A,B);
endmodule
```
### Full Adder:
```
module exp3b(A,B,C,S,CA);
input A,B,C;
output S,CA;
wire bc,acout,bcout,about,baout;
xor(bc,B,C);
xor(S,A,bc);
and(acout,A,C);
and(about,A,B);
and(bcout,B,C);
or(baout,bcout,about);
or(CA,acout,baout);
endmodule
```
## RTL Schematic:
### 1. HALF ADDER:
![image](https://github.com/Afsarjumail/Adder/assets/118343395/6aadd7e0-213f-47b7-944e-8d1da9b1c62a)


### 2.FULL ADDER:
![image](https://github.com/Afsarjumail/Adder/assets/118343395/889c1eab-ea9b-46bd-bd1a-9c774733d57f)


## Timing Diagram:
### 1. HALF ADDER:
![image](https://github.com/Afsarjumail/Adder/assets/118343395/f29b242f-74b7-4f8f-9ddf-cc556190188c)

### 2.FULL ADDER:
![image](https://github.com/Afsarjumail/Adder/assets/118343395/f4d0a271-5cc3-4cf7-bb56-d4d6872652fa)

## Result:
Thus the half adder and full adder circuits are designed and implemented and the truth tables are verified.
