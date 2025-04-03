Input files:
- samples_openrefine_lesson.csv -- the messy dataset from the OpenRefine lesson 
- data_cleaning_script.txt -- the OpenRefine operations you've extracted

Output files:
- samples_openrefine_lesson_clean.csv -- the clean dataset resulting from the OpenRefine lesson

Instructions:
1. Start a new project in OpenRefine using the messy dataset you downloaded before (`samples_openrefine_lesson.csv`). Give the project a new name.
2. Click the `Undo / Redo` tab > `Apply` and paste in the contents of the data_cleaning_script.txt file you just created with the JSON code.
3. Click `Perform operations`. The dataset should now be the same as your other cleaned dataset.


# Secure and federated genome-wide association studies for biobank-scale datasets

Sharing data across institutions for genome-wide association studies (GWAS) would enhance the discovery of genetic variation linked to health and disease1,2. However, existing data-sharing regulations limit the scope of such collaborations3. Although cryptographic tools for secure computation promise to enable collaborative analysis with formal privacy guarantees, existing approaches either are computationally impractical or do not implement current state-of-the-art methods4,5,6. We introduce secure federated genome-wide association studies (SF-GWAS), a combination of secure computation frameworks and distributed algorithms that empowers efficient and accurate GWAS on private data held by multiple entities while ensuring data confidentiality. SF-GWAS supports widely used GWAS pipelines based on principal-component analysis or linear mixed models. We demonstrate the accuracy and practical runtimes of SF-GWAS on five datasets, including a UK Biobank cohort of 410,000 individuals, showcasing an order-of-magnitude improvement in runtime compared to previous methods. Our work enables secure collaborative genomic studies at unprecedented scale.


## Introduction

Secure computation frameworks from modern cryptography offer promising strategies to address privacy concerns in collaborative genomic studies3,7,8,9. These techniques allow a group of parties to jointly analyze their data by exchanging encrypted information while ensuring that each party’s data remain private from others. Although recent work has illustrated the potential of this strategy for genome-wide association studies (GWAS)4,5,6, existing methods remain limited in practical utility. Prior work based on the framework of secure multiparty computation (MPC)4 is prohibitively slow for large biobank-scale cohorts (as demonstrated in this work) and requires the external sharing of entire input datasets in encrypted form, which may not be feasible in practice due to security risks. More recent methods based on homomorphic encryption (HE) schemes5,6 improve efficiency but fail to support the standard analysis pipelines commonly used by researchers due to their computational complexity. These pipelines include those based on principal-component analysis (PCA) and linear mixed models (LMMs), which provide strategies to account for population structure within a study cohort to accurately estimate association signals10,11.
