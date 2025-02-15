<img src="https://img.shields.io/github/license/liuzan-info/PhosMap">

# PhosMap
A docker image-based tool to accomplish one-stop interactive analysis of quantitative phosphoproteomics.
<img src="www/main.svg" width = 70%>

## Brief Description
PhosMap supports multiple function modules for full landscape of 
phosphoproteomics data analyses including quality control, phosphosite 
mapping, dimension reduction analysis, time course analysis, kinase 
activity analysis and survival analysis. Various of publication ready 
figures and tables could be generated via PhosMap. We provided a downloadable
R package for local customized analysis of massive data in the R shiny environment
deploying on the Docker upon the Windows, Linux, and Mac system.


We provide a demo server at https://bio-inf.shinyapps.io/phosmap/. 
This server is single-thread and of low-level hardware, we do recommend
users to analyze the data using the demo server with small data sets. 
An upgraded hardware is necessary, according to the possible computational
cost of the data, to reach the potential of PhosMap.

## How to install
There are two different ways to launch PhosMap:
### 1. Docker-based installation
We provide a docker image with PhosMap: https://hub.docker.com/r/liuzandh/phosmap

Pull the docker image of PhosMap:
```linux
docker pull liuzandh/phosmap:0.1
```
Create a docker container containing PhosMap:

```linux
docker run -p HostPort:8787 -e PASSWORD=123456 liuzandh/phosmap:0.1
```
Then, you can enter PhosMap by visiting HostIP:HostPort. Username is "rstudio", Password is "123456". For example: HostPort could be set to 5907. This parameter can be changed according to user needs. 
such as,
```linux
docker run -p 5907:8787 -e PASSWORD=123456 liuzandh/phosmap:0.1
```
Next, open 127.0.0.1:5907 in the local browser or remotely access ip:5907 (you should ensure that the machine can be accessed remotely).

### 2. R-based installation
This tool is developed with R, so if you want to run it locally, you may do some preparatory work:
- [1] **Install R.** You can download R from here: https://www.r-project.org/.
- [2] **Install RStudio.** You can download RStudio from here: https://www.rstudio.com/.
- [3] **Download the source code from github.**
- [4] **Download the necessary data.** Please download "PhosMap_datasets.zip" from module "Download" on https://bio-inf.shinyapps.io/phosmap/. Then unzip this file to phosmap folder like this pic.
  <img src="www/unzip.jpg" width=30%>
- [5] **Check packages.** After installing R and RStudio, you should check whether you have installed these packages ("shiny","shinyjs","shinyBS","shinyWidgets","ggplot2","ggrepel","plotly","colourpicker","ggseqlogo","pheatmap","survminer","survival","zip","stringr","readr","dplyr","DT","png","svglite","ggplotify","bslib","ksea","rmotifx","PhosMap","qpdf","pcaMethods","impute","rrcovNA","e1071"). 
  You can run the codes below to install them:
  ```linux
  if (!require("BiocManager", quietly = TRUE)){install.packages("BiocManager")}

  BiocManager::install(c("pcaMethods", "impute"))

  install.packages(c("shiny","shinyjs","shinyBS","shinyWidgets","ggplot2","ggrepel","plotly","colourpicker","ggseqlogo","pheatmap","survminer","survival","zip","stringr","dplyr","DT","png","svglite","ggplotify","bslib","qpdf", "rrcovNA", "e1071"))

  install.packages('devtools')
  require(devtools)

  install_github('evocellnet/ksea')
  install_github('omarwagih/rmotifx')
  install_github('ecnuzdd/PhosMap')
  ```
- [6] **click "Run App".** View the file ui.R, then just click button "Run App", Phosmap will start.

## Detail of R package "PhosMap"
https://github.com/ecnuzdd/PhosMap

## Friendly suggestion
1. Open PhosMap with Chrome.
2. The minimum operating system specifications are: RAM 8GB, Hard drive 100 GB.

## Reporting issues
You could push an issue on this github if you have any problems.
