# FIR-FILTER-DESIGN
# EXP 4e: Design-of-FIR-Digital-Filter-using-Barlett-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Barlett-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = Wc/ %pi ; 
else 
hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2))/(M-1)); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR LPF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR LPF using Bartlett Window');
```
## CALCULATION:
![WhatsApp Image 2026-03-26 at 11 39 29](https://github.com/user-attachments/assets/5976c9dc-e0d6-4ed0-866e-e46f96df3b3d)

<img width="1529" height="398" alt="image" src="https://github.com/user-attachments/assets/99429cc3-257b-4fa9-a72f-0aec17dd4273" />

# OUTPUT: 

<img width="454" height="440" alt="image" src="https://github.com/user-attachments/assets/8014d6d3-1703-4536-a258-e1f5e046571b" />
<img width="767" height="721" alt="image" src="https://github.com/user-attachments/assets/1630750f-a6d7-4d11-80a8-02a72300cd0c" />


# RESULT: 

Thus design of low pass FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = 1-Wc/ %pi ; 
else 
hd(n) = -sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1));  
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR HPF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR HPF using Bartlett Window');
```
# CALCULATION:
<img width="1344" height="1148" alt="image" src="https://github.com/user-attachments/assets/465bd5a8-0b09-4e94-aa25-7fbd9fe3721c" />

# OUTPUT: 
<img width="471" height="474" alt="image" src="https://github.com/user-attachments/assets/8da6cfdb-99a6-4021-9b85-5d8df3b54f29" />

<img width="770" height="723" alt="image" src="https://github.com/user-attachments/assets/5e5b7399-271d-49d5-a7c7-cbfdb89443a8" />

# RESULT: 
Thus design of HIGH pass FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =(Wc2-Wc1)/%pi ; 
else 
hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1)); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Bartlett Window');
```
# CALCULATION:
![WhatsApp Image 2026-03-26 at 11 43 03](https://github.com/user-attachments/assets/3a41c031-9e93-4bfc-a971-ee967fce4c49)

# OUTPUT: 
<img width="528" height="456" alt="image" src="https://github.com/user-attachments/assets/f96e9d18-37ee-4f67-9ad9-a9741e9b995e" />
<img width="757" height="721" alt="image" src="https://github.com/user-attachments/assets/61280890-0152-4960-bcb4-ffa4b1758808" />

# RESULT: 
Thus design of BAND pass FIR digital filter using-Barlettr-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =1-((Wc2-Wc1)/%pi); 
else 
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1));  
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Bartlett Window');
```
# CALCULATION:
![WhatsApp Image 2026-03-26 at 11 43 05](https://github.com/user-attachments/assets/693dbfd2-4d9f-4224-abc2-2eb612b59c45)

# OUTPUT: 
<img width="594" height="509" alt="image" src="https://github.com/user-attachments/assets/83e2f6ed-bb7a-4ca2-b329-36ad274cb906" />
<img width="755" height="716" alt="image" src="https://github.com/user-attachments/assets/8922de5e-ceca-4a99-b519-d172ab773fd4" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.
