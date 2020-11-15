+++
categories = ["computational-biology"]
coders = []
date = 2020-11-15T10:36:12+05:30
description = "Cancer Subtype Discovery from Multimodal Omic Data"
github = ["https://github.com/evi1haxor/"]
gdrive = ["https://drive.google.com/s"]
image = "https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1591793276/logos/logos_hugo_h2xbne.svg"
title = "Cancer Subtyping Algorithm"
type = "post"
[[tech]]
logo = "https://res.cloudinary.com/samrobbins/image/upload/v1591793276/logos/logos_hugo_h2xbne.svg"
name = "Hugo"
url = "#"
[[tech]]
logo = "https://res.cloudinary.com/samrobbins/image/upload/v1591793279/logos/logos_uikit_irc5gp.svg"
name = "UIkit"
url = "#"
[[tech]]
logo = "https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1593603175/forestry-pos-full_lid6rs.svg"
name = "Forestry CMS"
url = "#"

+++
# Cancer Subtype Discovery from Multi-modal Omic Data

Needless to say how bad a disease cancer is. [As per WHO](https://www.who.int/news-room/fact-sheets/detail/cancer), cancer is the second-largest non-infectious reason for the death by natural cause in humans. Cancer has been around for millions of years. The earliest cancer research dates back to the 1700s. Yet, there had been no promising cure for this disease. We have found the cure of so many diseases. Even completely eradicated many from the face of the earth altogether. That makes it even stupefying that still there is no cure for cancer disease. One might even notice that medicinal progress of human civilization has hit a bit of a stumbling block in the 21st century. The reason could be the same as it is for the difficulty in discovering the drug-based cure for the cancer disease. The diseases left-over, like cancer, have another layer of difficulty to them. Unlike those whose cure has been found, diseases like cancer simply do not respond to the conventional one-size-fits-all solution[2]. Cancer is not one disease. It is thousands of diseases in itself. Even the patients with the same type of cancer are not necessarily the same at the molecular level[3]. That is why discovering a single drug to cure all cancer types is not possible as there is no single cure for cancer in the first place. That is where personalised medicines[4] come into the picture. It is about tailoring the medicinal treatment of a patient based on his/her molecular activity as manifested in the characteristics and symptoms during the treatment of a disease. With the rise of the information revolution[5], a huge amount of clinical data is being generated on a daily basis. Analysis of this data, if done carefully, can provide us with invaluable information regarding the personalised treatment of future patients.
-CANCER SUBTYPING AND PERSONALISED TREATMENT-
A decade or two back, diagnosis of cancer was made by analysing the pieces of the tumour under a microscope in a pathology lab[6]. And that was merely by looking at the sample, the related conclusions about the disease like cancer subtype, differentiation into malignant and benign, even judgement of its severity were made. It worked out for the most part but at the same time left much undiscovered. Now we know that cancer is a disease with implication at the cell and molecular levels. That is, now we know that it is caused by an aberration in the genes of the cells[7]. One noteworthy catch here is that there are hundreds and thousands of genes in a cell. Therefore, emphasising by reiterating my previous statement, there could be an enormous amount of combination of defects in genes which ultimately manifest into cancer. If that is the case, then can we not take each individual patient and see what all genes are having anomalies? Yes, there can be different sets of genes in different patients. But mostly they have intersections. 
With lowered cost of sequencing since the past two decades[8], it has been made possible to sequence a large amount of genome from the cancerous tissues right away and strictly interrogate the individual tumour in order to hunt for the abnormal genes which caused cancer to progress. Earlier it was a common conviction that the only way to treat the disease cancer is through clinical trial and error. But the generation of this large amount of sequencing data had made it possible to come up with a probable hypothesis for the cancer subtype discovery. 

-CANCER STATISTICS AND THE CURSE OF DIMENSIONALITY-
Once it was known that cancer is caused by the aberration in genes, the cancer diagnosis has turned from the tumour perspective to the molecular perspective. With lowered cost and ease of omic data generation for the cancerous cells, all the cancer databases are being overwhelmed by the unanalysed data. This brings along the common analytical problems with big data. One such problem is better illustrated as “The Curse of Dimensionality”[9]. Too many dimensions in the data lead to reduced accuracy in the results. Therefore, before analysing the data, for cancer subtyping in my case, a stable dimensionality is much needed. The term ‘stable’ here illustrates the structure of the data so that our algorithm could be able to discriminate the samples into subtypes.
Hence, with higher dimensions in the data is proportional to the fact that the true dimensions might be quite less than the observed dimensions as in the raw data. For the most part, this contention between the true dimensions and the observed dimensions is subjected to the correlation in the data. That is some features are proportional to each other. So one feature might be distorted to be another feature. Usually, the distortion is an invertible function. In our biological case,  gene expression can be linked based on their expression mechanisms. This phenomenon is called the genetic correlation. For example, there are many polygenic traits in humans. Let’s take height as a trait. Then, in broad terms, it can be stated that because the trait- height is governed by so many genes, there must be some other traits, say maximum running speed, which shows proportionality with the manifestation of height trait. So if we are analysing some data (not necessarily cancer data) which has a feature ‘Height’ and feature ‘Maximum speed’, then essentially both features are providing our machine learning model with the same information. In this way, you could have completely redundant information in your data and you might want to remove one of these features for computational gain. 
While the curse of dimensionality might affect your computational complexity but it is not the worst it does. In this project, I have made an attempt of dimensionality reduction with the aim of keeping the cluster information intact. Simply put, clustering is all about counting the classes in a region of space. Since it is the dimensions or the number of features which exhibits the space, that is why with the increase in dimensions the density of the classes  suspended in the space increases. In other words, given the number of samples and classes are the same, with the increase in dimensions, these samples get sparsely distributed across space. 
So in summary- my aim is to reduce the dimensionality of the cancer data ensuring that the subtype information remains intact. 


--EXISTING METHODS--
Dimensionality reduction is a well-studied field of data science. Some miscellaneous ways to reduce the dimensions of your data may be using your domain knowledge. If you know that ‘Height’ and ‘Maximum speed’ are correlated traits, then you can simply use just one of them and you will be one whole dimension down. Dimensionality reduction has to be done keeping as much structure in the data as possible so that the clustering model will be able to discriminate data in classes.
Dimensionality reduction methods can be classified into two broad processes.
FEATURE SELECTION: Picking out a subset of original dimensions and throwing away the rest.
FEATURE EXTRACTION: Constructing a new dataset altogether which may be some linear or non-linear combination of the original dataset.


-PRINCIPAL COMPONENT ANALYSIS-
All the dimensionality reduction algorithms based on PCA (Principal Component Analysis)[10] define a new set of dimensions such that about those dimensions, the data have a maximised variability. That will ensure that along the found dimensions, our data is spread out the most. It can be visualised as the rotation of axes about the origin so that all the correlated data becomes uncorrelated about the new rotated axes. For example, in the adjacent figure, green axes are the new rotated axes. These axes are called the Principal Components.


