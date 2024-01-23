# DRGEXCOBRA
DNA repair gene expression correlation with TFAP2B in BRCA data


---
title: "Dr. Gex Cobra"
author: "SanghoonLee"
date: "2024-01-23"
output: 
  html_document: default
pdf_document: default
---
  <span style="color:red">**D**</span>NA <span style="color:red">**r**</span>epair <span style="color:red">**G**</span>ene <span style="color:red">**ex**</span>pression <span style="color:red">**Co**</span>rrelation in <span style="color:red">**br**</span>east c<span style="color:red">**a**</span>ncer (Dr. Gex Cobra) was built on R version 4.3.1 (2023-06-16) -- "Beagle Scouts"  This means you need to install R version >= 4.3.1
DRGEXCOBRA was tested on both Windows and Mac environment.


## A. Instruction 
DRGEXCOBRA is a tool to visualize the correlation of DNA repair gene and your interst gene expression in breast cancer subtypes 

This is an instruction to explain how to use DRGEXCOBRA. Considering your computer programming skills, I made a R package to minimize your computer work and coding. Here are brief overview to use DRGEXCOBRA.

## B. Basic requirements

### Step1. Download R and Rstudio, and install them. 
You can just google for **"R download and install"** and **"Rstudio download"** to complete this step. If you have some experience already,

You can install R from CRAN: https://cran.r-project.org/
  
  You can install a user-friendly interface, R-Studio, from here: https://www.rstudio.com/products/rstudio/download/
  
  If you want to learn more in structure or if you got stuck, before asking me, visit https://hsls.libguides.com/video_intro2R There are a video lecture, ppt slides, and whole basic explanation.

### Step2. Start Rstudio
What does 'start Rstudio' mean? Visit the lecture I introduced in Step1.

### Step3. In the R console, install necessary R packages and install DRGEXCOBRA. 
What are 'R console' and 'R package'? The lecture video I introduced in Step1 will explain everything.

Simply, run these code lines in your R console. Just copy the lines, paste them to console, and hit enter key.

```{r}
# Install and load multiple packages at a time.  This will take 10~15 min if you are installing any packages for the first time.
install.packages(c("devtools","usethis","pacman","data.table","dplyr","tidyr","ggplot2","ggpubr","purrr","shiny"), repos="http://cran.us.r-project.org")
pacman::p_load(devtools,usethis,pacman,data.table,dplyr,tidyr,ggplot2,ggpubr,purrr,shiny)
```
![InstalldevtoolsPackage](https://github.com/leeoesterreich/DRGEXCOBRA/assets/87338488/bd7864ca-39d7-460f-b378-c06ae45b9c98)

### Step4. Download DRGEXCOBRA R package file from Pitt OneDrive
I couldn't store DRGEXCOBRA R package to the lab Github because METABRIC and SCAN-B data file sizes are too big, 218 Mb and 375 Mb. Github doesn't allow to upload a big size file > 25 Mb.

Therefore, I made R package .zip file and stored it at the lab Pitt OneDrive. Click [here](https://pitt-my.sharepoint.com/:f:/r/personal/avleelab_pitt_edu/Documents/Lee-Oesterreich%20Lab/Lee-Oesterreich%20General%20Lab%20Items/Bioinformatics_Basics_And_Scripts/08_DRGEXCOBRA?csf=1&web=1&e=Fcy1dl) or go to 

**Lee-Oesterreich lab > Lee-Oesterreich General Lab Items > Bioinformatics_Basics_And_Scripts > 08_DRGEXCOBRA**

Download "DRGEXCOBRA_0.0.0.9000.tar.gz" (650 Mb). It takes long due to the file size. Store the .tar.gz file to your local computer, but you don't need to untar the file. For example, I stored it at "..../H45_ShinyApp_METABRICSCANB_TROP2" (screenshot below)

**Mac users:** Mouse right click on "GEXPLORER_0.0.1.1.tar.gz" file and click "Get Info." Drag the folder address and click Command+C (screenshot below)
Window users: You can copy the address in Windows Explorer.

![DownloadDRGEXCOBRA](https://github.com/leeoesterreich/DRGEXCOBRA/assets/87338488/a4a77818-bc0a-444d-9057-a51718630e8d)

### Step5. Install DRGEXCOBRA R package
In the R console, let's change your working directory to the folder you stored "DRGEXCOBRA_0.0.0.9000.tar.gz" The code line should be like this. Look at the screenshot below. 

setwd("/DirectoryAddress/YouCopied/FromGetInfo)    # setwd means set Working Directory. 

**Windows users:** When you copy and paste your address in your R code, the folder split is backslash like this, "\user\MyFolder\" You should revise it to slash. R doesn't understand backslash. e.g. setwd(/user/MyFolder/")
```{r}
## Let's change your working directory to the folder you stored "DRGEXCOBRA_0.0.0.9000.tar.gz" file. Note you need quotation inside parenthesis, like setwd("YourFolderAddress")
setwd("/Users/sanghoonlee/Library/CloudStorage/OneDrive-UniversityofPittsburgh/H45_ShinyApp_METABRICSCANB_TROP2")

## Install DRGEXCOBRA This takes 2~5 min depending on your computer spec.  Note you need quotation outside the file name. 
install.packages("DRGEXCOBRA_0.0.0.9000.tar.gz")

## Load your DRGEXCOBRA package. Note you DON'T need quotation. The package name is DRGEXCOBRA, not DRGEXCOBRA_0.0.1.1.tar.gz
library(DRGEXCOBRA) 
```
![InstallDRGEXCOBRA](https://github.com/leeoesterreich/DRGEXCOBRA/assets/87338488/3f4b110d-6243-476e-9d15-196037759c23)

</br>
  
  Once you install DRGEXCOBRA package one time, you don't need to install it again when you restarted your R session. Just you need to load DRGEXCOBRA 

> library(DRGEXCOBRA)


## C. Play with DRGEXCOBRA

Copy the code line below and run it in your R console. 

```{r}
## DRGEXCOBRA. It takes about 10 seconds to start a ShinyApp depending on your computer spec.
shinyApp(ui=UserInterface, server=ShinySever)
```

For now, you should choose a gene of DNA repair in the Gene Query box. You can't type in your gene of interest. 

![ShinyAppDRGEXCOBRA](https://github.com/leeoesterreich/DRGEXCOBRA/assets/87338488/242aaf88-c758-49d4-aa0d-3c6bbfe5877a)



