# URBANSOUND-CLASSIFICATION


# INTRODUCTION
In this project, the aim would that Our model will be trained to understand other types of sounds also.

# URBANSOUND DATASET : 

8732 LABELED SOUNDS (EXCERPTS TAKEN FROM [www.freesond.org](www.freesond.org) )
WEBSITE : [https://urbansounddataset.weebly.com/](https://urbansounddataset.weebly.com/)
#### 10 CLASSES
1. Air_conditioner
2. Car_horn
3. Children_playing
4. Dog_bark
5. Drilling
6. Enginge_idling
7. Gun_shot
8. Jackhammer
9. Siren
10. Street_music



## IMPORTANT TERMS

#### BIT RATE : 
	It is the number of bits processed per unit time.<br> 
	It is basically used to describe the amount of data being transferred into audio. <br>
	Higher bit rate generally means better audio quality
#### SAMPLING : 
	It is reduction of continuous-time signal into a discrete-time signal. 
	Example is the conversion of sound waves into sequences of samples.
#### SAMPLING FREQUENCY/RATE : 
	Number of samples taken over some fixed amount of time
#### AMPLITUDE : 
	Measure of change in soundwave over a period of time
#### FOURIER TRANSFORM : 
	Decomposes a function of time (Signal) into constituent frequencies.
#### BIT DEPTH : 
	It represents the number of possible amplitude values we can record for each sample. It can be : <br>
	1. 16 BIT : 65536 VALUES
	2. 24 BIT 16777216 VALUES
	3. 32 BIT : 4294967296 VALUES
#### MEL-SCALE : 
	A unit of PITCH proposed by Stevens, Volkmann and Newmann in 1937. 
	The mel scale is a scale of pitches judged by listeners to be equal in distance one from another. 
	The reference point between this scale and normal frequency measurement is defined by equating a 1000 Hz tone, 
	40 dB above the listener's threshold, with a pitch of 1000 mels. Below about 500 Hz the mel and hertz scales coincide; 
	above that, larger and larger INTERVALs are judged by listeners to produce equal pitch increments.
	
#### CEPSTRUM : 
	It is the result of computing inverse fourier transform of the logarithm of the estimated signal spectrum.
	Cepstrum pitch determination is particularly effective because the effects of the vocal excitation (pitch) 
	and vocal tract (formants) are additive in the logarithm of the power spectrum and thus clearly separate.
#### MFCC : 
	Mel-frequency cepstral coefficients (MFCCs) are coefficients that collectively make up an MFC. 
	They are derived from a type of cepstral representation of the audio clip (a nonlinear "spectrum-of-a-spectrum"). 
	The difference between the cepstrum and the mel-frequency cepstrum is that in the MFC, 
	the frequency bands are equally spaced on the mel scale, which approximates the human auditory system's response 
	more closely than the linearly-spaced frequency bands used in the normal cepstrum.
           

## LIBROSA
<p>
It is a python package for music and audio analysis. It provides the building blocks necessary to create music information retrieval systems.
	**samples, sampling_rate = librosa.load(filepath)**
The above function automatically converts the sampling rate to 22.05KHz. And also normalize the bit depth between -1 and 1 implicitly.
	**librosa.feature.mfcc(y=samples, sr=sampling_rate, n_mfcc = 40)**
Function to convert a discrete signal to mfcc. In this model we have taken 40 mfcc coefficients 
</p>
## MODEL IMPLEMENTATION 

In this problem statement we have used a simple deep learning model. <br>
MFCCs are calculated as a part of feature extraction. And this process is done in librosa.<br>
Dataset is split into 80:20 ratio of training and validation data. Model Architecture : 


## MODEL TRAINING 

Total Parameters : **700,682**
Non-trainable Parameters : **0**
Learning Rate = **0.001 (Implicit)**
Optimizer : **Adam**
Number of Epochs : **100 (Less might also work well)**
Batch Size : **32**


## MODEL RESULT 

TRAINING ACCURACY : **98.02%**
TRAINING LOSS : **0.0681**
VALIDATION ACCURACY : **92.90%**
VALIDATION LOSS : **0.5681**


## KAGGLE IMPLEMENTATION

[https://www.kaggle.com/captaininderpreet/urbansound8k-classification/](https://www.kaggle.com/captaininderpreet/urbansound8k-classification/)
