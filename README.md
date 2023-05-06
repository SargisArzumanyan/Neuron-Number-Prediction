# Neuron-Number-Prediction

In this project I try to build a regression model to predict neuron counts in main brain regions of different species.
As you can see, results aren't great, sometimes I manage to get high r2_scores, but it strongly depends on train test split.
Hyperparameter tuning doesn't help much, probably more feature engineering is nedded.

Forebr m - forebrain mass (cerebral cortex in mammals, pallium in birds)
Cer m - cerebellum mass
rest m - rest of brain mass
forebr n - number of neurons in forebrain
cer n - number of neurons in cerebellum
rest n - number of neurons in rest of the brain
body m - body mass
fmr % - relative mass of forebrain (to whole brain)
cmr % - relative mass of cerebellum
rmr % - relative mass of rest of the brain
