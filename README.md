 # Tracking Long-Term and Geographic Variation in Body Size Among Chinese Populations: Insights from Archaeological and Contemporary Evidence

This repository is organized into the following components:

## 1. Information on the Data

Provides information on published and original datasets utilized in the author's (Doudou Cao, DC) PhD research. The data focuses on body size dimensions across both archaeological and contemporary Chinese populations, including:

### Contemporary Populations
- **Scope**: Published anthropometric data on modern Chinese populations (mid-20th to early 21st century).  
- **Sample Size**: 79,133 adults (40,819 males, 38,314 females) from 189 groups, including:  
  - 86 Han groups (21,707 males, 20,523 females).  
  - 88 ethnic minority groups (16,323 males, 15,098 females) in lowland China.  
  - 15 ethnic minority groups on the Tibetan Plateau (e.g., Tibetan, Menba, Luoba, Sherpa).  
- **Time Periods**:  
  - **Mid-to-late 20th century** (1949–1999): Includes individuals born during the Great Chinese Famine (1959–1961), marked by malnutrition and developmental delays.  
  - **Early 21st century** (post-2000): Represents individuals benefiting from improved healthcare, urbanization, and living standards after China's 1978 economic reforms.  
- **Anthropometric Measures**: Group mean stature, body mass, and sitting height from individuals aged 18 and above.  

### Archaeological Populations
- **Scope**: Published and newly collected osteometric data from ancient Chinese populations (10,000–38 BP).  
- **Sample Size**: 3,152 individuals (1,715 males, 1,437 females) from 80 groups across 70 sites.  
  - Individual measurements available for 2,808 individuals (1,560 males, 1,371 females).  
  - The rest are published group means.  
- **Measurements**:  
  - Maximum limb lengths: Femur (FXL, n = 3,027), tibia (TXL, n = 1,252), humerus (HXL, n = 1,047), radius (RXL, n = 803).  
  - Bicondylar femur length (FBL, n = 102) and femoral head diameter (FHD, n = 1,587).  
  - **FXL** is used as a proxy for stature, reflecting its strong correlation with body height, while **FHD** serves as a proxy for body mass due to its biomechanical relationship with weight-bearing capacity.  

### Temporal and Cultural Categorization
To track temporal trends, the data were categorized into the following time periods:  
1. Early Neolithic (9,000–7,000 BP)  
2. Middle Neolithic (7,000–4,500 BP)  
3. Late Neolithic (4,500–3,500 BP)  
4. Bronze-Early Iron Age (3,500–2,152 BP)  
5. Early-Mid Iron Age (2,152–1,530 BP)  
6. Middle Iron Age (1,530–583 BP)  
7. Late Iron Age (582–38 BP)  

Groups were also categorized by subsistence strategies across historical periods:
1. Broad-spectrum subsistence during the Neolithic.
2. Early northern millet agriculture during the Neolithic.
3. Early southern rice agriculture during the Neolithic.
4. Northern agriculture during the Bronze and Early Iron Age.
5. Northern agriculture spanning the Early to Middle Iron Age.
6. Northern agriculture during the Late Iron Age.
7. Highland pastoralism or husbandry during the Bronze and Iron Age.

### Software
- Analyses were conducted in R using the following packages:
  -  `raster` for bioclimatic variable extraction.
  - `lm` for linear regression.
  - `MASS` for robust regression.
  - `lmerTest` for mixed-effects models.
---

## 2. Regression Analyses

### Contextualizing Body Form Variations
To examine relationships between body dimensions, environmental factors, and time, regression analyses were conducted:  
- **Environmental Variables**: Altitude, minimum and maximum temperatures, and precipitation were extracted using the WorldClim dataset v2.1.  
- **Models**:  
  - Robust regression for contemporary groups due to outliers.  
  - Linear and mixed-effects models for archaeological groups, incorporating site-specific random effects.  
- **Visualizations**: Regression coefficients were plotted to represent the direction and magnitude of relationships.  
                      Inverse Distance Weighting (IDW) was also used to represent spatial variability in body size for living and archaeological groups. This method emphasizes local environmental and cultural factors
---

## 3. Bayesian Modeling

### Methodology
To address the uneven distribution of samples in archaeological datasets, a Bayesian additive mixed model was applied to model femur lengths (FXL, n = 2,427). The model:  
- Utilized a smooth function to account for spatial (latitude/longitude), temporal, and sex-based variation.  
- Incorporated site-specific random effects to control for intra-site variability.   

### Computation
- Conducted using Markov Chain Monte Carlo (MCMC) methods with the Metropolis-Hastings algorithm.  
- Implemented in R using the `brms` package for Bayesian modeling and `rstan` for computation.
  
### Visualizations
- **Thin Plate Splines (TPS)** was applied to smooth Bayesian-modeled femur length data, addressing computational strain and uneven sampling by segmenting data into time periods and reducing the dataset for clarity.
---

This study seeks to provide a comprehensive framework for understanding how environmental, historical, and cultural factors influence body size variation in Chinese populations over time. Scripts and datasets are included for replication and further exploration.
