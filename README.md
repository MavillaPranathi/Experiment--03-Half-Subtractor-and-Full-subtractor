# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure

Connect the supply (+5V) to the circuit Switch ON the main switch If the output is 1,then the led
glows.

## Program:
```
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by:M.PRANATHI
RegisterNumber:22005710
*/
1. For HALF SUBTRACTOR:

module half_sub(a,b,diff,b_out);
input a,b;
wire d;
output diff,b_out;
xor (diff,a,b);
not (d,a);
and (b_out,d,b);
endmodule

2.For FULL SUBTRACTOR:

module full_sub(b_out,diff,a,b,c_in);
output b_out,diff;
input a,b,c_in;
wire w1,w4,w5,w6;
xor (diff,a,b,c_in);
not (w1,a);
and (w4,w1,b);
and (w5,w1,c_in);
and (w6,b,c_in);
or (b_out,w4,w5,w6);
endmodule
```
## Output:

## Truthtable
1. For HALF SUBTRACTOR:

![hs](https://user-images.githubusercontent.com/118343610/229426038-25319527-e079-41c2-a7f4-5425d00dd58c.png)

2.For FULL SUBTRACTOR:

![image](https://user-images.githubusercontent.com/118343610/229427318-c40d1661-6ad8-42d6-980c-acb5fdc67e90.png)


##  RTL realization
1. For HALF SUBTRACTOR:

![image](https://user-images.githubusercontent.com/118343610/229428316-b66a419f-84e9-477f-8de5-62245b2e1f44.png)


2.For FULL SUBTRACTOR:

![image](https://user-images.githubusercontent.com/118343610/229428406-6c0e32e5-5b9d-49cf-b43a-130a715a34c2.png)



## Timing diagram 
1. For HALF SUBTRACTOR:  

![image](https://user-images.githubusercontent.com/118343610/229428487-25ba8c2d-057f-49c9-ab18-cec114065db5.png)


2.For FULL SUBTRACTOR:

![image](https://user-images.githubusercontent.com/118343610/229428562-2b5deaeb-3604-4983-be46-a95f185ec8f5.png)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
