##Remove EMG noise from ECG

## Goal

Familiarização com o Bitalino e software de aquisição Open Signals: uso do Bitalino para recolha de sinais de ECG poluídos com EMG; 
Tratamento dos sinais recolhidos com recurso a Python, removendo o ruído de EMG no sinal de ECG aquirido

## Team

* Ana Lúcia Castro
* Luísa Palmeira
* Maria Portugal

## Process

### Step 1 - First signal recorded

Após a colocação dos eléctrodos recolheram-se dois sinais. O melhor sinal obtido no Bitalino foi:

![first signal](https://github.com/LuisaPalmeira/Eletrofisiologia/blob/master/Imagem1.png?raw=true)


### Step 2 - Improved signal

![second signal](https://github.com/LuisaPalmeira/Eletrofisiologia/blob/master/Imagem2.png?raw=true)


### Step 3 - Defining the signal processing stages

Translação do sinal para zero; 
Tendo em conta que a frequência do EMG é bastante superior:
  Aplicou-se um filtro de banda, que filtra a 5 Hz, obtendo o primeiro sinal filtrado;
  De seguida, aplicou-se um filtro passa baixo, obtendo assim apenas o sinal ECG.
  
Nota: 
Como era muito difícil separar o ECG do EMG nos dois sinais recolhidos, o filtro de banda teve de filtrar a frequências mais baixas.

### Step 4 - The final outcome

![final signal](https://github.com/LuisaPalmeira/Eletrofisiologia/blob/master/Imagem2.png?raw=true)


### Code

from base64 import *
from numpy import *
from scipy import *
from pylab import *
from novainstrumentation import *
import novainstrumentation as ni
import numpy as np
import scipy.interpolate as si


x =loadtxt('C:\OpenSignals_3.0\AnaLu2.txt')

s = x[:,7]
 
print s

t=arange(len(s))/1000.
plot(t,s)

sm = s - mean(s)
sf = ni.code.bandpass(sm, 1., 5., fs=1000)
xlabel('t(s)')
ylabel('Sinal')
plot(t, sf)


sn = ni.code.smooth(sf, window_len=10, window='hanning')
plot(t,sn)



tight_layout ()
show ()
