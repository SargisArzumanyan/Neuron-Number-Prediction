# Neuron-Number-Prediction

In this project I try to build a regression model to predict neuron counts in main brain regions of different species.

Before starting, I want to remind that intelligence and complexity is not what makes life valuable, all living beings with small or large brains, with few or many neurons deserve to be happy and to live a joyful life.

Now let's start.

# Introduction

Defining what is intelligence is always subjective and heavily depends on culture, here i will use definition very similar to that of [fluid intelligence](https://en.wikipedia.org/wiki/Fluid_and_crystallized_intelligence).
Recently it was found that forebrain neuron count is a better predictor of animal's intelligence than brain size [^1] or the encephalization quotient (EQ) [^3], it also often coincides with our intuitive perception of intelligence, for example primates have higher neuron densities [^2] and are generally considered to be more intelligent than other mammals with similar brain masses, corvids and parrots are another example [^4], although the importance of neuron counts in purely associative regions [^5] such as prefrontal cortex of mammals is also suggested [^3].
Cetacean are especially an interesting case, there is a high probability that several species are sapient, and there is a controversy in their neuron count estimates with different researchers getting very different results when measuring neuron densities in the cortices of the same species using stereological methods [^11] [^12]. The question of how intelligent are different cetacean species? is very important, since anything comparable to humans will have implications akin to making a contact with alien civilization.

## Why only use data obtained by isotropic fractionator or similar methods? 
Neurons are distributed very unevenly across cortical and other brain regions, counting them only in a few sampled areas may not give accurate results, especially for large brains.
Isotropic fractionator solves that problem by turning the structure such as cerebral cortex or pieces of it into a uniform suspension of free-floating cell nuclei, which are distributed evenly, and the densities in small samples become very close to the true average density [^6].

## Note on Short-finned pilot whale neuron count

According to [this blog post](https://darwinianconservatism.blogspot.com/2026/01/do-large-cetacean-brains-deny-human.html?m=1) only total cell counts of Short-finned pilot whale brain structures are certainly correct, but I find it significantly more likely, that the 11.85 billion cortical neuron count present in dissertation is an underestimate than an overestimate, because total cell count is very high.
Let's look at numbers.
From dissertation [^7]
cortex mass - 1835.9 gram,
cortical neurons - 11.85 billion,
cortical other cells (glial + endothelial cells) - 339.29 billion.

From these numbers we can obtain 184.8 million other cells in a gram of cortex other cells density.
Note, that in dissertation the number for density is nearly twice lower, but since neuron density is also twice lower than what we get by dividing the count by mass and both 11.85 billion count and 1800 gram mass are present elsewhere, including in the abstract, it much more likely that density and not other values are incorrect.
If we look at the mammalian datasets [^8] [^9] [^10], the highest other cell density has Smoky shrew 111.754 million/gram, and the variation in other cell density is much lower than that of neurons, with most species falling between 40 - 80 million/gram range, assuming even 120 million/gram other cell density in Short-finned pilot whale cortex will still mean 220 billion other cells and 130 billion neurons in the cerebral cortex, so Pilot whale are very large outliers either in neuron count, other cells count or in both.

# Results

# Mammals

## Data exploration and visualization

Let's first look at pictures.
Note that cetaceans belong to the order Artiodactyla, which is also sometimes called Cetaartiodactyla, to which alongside cetaceans belong animals such as Deers, Pigs, Giraffes, currently, there are only 3 cetaceans in the dataset, Harbor porpoise, Minke whale, and Short-finned pilot whale, which occupy highest 3 values of Artiodactyla (have lilac color on graphs) 

### Scatter plots

1. As we can see in Primates (pink) neuron counts grow faster with cortical mass
<img width="1007" height="679" alt="image" src="https://github.com/user-attachments/assets/b5e2362d-434e-4305-a558-d0a1cb1369c1" />

2. The same is true for cerebellum, but the difference is smaller
<img width="995" height="679" alt="image" src="https://github.com/user-attachments/assets/90f1512a-77b8-4596-87e2-f3a18a71a6f8" />

3. In all orders cortical neuron density falls as brains get larger, but Primates have higher neuron densities than others
<img width="1007" height="679" alt="image" src="https://github.com/user-attachments/assets/d2e6c4b1-a9ee-4526-a79e-c4609b34fdcd" />

4. The same is true for cerebellum
<img width="999" height="679" alt="image" src="https://github.com/user-attachments/assets/9a1e5d67-f629-4319-b642-e802f3444468" />

### Histograms

1. Most forebrain mass values are concentrated between 0.1 - 1 gram and 1 - 100 gram ranges
<img width="987" height="697" alt="image" src="https://github.com/user-attachments/assets/d8e57efd-164c-4d77-b6f0-1f9d4067c436" />

2. Most forebrain neuron count values are between 10 million - 100 million followed by 100 million - 1 billion ranges
<img width="987" height="697" alt="image" src="https://github.com/user-attachments/assets/bc3174d3-f73d-4417-aa29-80091c98e7e0" />

3. Most cerebellum mass values are between 0.1 - 1 gram range and between 1 - 10 gram range
<img width="987" height="697" alt="image" src="https://github.com/user-attachments/assets/28c9dfb8-7668-429d-840a-c66a5152195c" />

4. Most cerebellum neuron counts are between 10 million and billion or bitween 1 billion and 10 billion 
<img width="987" height="697" alt="image" src="https://github.com/user-attachments/assets/21d482ad-ac00-4d60-be16-fcb002e014ac" />

### Correlation coefficients between different features

<img width="1724" height="816" alt="image" src="https://github.com/user-attachments/assets/905383a5-d8e1-43e6-91c2-b2e90c6c8d97" />

As we can see forebrain neuron count (Forebrain n) has the highest correlation with forebrain mass (Forebrain m), which has the value of 0.71
and cerebellum neuron count (Cerebellum n) is most correlated with cerebellum mass (Cerebellum m) which has the value of 0.98.
Interestingly forebrain neuron density (Forebrain n d) and cerebellum neuron density (Cerebellum n d) are highly correlated with each other with value of 0.8, suggesting coordinated evolution of 2 structures. 

### The ratios between maximum and minimum values of different features

<img width="462" height="458" alt="AdobeExpressPhotos_c455aa9a177a425b867e8acc79cf8363_CopyEdited" src="https://github.com/user-attachments/assets/d57d1123-7262-482b-b01e-3c25da24d25b" />

As we can see the variation in cerebellum mass and cerebellum neuron counts is larger than that for forebrain

## Regression

Let try to build regression models to predict Forebrain and Cerebellum neuron counts.
Random forest regressor is used.

### Regression with many numerical features, some of which are correlated with each other

The following features are used for this model

"Forebrain m", "Cerebellum m", "Whole brain m", "Body m", "Forebrain m r %", "Cerebellum m r %", "Forebrain m per body m",
          "Cerebellum m per body m", "Whole brain m per body m"

For forebrain neuron count 

r2 score and mean squared error values are

<img width="654" height="169" alt="AdobeExpressPhotos_7d9133faffa84b6fbce9858e83ee0c19_CopyEdited" src="https://github.com/user-attachments/assets/48e1ee0a-2a74-4986-9d6b-9513676ac785" />

Features ranked by importance

<img width="833" height="560" alt="image" src="https://github.com/user-attachments/assets/a3609f3a-b954-49f4-9276-3fbb44c14c0a" />

For cerebellum neuron count

r2 score and mean squared error

<img width="728" height="176" alt="AdobeExpressPhotos_6535ef038231489f9bcf95894d3778bc_CopyEdited" src="https://github.com/user-attachments/assets/3debdb99-30d3-49c7-bce0-1af982ad6f2b" />

features ranked by importance

<img width="833" height="560" alt="image" src="https://github.com/user-attachments/assets/31171512-4e16-4ba6-b068-046b10662bcc" />

As we can see forebrain neuron counts are much easier to predict

### Regression with each individual feature

The results for forebrain neuron count

<img width="435" height="441" alt="AdobeExpressPhotos_5b1b5380d69142a5a4e451ab7be12e75_CopyEdited" src="https://github.com/user-attachments/assets/63bc4f2d-6444-4e22-bdfe-633e87a0c5a2" />

As we can see Cerebellum mass, whole brain mass and forebrain mass are the most informative features with 0.8992, 0.88, 0.8776 r2 scores respectively.
This scores are considerably higher than the ones obtained when combined features were used in previous section, suggesting that the existence of correlation between different features caused multicollinearity and made the results worse.

But for cerebellum no improvement was made, with body mass being the most informative feature with r2 score of 0.57.

<img width="451" height="440" alt="AdobeExpressPhotos_b78715caf0224d80b89da071058eebe2_CopyEdited" src="https://github.com/user-attachments/assets/2c3db2e1-f5ea-4c7d-8b48-268a1d7d1f14" />

### Let's pair 1 most intuitively important feature with each of others, including categorical taxonomic features, 'order' and 'family'

For forebrain neuron count, the forebrain mass feature will be paired with the rest.

<img width="463" height="732" alt="AdobeExpressPhotos_ecd3b667a0a1402cb42c4ae6b8c3711b_CopyEdited" src="https://github.com/user-attachments/assets/10f34125-72c2-4649-ab95-9ea4d4bf0588" />

As we can see adding taxonomic information improved the results, with 'Forebrain m' and 'Family' the r2 score is 0.9037.

For cerebellum neuron count, the cerebellum mass will be paired in the same way.

<img width="497" height="724" alt="image" src="https://github.com/user-attachments/assets/11c5e333-ad0f-4963-935d-c15d85f81f9e" />

As we can see, in this case no improvement was made

### Using structure mass + both taxonomic features

<img width="518" height="117" alt="AdobeExpressPhotos_d0d0ebd97a164f09a51b6947b2d6bfcd_CopyEdited" src="https://github.com/user-attachments/assets/e324aad0-4da5-4273-b24b-6e72a96e5e97" />

As we can see, the r2 score for forebrain neuron count improved farther up to 0.9438, but for cerebellum neuron count no improvement was made.

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
[^7]: [Short-finned pilot whale and Minke whale neuron counts](https://sucupira.capes.gov.br/sucupira/public/consultas/coleta/trabalhoConclusao/viewTrabalhoConclusao.jsf?popup=true&id_trabalho=6349577)
[^8]: [Herculano-Houzel S, Catania K, Manger PR, Kaas JH (2015). "Mammalian Brains Are Made of These: A Dataset of the Numbers and Densities of Neuronal and Nonneuronal Cells in the Brain of Glires, Primates, Scandentia, Eulipotyphlans, Afrotherians and Artiodactyls, and Their Relationship with Body Mass". Brain, Behavior and Evolution. 86 (3–4). S. Karger AG: 145–63. doi:10.1159/000437413. PMID 26418466. S2CID 10637829](https://karger.com/bbe/article/86/3-4/145/47190/Mammalian-Brains-Are-Made-of-These-A-Dataset-of)
[^9]: [Jardim-Messeder D, Lambert K, Noctor S, Pestana FM, de Castro Leal ME, Bertelsen MF, Alagaili AN, Mohammad OB, Manger PR, Herculano-Houzel S. Dogs Have the Most Neurons, Though Not the Largest Brain: Trade-Off between Body Mass and Number of Neurons in the Cerebral Cortex of Large Carnivoran Species. Front Neuroanat. 2017 Dec 12;11:118. doi: 10.3389/fnana.2017.00118. PMID: 29311850; PMCID: PMC5733047.](https://pmc.ncbi.nlm.nih.gov/articles/PMC5733047/)
[^10]: [Sandra E. Dos Santos, Jairo Porfirio, Felipe B. da Cunha, Paul R. Manger, William Tavares, Leila Pessoa, Mary Ann Raghanti, Chet C. Sherwood, Suzana Herculano-Houzel; Cellular Scaling Rules for the Brains of Marsupials: Not as “Primitive” as Expected. Brain Behav Evol 31 March 2017; 89 (1): 48–63. https://doi.org/10.1159/000452856](https://karger.com/bbe/article-abstract/89/1/48/47074/Cellular-Scaling-Rules-for-the-Brains-of?redirectedFrom=fulltext)
[^11]: [C. Poth, C. Fung, O. Güntürkün, S.H. Ridgway, H.H.A. Oelschläger,
Neuron numbers in sensory cortices of five delphinids compared to a physeterid, the pygmy sperm whale,
Brain Research Bulletin,
Volume 66, Issues 4–6,
2005,
Pages 357-360,
ISSN 0361-9230,
https://doi.org/10.1016/j.brainresbull.2005.02.001.
(https://www.sciencedirect.com/science/article/pii/S0361923005000420)](https://www.bio.psy.ruhr-uni-bochum.de/bpsy/mam/content/documents/poth_2005_neuron_numbers_in_sensory_cortices_of_five_delphinids.pdf)
[^12]: [Ridgway SH, Brownson RH, Van Alstyne KR, Hauser RA. Higher neuron densities in the cerebral cortex and larger cerebellums may limit dive times of delphinids compared to deep-diving toothed whales. PLoS One. 2019 Dec 16;14(12):e0226206. doi: 10.1371/journal.pone.0226206. PMID: 31841529; PMCID: PMC6914331.](https://pmc.ncbi.nlm.nih.gov/articles/PMC6914331/)
