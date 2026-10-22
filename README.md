# Neuron-Number-Prediction

In this project I try to build a regression model to predict neuron counts in main brain regions of different species.

Before starting, I want to remind that intelligence and complexity is not what makes life valuable, all living beings with small or large brains, with few or many neurons deserve to be happy and to live a joyful life.

Now let's start.

Recently it was found that forebrain neuron count is a better predictor of animal's intelligence than brain size or the encephalization quotient (EQ) [^1] [^3], it also often coincides with our intuitive perception of intelligence, for example primates have higher neuron densities [^2] and are generally considered to be more intelligent than other mammals with similar brain masses, corvids and parrots are another example [^4], although the importance of neuron counts in purely associative regions such as prefrontal cortex of mammals is also suggested [^3] [^5].

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
additionally neuron counts for 19 more bird species are colected from https://dspace.cuni.cz/handle/20.500.11956/151559 

and Harbour porpoise's numbers are from here (https://patzkelab.org/2019/06/10/30th-annual-meeting-of-cetology-study-group-of-japan-tokyo/).

Numbers for Short-finned pilot whale and Common minke whale are from https://sucupira.capes.gov.br/sucupira/public/consultas/coleta/trabalhoConclusao/viewTrabalhoConclusao.jsf?popup=true&id_trabalho=6349577

Only neural counts obtained by isotropic fractionator method are included.

## References

[1^]: https://www.nature.com/articles/s41559-022-01815-x?utm_source=researchgate.net&utm_medium=article 
[2^]: https://pmc.ncbi.nlm.nih.gov/articles/PMC1805542/
[3^]: https://www.sciencedirect.com/science/chapter/referencework/abs/pii/B978044327380300049X?via%3Dihub
[4^]: https://pmc.ncbi.nlm.nih.gov/articles/PMC4932926/
[5^]: https://onlinelibrary.wiley.com/doi/10.1002/cne.25298
