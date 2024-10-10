# Neuron-Number-Prediction

In this project I try to build a regression model to predict neuron counts in main brain regions of different species.

Forebr m - forebrain mass (cerebral cortex in mammals, pallium in birds),
Cer m - cerebellum mass,
rest m - rest of brain mass,
whole brain m - brain mass,
forebr n - number of neurons in forebrain,
cer n - number of neurons in cerebellum,
rest n - number of neurons in rest of the brain,
whole brain n - number of neurons in entire brain,
body m - body mass,
fmr % - relative mass of forebrain (to whole brain),
cmr % - relative mass of cerebellum,
rmr % - relative mass of rest of the brain.
All masses are provided in grams.

Most of the neuron count data is collected from articles cited in wikipedia's 'list of animals by number of neurons' page,
(https://en.wikipedia.org/wiki/List_of_animals_by_number_of_neurons),
numbers for many birds is colected from this article (https://www.nature.com/articles/s41559-022-01815-x),
additionally counts for 19 more bird species are colected from https://dspace.cuni.cz/handle/20.500.11956/151559 

and Harbour porpoise's numbers are from here (https://patzkelab.org/2019/06/10/30th-annual-meeting-of-cetology-study-group-of-japan-tokyo/).

Numbers for Short-finned pilot whale and Common minke whale are from https://sucupira.capes.gov.br/sucupira/public/consultas/coleta/trabalhoConclusao/viewTrabalhoConclusao.jsf?popup=true&id_trabalho=6349577

Only neural counts obtained by isotropic fractionator method are included.
