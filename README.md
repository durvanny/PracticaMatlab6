# PracticaMatlab6
Tarea
clear
nneg=-30:-1; %numero negativos
npos=1:30;   %numeros positivos
n=nneg;      %contenedor negativo
Fnneg=(1./(1i*n*pi)).*(-3*exp(-1i*n*6*pi/7)+2*exp(1i*n*2*pi/7)+exp(-1i*n*12*pi/7));
%funcion exponencial de las series de fourier de numeros negativos
n=npos;      %contenedor positivo
Fnpos=(1./(1i*n*pi)).*(-3*exp(-1i*n*6*pi/7)+2*exp(1i*n*2*pi/7)+exp(-1i*n*12*pi/7));
%funcion de la exponencial de las series de fourier de numeros negativos
F0=10/7;  %funcion final    
n=[nneg,0,npos]; %variable contenedora de numeros
Fn=[Fnneg,F0,Fnpos]; %variable contenedora funciones
k=0;
 
for t=-1:.01:6 %bucle para periodo 
k=k+1;
fapprox(k)=sum(Fn.*(exp(1i*n*2*pi*t/7))); %fapprox= es un vector
end
t=-1:.01:6; %periodo
fexact=4*(t<=3)-2*(t>=3);
plot(t,fapprox,t,fexact); %plot dibuja funciones de variables
grid on

