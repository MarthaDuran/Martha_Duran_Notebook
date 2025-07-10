# Molecular Networks

In this post, I'll briefly explain a method that helps analyze metabolic compounds, incorporating techniques such as chromatography and mass spectrometry. These analyses provide information aimed at identifying chemical compounds and their composition. This data can be integrated to create large datasets that are used to develop molecular networks. Molecular networking organizes complex MS/MS data by analyzing similar spectra and creates a visual map, where each dot (node) represents a molecule and the edges connect related ones. In this map, the edge label indicates Δm/z, which represents the difference in mass between the two spectra. These mass differences are considered to be **neutral losses**-small neutral or not ionized molecules that were potentially lost during the fragmentation. The analysis of these differences can help identify related compounds, such as derivatives or metabolites, support hypotheses related to chemical modifications, and annotate unknown compounds based on known molecular structures. 

---

## Step by step on generating a molecular network:

### Step 1: Log in to the GNPS dataset
You log into your account. If you don't have one, create an account using an email address and a password. 

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

**What do the negative numbers mean?**
In qPCR, lower Ct values represent higher expression of the gene of interest. This formula intends to transform the cycle difference into a biological meaning. A higher fold change represents increased gene expression.
 
---

## Example Calculation for the gene *foxA*

| Sample             | Tubulin Ct | foxA Ct | ΔCt |
|--------------------|------------|---------|-----|
| DMSO Control       | 23.30      | 24.37   | 1.07|
| Inhibitor Treatment| 22.72      | 23.72   | 1.00|

ΔΔCt = 1.00 - 1.07 = **-0.07**  
Fold Change = 2^0.07 ≈ **1.05**

This means *foxA* was expressed slightly more in the treated sample.

---

## Results

| Gene  | ΔCt control | ΔCt treated | ΔΔCt | Fold change |
|------|--------------|--------------|------|-------------|
| ascs | 5.80         | 5.79         | -0.01| 1.01        |
| Delta| 2.67         | 2.82         | 0.15 | 0.90        |
| ets  | 1.42         | 1.72         | 0.30 | 0.81        |
| foxA | 1.07         | 1.00         | -0.07| 1.05        |
| gcm  | 5.06         | 5.46         | 0.40 | 0.76        |
| NGN  | 5.06         | 4.63         | -0.42| 1.34        |
| opt  | 7.72         | 8.99         | 1.26 | 0.42        |
| pak3 | 2.11         | 2.58         | 0.47 | 0.72        |
| pak4 | 2.28         | 2.53         | 0.26 | 0.84        |
| pitx | 6.38         | 9.01         | 2.62 | 0.16        |
| SM30 | -2.33        | -0.95        | 1.37 | 0.39        |
| sm50 | 0.40         | 2.09         | 1.69 | 0.31        |
| soxC | 1.78         | 1.61         | -0.17| 1.12        |
| synB | 0.83         | 1.34         | 0.51 | 0.70        |

### Interpretation:
- The genes that have a fold change < 1 are **downregulated** in the treatment sample, like *pitx*, *sm50*
- The genes that have a fold change > 1 are **upregulated**, such as *NGN*, *foxA*




