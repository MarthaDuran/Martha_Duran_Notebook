# Calculating fold change in genes of interest with the ΔΔCt Method in qPCR

This post outlines the procedure for calculating the **fold change of gene expression** in the qPCR experiment, using the **ΔΔCt method**, as taught by Prashat.

---

## The method is the following:

### Step 1: Calculate ΔCt
ΔCt = Ct (Target gene) - Ct (Reference gene, Tubulin)

### Step 2: Calculate ΔΔCt
ΔΔCt = ΔCt (Treated) - ΔCt (Control)

### Step 3: Calculate Fold Change
Fold Change = 2^(-ΔΔCt)

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




