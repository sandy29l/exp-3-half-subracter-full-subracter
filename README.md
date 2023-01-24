# exp-3-half-subracter-full-subracter
AIM:

To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

Equipments Required:

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

Theory

Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

Half Subtractor Full Subtractor

Half Subtractor

The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.

![166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a](https://user-images.githubusercontent.com/123359969/214294747-d15d1fc4-b201-47b2-bb82-d41be76e446c.png)

half-subtractor9

Sum = X'Y+XY' = X ⊕ Y Carry=X'Y

Full Subtractor

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![166112541-24c68359-3de8-4674-ae22-8272ffc385ed](https://user-images.githubusercontent.com/123359969/214294841-10cb4622-db5b-486f-ad7e-fa6195d32a87.png)

full-subtractor6

Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin
```
Procedure
Write the detailed procedure here
```
Program:

Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.

Developed by: Santhosh L

RegisterNumber: 22008479

Half Subtractor:
```
module half_sub(x, y, x1, d, b);
input x, y;
output x1, d, b;
xor(d, x, y);
not(x1, x);
and(b, x1, y);
endmodule
```
Full Subtractor:
```
module full_sub(x, y ,z, x1, x2, x3, x4, x5, d, b);
input x, y, z;
output x1, x2, x3, x4, x5, d, b;
xor(x1, x, y);
xor(d, x1, z);
not(x2, x);
and(x3, x2, y);
and(x4, x2, z);
and(x5, y, z);
or(b, x3, x4, x5);
endmodule
```
Output:

Truthtable

Half Subtractor:
![half_sub_truthtable](https://user-images.githubusercontent.com/123359969/214295062-5fd5260c-6917-4d81-b15d-e0e82bbb832f.png)

Full Subtractor:
![full_sub_truthtable](https://user-images.githubusercontent.com/123359969/214295095-13159813-f5a5-4471-b77f-7bed0b3e4c57.jpg)



RTL realization
Half Subtractor:

![half_sub_rtl](https://user-images.githubusercontent.com/123359969/214295140-b1f1a2aa-b797-403d-9ff9-b1c47dca18eb.png)


Full Subtractor:

![full_sub_rtl](https://user-images.githubusercontent.com/123359969/214295171-bf41beda-8a7d-40bd-a36c-ed5b5f982f8b.png)


Timing diagram
Half Subtractor:

![half_sub_timingdiag](https://user-images.githubusercontent.com/123359969/214295198-af25480c-3d5f-47aa-84a9-4acb8aff46ab.png)


Full Subtractor:
![full_sub_timingdiag](https://user-images.githubusercontent.com/123359969/214295216-d46a61a2-4f2b-4052-bcf4-13341214c353.png)



Result:

Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
