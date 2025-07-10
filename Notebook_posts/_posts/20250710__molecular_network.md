# Molecular Networks

In this post, I'll briefly explain a method that helps analyze metabolic compounds, incorporating techniques such as chromatography and mass spectrometry. These analyses provide information aimed at identifying chemical compounds and their composition. This data can be integrated to create large datasets that are used to develop molecular networks. Molecular networking organizes complex MS/MS data by analyzing similar spectra and creates a visual map, where each dot (node) represents a molecule and the edges connect related ones. In this map, the edge label indicates Δm/z, representing the mass difference between the two spectra. These mass differences are considered to be **neutral losses**-small neutral or not ionized molecules that were potentially lost during the fragmentation. The analysis of these differences can help identify related compounds, such as derivatives or metabolites, support hypotheses related to chemical modifications, and annotate unknown compounds based on known molecular structures. 

---

## Step by step on generating a molecular network:

### Step 1: Log in to the GNPS dataset
You log into your account. If you don't have one, create an account using a valid email address and a secure password. 

### Step 2: Create a Molecular Network
You can scroll down the main page until you see a menu with several options. Click on 'Create molecular network', placed within the 'Molecular Networking' section.

### Step 3: Create a job
Create a suitable name for the job analysis. Load your data in the section 'Basic options'. Click on 'Select Input Files', next to the 'Spectrumc Files (Required) option.  In the pop-up window, go to the 'Share files' section. Write the code of the dataset in the 'Import Data Share' section. Today I used the 'MSV000088759' dataset. Once it is imported, the dataset must be loaded by clicking the 'Select Input Files' section. The files are found in the 'peak' folder and must be selected and added as input files by clicking on the 'Spectrum files G1' button. 

### Step 4: Submit and wait
Once the files are loaded, enter your email address and click the 'Submit' button. The job will start, and it should take around 30 minutes. 

### Step 5: Visualize the results
Once the job is ready, click on the 'View All Clusters With IDs' link in the 'Default Molecular Networking Results Views' section.

### Step 6: Find a cluster of interests
You can just navigate through the database and select a cluster of interest. In this case, the 'Etoposide' was selected, belonging to the 2236 cluster. To open the map, click on 'View Network'

### Step 7: Analyzing the network

![Molecular Network Overview](https://github.com/MarthaDuran/Martha_Duran_Notebook/blob/3914e5e786b090ad36c2e254695d57283c0ae34e/Notebook_posts/images/network_overview.png)

This is the network we are working on today. Each dot represents different compounds in the database, where the blue one corresponds to Etoposide, with a parent mass of 589.191. The other compound we will focus on is the one with a molecular mass of 606.218. The lines represent the existing similarities between them, and the number above the line indicates the Δm/z. In this case, it is 17.027. 

UNIMOD is a publicly available online database for identifying compounds based on their mass spectra. According to it, a mass of 17.026, which is close to the number in our network, corresponds to Ammonium. Since the delta between Etoposide and the unknown compound is positive, we can assume that the new compound may contain Ammonium. 

 If we look at the peaks,
 ## Etoposide
 ![Etoposide](https://github.com/MarthaDuran/Martha_Duran_Notebook/blob/8229fd08dda2bf7bef616edb93a6c4026e71e7e8/Notebook_posts/images/etoposide_peaks.png)

## Unknown compound
 ![Unknown compound]()

Both spectra exhibit peaks at 165.046 and 229.046, which support the similarities between these two compounds. Since the unknown compound also contains the main peak, we can assume the unknown compound is a derivative of Etoposide. If we incorporate this information with the delta previously described, this new fragment may have an extra amine group, or this compound may have lost ammonia during the fragmentation. 

## What is Etoposide?
Etoposide is a chemotherapy agent used to treat different types of cancer by interrupting cell division. 
