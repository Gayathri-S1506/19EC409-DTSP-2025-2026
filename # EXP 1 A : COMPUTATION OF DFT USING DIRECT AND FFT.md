# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 
To compute the Discrete Fourier Transform (DFT) of a given sequence using both direct computation and the Fast Fourier Transform (FFT) in SCILAB, and to compare their magnitude and phase spectra.
# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
// DISCRETE FOURIER TRANSFORM 
x = [1, 2, 3, 4];
N = length(x);
X_direct = zeros(1, N);

for k = 0:N-1
    X_direct(k+1) = sum(x .* exp(-%i*2*%pi*k*(0:N-1)/N));
end

X_fft = fft(x);

scf(0);
subplot(2,1,1);
plot(0:N-1, abs(X_direct), 'r-o');
xtitle("Magnitude of DFT (Direct)", "k", "|X(k)|");
xgrid();

subplot(2,1,2);
plot(0:N-1, abs(X_fft), 'b-*');
xtitle("Magnitude of DFT (FFT)", "k", "|X(k)|");
xgrid();

scf(1);
subplot(2,1,1);
plot(0:N-1, angle(X_direct), 'r-o');
xtitle("Phase of DFT (Direct)", "k", "Phase (radians)");
xgrid();

subplot(2,1,2);
plot(0:N-1, angle(X_fft), 'b-*');
xtitle("Phase of DFT (FFT)", "k", "Phase (radians)");
xgrid();


# OUTPUT: 
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/e510fa5e-ef0d-4afe-9f21-55f7cd8193e9" />


# RESULT: 
The program successfully computes and displays the DFT and FFT of the input sequence, showing matching magnitude and phase plots, verifying the equivalence of both methods.
