 exp 1 AIM:- To perform linear convolution of two signals, of nonperiodic
signals, periodic signals and random noise andinterpret the results obtained.
liner 
clc;
clear all;
close all;
x=input('enter the 1st sequence');
h=input('enter the 2nd sequence');
y = conv(x,h);
figure;
subplot(3,1,1);
stem(x);
ylabel('Amplitude --.');
xlabel('(a) n --.');
title('first sequence');
subplot(3,1,2);
stem(h);
ylabel('Amplitude --.');
xlabel('(b) n --.');
title('Second sequence');
subplot(3,1,3);
stem(y);
ylabel('Amplitude --.');
xlabel('(c) n --.');
title('result of linear convolution');
disp('The resultant signal is');

clc;
clear all;
xn=input("Enter ist seq");
hn=input('Enter 2nd seq');
yn= conv(xn,hn);
hnc=[1 2 0 0 ];
ync=cconv (xn, hnc, 4);
subplot(1,3,1);
stem(yn);
title('Result of linear conv'); subplot (1,3,2)
stem(ync);
title('Result of circular conv')
Enter 1st seq[1 2 3 4]
command 
Enter 1st seq[1 2 3 4]
Enter 2nd seq[1 2 0 0]

exp 3 :To obtain Discrete Fourier Transform and its Inverse using MATLAB
clc;
clear all;
xn=[1234]
xk=fft(xn)
xout=ifft(xk)
subplot(1,3,1)
stem (xn)
title('original signal')
subplot(1,3,2)
stem (xk)
title('DFT OF xn')
subplot(1,3,3)
stem (xout)
title('IDFT of xk')

 exp 4 AIM : Design and implementation of IIR BUTTERWORTH low pass filter to meet  the given specification. 

CODE :- 
clc;
close all;
clear all;
format long
rp=input('enter the passband ripple');
rs=input('enter the stopband ripple');
wp=input('enter the passband freq'); ws=input('enter the stopband freq');
fs=input('enter the sampling freq');
w1=2*wp/fs;w2=2*ws/fs;
[n, wn]=buttord (w1,w2,rp,rs, 's');
[z,p,k]=butter (n,wn);
[ba]=zp2tf(z,p,k);
[b, a]=butter (n,wn,'s');
w=0:.01:pi;
[h, om]=freqs (b, a, w);
m=20*log10(abs (h));
an=angle(h);
subplot(2,1,1); plot(om/pi,m);
ylabel ('Gain in dB -->'); xlabel('(a) Normalisedfrequency -->');
subplot(2,1,2); plot(om/pi,an);
xlabel('(b) Normalised frequency -->');
ylabel('Phase in radians -->');

COMMAND WINDOW :
enter thepassbandripple0.15
enter the stopband ripple60
enter the passband freq1500
enter the stopband freq3000
enter the sampling freq7000

exp 5 AIM : Design and implementation of IIR BUTTERWORTH high pass filter to meet  the given specification. 
CODE :- 

clc; 
close all; 
clear all; 
format long 
rp=input('enter the passband ripple'); 
rs=input('enter the stopband ripple'); 
wp=input('enter the passband freq'); 
ws=input('enter the stopband freq'); 
fs=input('enter the sampling freq'); 
w1=2*wp/fs; 
w2=2*ws/fs; 
[n,wn]=buttord(w1,w2,rp,rs,'s'); 
[b,a]=butter(n,wn,'high','s'); 
w=0:.01:pi; 
[h,om]=freqs(b,a,w); 
m=20*log10(abs(h)); 
an=angle(h); 
subplot(2,1,1); 
plot(om/pi,m); 
ylabel('Gain in dB -->'); 
xlabel('(a) Normalised frequency --c>'); 
subplot(2,1,2); 
plot(om/pi,an); 
xlabel('(b) Normalised frequency --> '); 
ylabel('Phase in radians'); 

COMMAND WINDOW : 
enter the passband ripple 0.2 
enter the stopband ripple 40 
enter the passband freq 2000 
enter the stopband freq 3500 
enter the sampling freq 8000 

exp 6 AIM:- Design and implementation of IIR Chebyshev filter to meet the given specifications.
SOFTWARE REQUIRED:

clc; 
close all;
clear all;
format long
rp=input('enter the passband ripple...');
rs=input('enter the stopband ripple...');
wp=input('enter the passband freq...');
ws=input('enter the stopband freq...');
fs=input('enter the sampling freq...');
w1=2*wp/fs;w2=2*ws/fs;
[n,wn]=cheb1ord(w1,w2,rp,rs,'s');
[b,a]=cheby1(n,rp,wn, 's');
w=0:.01:pi;
[h, om]=freqs (b,a,w);
m=20*log10(abs(h));
an=angle(h);
subplot(2,1,1);plot(om/pi,m);
ylabel('Gain in dB -->'); xlabel('(a) Normalisedfrequency -->');
subplot (2,1,2);plot(om/pi, an);
xlabel('(b) Normalised frequency -->');
ylabel('Phase in radians -->');

command :
enter the passband ripple 0.23
enter the stopband ripple 47
enter the passband freq 1300 
enter the stopband freq 1550
enter the sampling freq 7800

 exp8 AIM:- to observe finite word length effects
SOFTWARE REQUIRED:System with MATLAB 7.0.
THEORY:- Write Description Of fix(), sign(), abs() Function.
PROGRAM: 

% equivalent beq of the binary representation
% of a decimal number d with n bits for the
% magnitude part obtained by rounding
%
m = 1; d=75.25; n=5; d1 = abs(d);
while fix(d1) > 0
d1 = abs(d)/(10^m);
m = m+1;
end
beq = 0; d1 = d1 + 2^(-n-1);
for k = 1:n
beq = fix(d1*2)/(2^k) + beq;
d1 = (d1*2) - fix(d1*2);
end


