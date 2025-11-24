# EVALUATION-OF-RADAR-RANGE-USING-PYTHON-

__Aim__:

To calculate the maximum range of a radar system using the Radar Range Equation and verify the results 
through Python programming.

__Theory__:

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum 
range at which a radar can detect a target. It is given by:

<img width="573" height="442" alt="image" src="https://github.com/user-attachments/assets/ba374d30-d11f-41e5-a4fc-a42dde71d8e7" />

__Procedure__:

1. Set Up the Python Environment: Ensure that Python is installed on your system. You can use 
Anaconda for managing Python packages and environments, or any other Python IDE of your choice. 
2. Import Necessary Libraries: Import the math library in Python. 
3. Define the Radar Range Equation Function: Create a function to calculate the maximum range using 
the Radar Range Equation. 
4. Input Parameters for the Radar System: Define the input parameters such as transmitted power, 
transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power. 
5. Calculate the Maximum Range: Use the function to calculate the maximum range of the radar. 
6. Execute the Program: Run the Python script to calculate and display the maximum range of the radar.


### PROGRAM :
~~~
clc
clear;
close;

Pt = 1000;
G = 40;
lambda = 0.05;
sigma = 10;
pi4 = (4*%pi)^3;

R = linspace(1e3, 200e3, 500);
Pr_R = (Pt .* G^2 .* lambda^2 .* sigma) ./ (pi4 .* R.^4);
figure(1);
Pr_R_dB = 10 .* log10(Pr_R);
plot(R/1000, Pr_R_dB);
xlabel("Power Received");
ylabel("Range");

Pt_values = linspace(100, 10000, 500);
R_fixed = 50e3;
Pr_Pt = (Pt_values .* G^2 .* lambda^2 .* sigma) ./ (pi4 .* R_fixed.^4);
figure(2);
plot(Pt_values, Pr_Pt);
xlabel("Power Received");
ylabel("Power Transmitted");

G_values = linspace(5, 60, 500);
Pt_fixed = 3000;
Pr_G = (Pt_fixed .* G_values.^2 .* lambda^2 .* sigma) ./ (pi4 .* R_fixed.^4);
figure(3);
plot(G_values, Pr_G);
xlabel("Power Received");
ylabel("Gain");
~~~

### TABULATION :
<img width="1280" height="960" alt="image" src="https://github.com/user-attachments/assets/b25cf9a4-afb7-4b1b-852f-c76a6850b7cd" />


  __Output__:
  
<img width="741" height="565" alt="image" src="https://github.com/user-attachments/assets/7756b68a-4bdd-44dd-9574-aa55a03b7549" />
<img width="751" height="567" alt="image" src="https://github.com/user-attachments/assets/254769ff-0146-424c-99cd-205090004e01" />
<img width="763" height="570" alt="image" src="https://github.com/user-attachments/assets/17e7e6b7-4746-4746-9ebe-bc3dc7396d4f" />

   
  __Result__:
  ![WhatsApp Image 2025-11-24 at 20 30 42_b319c58d](https://github.com/user-attachments/assets/acb3c661-49f5-42e4-ae23-e600af7b32bd)

   




