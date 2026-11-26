# FIR-FILTER-DESIGN
# EXP 4 d: Design-of-FIR-Digital-Filter-using-Blackman-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Blackman-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
clc; clear; close;

N = 21;
wc = %pi / 2;
alpha = (N - 1) / 2;

hd = zeros(1, N); for n = 0 : N-1 if n == alpha then hd(n+1) = wc / %pi; else hd(n+1) = sin(wc * (n - alpha)) / (%pi * (n - alpha)); end end

w = zeros(1, N); for n = 0 : N-1 w(n+1) = 0.42 - 0.5 * cos((2 * %pi * n) / (N - 1)) + 0.08 * cos((4 * %pi * n) / (N - 1)); end

h = hd .* w;

[H, w_freq] = frmag(h, 256);

figure; subplot(2, 1, 1); plot2d3(0:N-1, h);
plot(0:N-1, h, 'ro');
xtitle('Impulse Response', 'n', 'h(n)'); xgrid(1);

subplot(2, 1, 2); H_dB = 20 * log10(H);
plot(w_freq, H_dB); xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)'); xgrid(1);

# OUTPUT: 
<img width="1917" height="892" alt="image" src="https://github.com/user-attachments/assets/ca89521b-3e3d-4301-a1a7-fc1c6d435474" />


# RESULT: 

Thus design of low pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc; clear; close;

N = 21;
wc = %pi / 2;
alpha = (N - 1) / 2;

hd = zeros(1, N); for n = 0 : N-1 if n == alpha then hd(n+1) = 1 - (wc / %pi); else hd(n+1) = -sin(wc * (n - alpha)) / (%pi * (n - alpha)); end end

w = zeros(1, N); for n = 0 : N-1 w(n+1) = 0.42 - 0.5 * cos((2 * %pi * n) / (N - 1)) + 0.08 * cos((4 * %pi * n) / (N - 1)); end

h = hd .* w;

[H, w_freq] = frmag(h, 256);

figure; subplot(2, 1, 1); plot2d3(0:N-1, h);
plot(0:N-1, h, 'ro');
xtitle('Impulse Response', 'n', 'h(n)'); xgrid(1);

subplot(2, 1, 2); H_dB = 20 * log10(H);
plot(w_freq, H_dB); xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)'); xgrid(1);
# OUTPUT: 
<img width="1917" height="893" alt="image" src="https://github.com/user-attachments/assets/92c583c5-0b6b-4ab2-b9b4-bd37920f5383" />


# RESULT: 
Thus design of HIGH pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc; clear; close;

N = 21;
wc1 = %pi / 4;
wc2 = 3 * %pi / 4;
alpha = (N - 1) / 2;

hd = zeros(1, N); for n = 0 : N-1 if n == alpha then hd(n+1) = (wc2 - wc1) / %pi; else hd(n+1) = (sin(wc2 * (n - alpha)) - sin(wc1 * (n - alpha))) / (%pi * (n - alpha)); end end

w = zeros(1, N); for n = 0 : N-1 w(n+1) = 0.42 - 0.5 * cos((2 * %pi * n) / (N - 1)) + 0.08 * cos((4 * %pi * n) / (N - 1)); end

h = hd .* w;

[H, w_freq] = frmag(h, 256);

figure; subplot(2, 1, 1); plot2d3(0:N-1, h);
plot(0:N-1, h, 'ro');
xtitle('Impulse Response', 'n', 'h(n)'); xgrid(1);

subplot(2, 1, 2); H_dB = 20 * log10(H);
plot(w_freq, H_dB); xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)'); xgrid(1);
# OUTPUT: 

<img width="1917" height="896" alt="image" src="https://github.com/user-attachments/assets/dd275d43-6197-4426-8021-fc73ed34cd47" />

# RESULT: 
Thus design of BAND pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
clc; clear; close;

N = 21;
wc1 = %pi / 4;
wc2 = 3 * %pi / 4;
alpha = (N - 1) / 2;

hd = zeros(1, N); for n = 0 : N-1 if n == alpha then hd(n+1) = 1 - ((wc2 - wc1) / %pi); else hd(n+1) = (sin(wc1 * (n - alpha)) - sin(wc2 * (n - alpha))) / (%pi * (n - alpha)); end end

w = zeros(1, N); for n = 0 : N-1 w(n+1) = 0.42 - 0.5 * cos((2 * %pi * n) / (N - 1)) + 0.08 * cos((4 * %pi * n) / (N - 1)); end

h = hd .* w;

[H, w_freq] = frmag(h, 256);

figure; subplot(2, 1, 1); plot2d3(0:N-1, h);
plot(0:N-1, h, 'ro');
xtitle('Impulse Response', 'n', 'h(n)'); xgrid(1);

subplot(2, 1, 2); H_dB = 20 * log10(H);
plot(w_freq, H_dB); xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)'); xgrid(1);

# OUTPUT: 

<img width="1917" height="896" alt="image" src="https://github.com/user-attachments/assets/e1116e0a-c67b-4364-b591-5311dc8f7379" />

# RESULT: 
Thus design of BAND STOP FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.
