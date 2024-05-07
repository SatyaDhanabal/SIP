[x,fs]=audioread('C:\program Files\MATLAB\MATLAB Production Server\R2015a\bin\work\data\1-11.wav');
t=(0:length(x)-1)/Fs;
subplot(2,1,1);
plot(t,x);
legend('Waveform');
xlabel('Time (s)');
ylabel('Amplitde');
ncoeff= round(Fs/1000) +2;
a=ipc(x,ncoeff);
[h,f]=freqz(1,a,512,Fs);
subplot(2,1,2);
plot(f,20*log10(abs(h)+eps));
legend('LP Filter');
xlabel('Frequency(Hz)');
ylabel('Gain(dB)');
r=roots(a);
r=r(imag(r)>0.01);
ffreq=sort(atan2(imag(r),real(r))*Fs?(2*pi));
for i=1:length (ffreq)
fprintf('Fromant %d Frequency%.1f\n",i,ffreq(i));
end
