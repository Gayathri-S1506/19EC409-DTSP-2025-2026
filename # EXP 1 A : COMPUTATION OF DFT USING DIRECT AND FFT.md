# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 
To compute the Discrete Fourier Transform (DFT) of a given sequence using both the direct computation method and the Fast Fourier Transform (FFT) algorithm in Scilab, and to compare their results through magnitude and phase plots.
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
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/a1130972-ba4d-40c9-a481-1e8b36862d59" />


# RESULT: 
The DFT of the given sequence was successfully computed using both direct and FFT methods in Scilab, yielding identical results that validate the correctness of the FFT algorithm.
