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

![first signal](C:\Users\LuisaPalmeira\Documents\GitHub\Eletrofisiologia\Imagem1.png)


### Step 2 - Improved signal

![second signal](C:\Users\LuisaPalmeira\Documents\GitHub\Eletrofisiologia\Imagem2.png)


### Step 3 - Defining the signal processing stages

Translação do sinal para zero; 
Tendo em conta que a frequência do EMG é bastante superior:
  Aplicou-se um filtro de banda, que filtra a 5 Hz, obtendo o primeiro sinal filtrado;
  De seguida, aplicou-se um filtro passa baixo, obtendo assim apenas o sinal ECG.
  
Nota: 
Como era muito difícil separar o ECG do EMG nos dois sinais recolhidos, o filtro de banda teve de filtrar a frequências mais baixas.

### Step 4 - The final outcome

![final signal](C:\Users\LuisaPalmeira\Documents\GitHub\Eletrofisiologia\Imagem2.png)

