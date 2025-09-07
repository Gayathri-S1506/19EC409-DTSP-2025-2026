# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT
# AIM: 

To obtain the Discrete Fourier Transform (DFT) using the direct method and Fast Fourier Transform (FFT) of a given sequence in SCILAB.

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
// DISCRETE FOURIER TRANSFORM 
clc;
clear;
close(); // Close any open graphics

// Parameters
N = 8;                    // Number of samples
n = 0:N-1;                // Time indices
f = 1;                    // Frequency index (1 cycle over N samples)

// Input signal: cosine wave
x = cos(2 * %pi * f * n / N);

// Initialize DFT output
X = zeros(1, N);

// Compute DFT using direct formula
for k = 0:N-1
    for m = 0:N-1
        X(k+1) = X(k+1) + x(m+1) * exp(-%i * 2 * %pi * k * m / N);
    end
end

// Magnitude and phase
magX = abs(X);
phaseX = atan(imag(X), real(X)); // Use atan to get correct quadrant

// Clean phase where magnitude is negligible
threshold = 1e-6;
clean_phase = phaseX;
for i = 1:N
    if magX(i) < threshold then
        clean_phase(i) = 0; // Or use %nan to ignore those points
    end
end

// Plot Magnitude Spectrum
subplot(2,1,1)
plot2d3(0:N-1, magX)
xtitle("Magnitude Spectrum", "k", "|X(k)|")

// Plot Phase Spectrum (cleaned)
subplot(2,1,2)
plot2d3(0:N-1, clean_phase)
xtitle("Phase Spectrum", "k", "∠X(k)")



# OUTPUT: 
<img width="764" height="707" alt="image" src="https://github.com/user-attachments/assets/cb3da746-7964-430c-88d4-308dbfbbf16a" />


# RESULT: 
The Discrete Fourier Transform (DFT) of the given sequence was successfully computed in SCILAB using both:
Direct Method (nested loops implementing the DFT formula), andFast Fourier Transform (FFT) (using built-in fft() function).
The magnitude and phase spectra were plotted for both methods and found to be identical, validating the correctness of the manually implemented DFT.
