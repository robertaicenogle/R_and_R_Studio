# R and R Studio


## Statistical Analysis and Hypothesis Testing in R
### The basic process to analyze datasets using R:
- Extract, Transform, and Load (ETL) data
- Visualize the data
- Perform statisical tests, create regression models
- Interpret the results

### A Detailed Look Ahead
- Load, clean up, and reshape datasets using **tidyverse** in R.
- Visualize datasets with basic plots such as line, bar, and scatter plots using **ggplot2**.
- Generate and interpret more complex plots such as boxplots and heatmaps using **ggplot2**.
- Plot and identify distribution characteristics of a given dataset.
- Formulate null and alternative hypothesis tests for a given data problem.
- Implement and evaluate simple linear regression and multiple linear regression models for a given dataset.
- Implement and evaluate the one-sample t-Tests, two-sample t-Tests, and analysis of variance (ANOVA) models for a given dataset.
- Implement and evaluate a chi-squared test for a given dataset.
- Identify key characteristics of **A/B testing**.
- Determine the most appropriate statistical test for a given hypothesis and dataset.

# Getting Started with R
## 1.1 Introduction to R
### Benefits of R
- Versatile and extensible programming language with many benefits
- Scripts are written in plaintext
- Versions of plaintext files are easy to control using tools such as Git
- R analysis scripts (or RScripts) are highly reproducible and easy to share with peers and collaborators
- Process of loading in a dataset, visualizing the data, and performing statistical tests is straightforward and easy to interpret
- Many useful data transformation and modelling libraries, such as the tidyverse package, that simplify the process of ETL and visualizations

### RStudio Integrated Development Environment
- RStudio is an integrated development environment (IDE) used to help design and test RScripts
- RStudio provides users a graphical user interface (GUI) with multiple dynamic windows and perpetual access to their RScript and R console
- RStudio enables users to test their analysis scripts line by line while allowing users to view different environment variables and outputs
- This means that for each line of code written and executed, users can verify the results and troubleshoot any problems quickly and easily

## 1.2 Install R
- We must first install R before installing RStudio
  - This way, RStudio can easily find our R installation while being configured
  - Otherwise, we would have to manually tell RStudio where to find our installed applications

### Install R on macOS or Windows
- Navigate to R's Comprehensive R Archive Network (CRAN) server ([Link](https://cran.r-project.org/mirrors.html))
- Select a mirror link near our region
- After you navigate to a CRAN mirror site, you'll reach a self-explanatory download page
  - For those running a **macOS** environment, select the latest release .pkg file
  - For those running a **Windows** environment, click on the base installer link
- On the next page, click the "Download R for Windows" link to start downloading the installer

### Following Successful Download
- Once your installer files are successfully downloaded (.pkg for macOS or .exe for Windows), run them just as you would for any other installation program
  - Use all default install options and, if prompted, check all boxes to allow all R components to install.

## 1.3 Install R Studio
- Navigate to the RStudio Download Page ([Link](https://www.rstudio.com/products/rstudio/download/?utm_source=downloadrstudio&utm_medium=Site&utm_campaign=home-hero-cta#download))
- Select the most appropriate installer link
  - If you're using **macOS**, drag the RStudio application into your application folder
  - If you're a **Windows** user, run it through the installer as you would with any other Windows program
- Once you have R and RStudio installed, run RStudio for the first time, get acquainted with the software, and install our required packages

### Navigate and Configure RStudio
- Notice four panes laid out within the application window
  - The bottom-left pane contains the R console
  - The top-left pane contains your source, or (any RScripts, tables, and files you open within RStudio)
    - By default, RStudio will open an untitled RScript file in the pane
  - The top-right pane contains our environment objects, such as variables, functions, and data frames
  - On the bottom right is the multi-tool pane, which contains tabs for a file explorer, R documentation help, installed package list, and a plot viewing tool

### Install Required Libraries
- **tidyverse** ([Links to an external site.](https://www.tidyverse.org/)) simplifies the installation process for the most common data analysis packages in R
   - To install packages in our R environment, use the install.packages() function
- to install the tidyverse in our R environment, simply run the following command in the R console:
  - |  > install.packages("tidyverse")  |

### Install jsonlite
- To install jsonlite page, run the following in the R console:
  - |  > install.packages("jsonlite")  |
- When installing packages in R, be sure to wrap the package name in quotation marks, otherwise R will throw an error.

### Create a Working Directory Folder Structure
- Allow us to keep all of our RScripts and analysis results in a neat, organized structure
- Simplifies the process of reading in any external files into our R environment
- Follow these steps to create a working directory in R:
1. Make a folder on your computer called "R_Analysis," or whatever would help identify your R analysis and scripts folder.
2. In the R menu screen, go to Session, click Set Working Directory, then select Choose Directory
3. Navigate to the folder on your computer and select Open. 
   - If you click on the Files tab in your bottom-right multi-tool pane, notice that the folder now represents your active working directory
4. Now create a new folder in your active directory using the "New Folder" button. 
   - Once you have created the folder, press the refresh ( ) button to refresh the directory to see your new folder
5. Use the file pane and click on the folder to navigate within it. 
   - Within the file pane, click on More and select the Set As Working Directory option to make your this new folder your new working directory
   - To set a folder as your default working directory, go to Tools, Global Options, General, and specify the location of the folder
   - Feel free to make subfolders within your R_Analysis folder, but be sure to always change your working directory so your output tables and figures do not get lost

# Programming and ETL in R
## 2.1 Fundamentals of R Programming
Two fundamental components to programming in R are:
- Creating **data structures**
  - data structures store values and properties
  - most straightforward R data structures are **named values** and **vectors**
      - named values - single value that has been given a name
      - vectors - list of numbers are assigned a location and stored as a single data structure
  - To create our first data structure in R, we use an assignment statement
    - to create a named value x and assign it a value of 3, we would use this R command:
      - | > x <- 3 |
    - The **assignment operator (<-)** tells R to assign whatever is right of the arrow to the name that is left of the arrow
    - The named value should appear in your environmental pane
  - In R, all environment objects are mutable, which means they can be assigned and reassigned multiple times.
  - Another simple data structure in R is the **numeric vector**
    - A numeric vector is an ordered list of numbers
      - To create a numeric vector, we use the c()function
        - Use the following command to assign the numeric vector, numlist, into the environment:
          - | > numlist <- c(0, 1, 2, 3, 4, 5, 6, 7, 8, 9) |
  - R also supports a number of more advanced data structures such as **matrices**, **data frames**, and **tibbles**
    - all of which are variations of the same data frame concept
      - A matrix can be thought of as a vector of vectors, where each value in the matrix is the same data type
      - A data frame is very similar to a Pandas DataFrame where each column can be a different data type
      - A tibble is a recent data object introduced by the tidyverse package in R and is an optimized data frame with extra metadata and features

- Using **functions**
  - functions perform operations

- More advanced R data structures can refer to the [R Introduction documentation](https://cran.r-project.org/doc/manuals/r-release/R-intro.pdf)

## 2.2 Functions in R


## 2.3 Read and Write Using R


## 2.4 Select Data in R


## 2.5 Transform, Group, and Reshape Data Using the Tidyverse Package


# Visualize Your Data Using ggplot2
## 3.1 Introduction to ggplot2


## 3.2 Build a Bar Plot in ggplot2


## 3.3 Add Formatting Functions


## 3.4 Build a Line Plot in ggplot2


## 3.5 Create Advanced Boxplots in ggplot2


## 3.6 Create Heatmap Plots


## 3.7 Add Layers to Plots


# Introduction to Statistical Tests
## 4.1 Identifying Statistical Test Types


## 4.2 Identify Different Data Types


## 4.3 Dive Into Distributions


## 4.4 Test for Normality


## 4.5 Understand Skew


# Introduction to Hypothesis Testing
## 5.1 Practice Hypothesis Testing


## 5.2 Assess Error in Hypothesis Testing


# Perform an Analysis of Means in R
## 6.1 Sample Versus Population Dataset


## 6.2 Use the One-Sample t-Test


## 6.3 Use the Two-Sample t-Test


## 6.4 Use the Two-Sample t-Test to Compare Samples


## 6.5 Use the ANOVA Test


# Correlation and Regression in R
## 7.1 The Correlation Conundrum


## 7.2 Return to Linear Regression


## 7.3 Perform Multiple Linear Regression


# Characterize Categorical Data
## 8.1 Category Complexities


# Getting Real With A/B Testing
## 9.1 Practice A/B Testing


# Choose the Right Test for Your Data
## 10.1 Whose Analysis Is It Anyway?
