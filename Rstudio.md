# Downloading and Installation of RStudio in linux
The following is a description of how I downloaded and installed Rstudio in my new desktop with Ubuntu 20.04

## Get pre-requisites
```
$ sudo apt update
$ sudo apt -y install r-base gdebi-core
```
## Download \*.deb file
Go the Rstudio site [https://www.rstudio.com/products/rstudio/download/#download] and download "rstudio-2021.09.1-372-amd64.deb" (or any other appropriate version into your desktop (Downloads folder)

## Installation
Go to the Downloads folder from the home directory and install Rstudio using the following commands
```
$ cd Downloads
$ sudo gdebi rstudio-1.2.5019-amd64.deb
```
## Check
Select the Rstudio from Applications and click to see if a new window with Rstudio opens
