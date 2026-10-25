# Neuron-Number-Prediction

In this project I try to build a regression model to predict neuron counts in main brain regions of different species.

Before starting, I want to remind that intelligence and complexity is not what makes life valuable, all living beings with small or large brains, with few or many neurons deserve to be happy and to live a joyful life.

Now let's start.

# Introduction
Recently it was found that forebrain neuron count is a better predictor of animal's intelligence than brain size [^1] or the encephalization quotient (EQ) [^3], it also often coincides with our intuitive perception of intelligence, for example primates have higher neuron densities [^2] and are generally considered to be more intelligent than other mammals with similar brain masses, corvids and parrots are another example [^4], although the importance of neuron counts in purely associative regions [^5] such as prefrontal cortex of mammals is also suggested [^3].
Cetacean are especially an interesting case, there is a high probability that several species are sapient, and there is a controversy in their neuron count estimates with different researchers getting very different results when measuring neuron densities in the cortices of the same species using stereological methods. The question of how intelligent are different cetacean species? is very important, since anything comparable to humans will have implications akin to making a contact with alien civilization.
Because there is less room for errors when applying the isotropic fractionator method [^6], only neuron counts obtained by that or very similar methods will be used.

## Note on Short-finned pilot whale neuron count

According to [this blog post](https://darwinianconservatism.blogspot.com/2026/01/do-large-cetacean-brains-deny-human.html?m=1) only total cell counts of Short-finned pilot whale brain structures are certainly correct, but I find it significantly more likely, that the 11.85 billion cortical neuron count present in dissertation is an underestimate than an overestimate, because total cell count is very high.
Let's look at numbers.
From dissertation [^7]
cortex mass - 1835.9 gram,
cortical neurons - 11.85 billion,
cortical other cells (glial + endothelial cells) - 339.29 billion.

From these numbers we can obtain 184.8 million other cells in a gram of cortex other cells density.
Note, that in dissertation the number for density is nearly twice lower, but since neuron density is also twice lower than what we get by dividing the count by mass and both 11.85 billion count and 1800 gram mass are present elsewhere, including in the abstract, it much more likely that density and not other values are incorrect.
If we look at the mammalian datasets [^8] [^9], the highest other cell density has Smoky shrew 111.754 million/gram, and the variation in other cell density is much lower than that of neurons, with most species falling between 40 - 80 million/gram range, assuming even 120 million/gram other cell density in Short-finned pilot whale cortex will still mean 220 billion other cells and 130 billion neurons in the cortex, so Pilot whale are very large outliers either in neuron count, other cells count or in both.


# Abbreviations in csv data files
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

# Sources of the data used
Most of the neuron count data is collected from articles cited in wikipedia's [list of animals by number of neurons page](https://en.wikipedia.org/wiki/List_of_animals_by_number_of_neurons),
numbers for many birds are colected from [^1] article,

and Harbour porpoise's numbers are from [here](https://patzkelab.org/2019/06/10/30th-annual-meeting-of-cetology-study-group-of-japan-tokyo/).

Numbers for Short-finned pilot whale and Common minke whale are from [^7]


## References

[^1]: [Sol, D., Olkowicz, S., Sayol, F. et al. Neuron numbers link innovativeness with both absolute and relative brain size in birds. Nat Ecol Evol 6, 1381–1389 (2022). https://doi.org/10.1038/s41559-022-01815-x](https://www.nature.com/articles/s41559-022-01815-x?utm_source=researchgate.net&utm_medium=article) 
[^2]: [S. Herculano-Houzel, C.E. Collins, P. Wong, & J.H. Kaas, Cellular scaling rules for primate brains, Proc. Natl. Acad. Sci. U.S.A. 104 (9) 3562-3567, https://doi.org/10.1073/pnas.0611396104 (2007).](https://www.pnas.org/doi/full/10.1073/pnas.0611396104)
[^3]: [Suzana Herculano-Houzel,
2.07 - The neuron number manifesto: Let's drop body mass from the search for biological correlates of intelligent, flexible cognition in evolution,
Editor(s): Jon H. Kaas, Suzana Herculano-Houzel,
Evolution of Nervous Systems (Third Edition),
Academic Press,
2026,
Pages 183-198,
ISBN 9780443273810,
https://doi.org/10.1016/B978-0-443-27380-3.00049-X.
(https://www.sciencedirect.com/science/article/pii/B978044327380300049X)](https://www.sciencedirect.com/science/chapter/referencework/abs/pii/B978044327380300049X?via%3Dihub)
[^4]: [Olkowicz S, Kocourek M, Lučan RK, Porteš M, Fitch WT, Herculano-Houzel S, Němec P. Birds have primate-like numbers of neurons in the forebrain. Proc Natl Acad Sci U S A. 2016 Jun 28;113(26):7255-60. doi: 10.1073/pnas.1517131113. Epub 2016 Jun 13. PMID: 27298365; PMCID: PMC4932926.](https://pmc.ncbi.nlm.nih.gov/articles/PMC4932926/)
[^5]: [Ströckens, F., Neves, K., Kirchem, S., Schwab, C., Herculano-Houzel, S., & Güntürkün, O. (2022). High associative neuron numbers could drive cognitive performance in corvid species. Journal of Comparative Neurology, 530, 1588–1605. https://doi.org/10.1002/cne.25298](https://onlinelibrary.wiley.com/doi/10.1002/cne.25298)
[^6]: [Herculano-Houzel S, Lent R. Isotropic fractionator: a simple, rapid method for the quantification of total cell and neuron numbers in the brain. J Neurosci. 2005 Mar 9;25(10):2518-21. doi: 10.1523/JNEUROSCI.4526-04.2005. PMID: 15758160; PMCID: PMC6725175.](https://pmc.ncbi.nlm.nih.gov/articles/PMC6725175/)
[^7]: [Short-finned pilot whale and minke neuron count](https://sucupira.capes.gov.br/sucupira/public/consultas/coleta/trabalhoConclusao/viewTrabalhoConclusao.jsf?popup=true&id_trabalho=6349577)
[^8]: [Herculano-Houzel S, Catania K, Manger PR, Kaas JH (2015). "Mammalian Brains Are Made of These: A Dataset of the Numbers and Densities of Neuronal and Nonneuronal Cells in the Brain of Glires, Primates, Scandentia, Eulipotyphlans, Afrotherians and Artiodactyls, and Their Relationship with Body Mass". Brain, Behavior and Evolution. 86 (3–4). S. Karger AG: 145–63. doi:10.1159/000437413. PMID 26418466. S2CID 10637829](https://karger.com/bbe/article/86/3-4/145/47190/Mammalian-Brains-Are-Made-of-These-A-Dataset-of)
[^9]: [Jardim-Messeder D, Lambert K, Noctor S, Pestana FM, de Castro Leal ME, Bertelsen MF, Alagaili AN, Mohammad OB, Manger PR, Herculano-Houzel S. Dogs Have the Most Neurons, Though Not the Largest Brain: Trade-Off between Body Mass and Number of Neurons in the Cerebral Cortex of Large Carnivoran Species. Front Neuroanat. 2017 Dec 12;11:118. doi: 10.3389/fnana.2017.00118. PMID: 29311850; PMCID: PMC5733047.](https://pmc.ncbi.nlm.nih.gov/articles/PMC5733047/)
