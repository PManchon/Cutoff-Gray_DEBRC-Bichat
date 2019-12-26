# Cutoff-Gray_URC-Bichat
Determine an optimal cutpoint in presence of competing risks to categorize a continuous distribution. 

Function implementation in R software to determine an optimal cut-point for a continuous covariate with competing risks 

Main article: Giannelli V et al. Impact of cardiac function, refractory ascites and beta blockers on the outcome of patients with cirrhosis listed for liver transplan-tation. J Hepatol (2019) 
(https://doi.org/10.1016/j.jhep.2019.10.002) 


A first step consisted in the research of an optimal cut-point for the continuous covariate in presence of competing risks. We used maximally selected Gray’s statistic.

We worked with a primary event: death on the waiting list and a competing risk: transplantation, in a sample of 584 observations with 353 possible unique values of LVWSI, denoted Z.

For each possible value of the continuous covariate Z fixed µ, we calculated with k=74 times of death on the waiting list:

U_µ=∑_(i=1)^k▒(d_i^+-d_i^ ∙(r_i^(*+))/(r_i^* )) 
With:

	d_i^+: The number of deaths in the group Z > µ at the ith time
  
  d_i^ : The total number of deaths at the ith time
  
	r_i^(*+): The number at risk in the group Z > µ at the ith time & the number of patients in the group Z> µ which had observed the competing event before the ith time.
  
	r_i^*: The total number at risk at the ith time & the total number of patients which had observed the competing event before the ith time.
  

And we calculated the standardized statistic Q as:

Q_µ=U_µ/(σ√(D-1))

Where σ=√(1/(D-1)∙∑_(i=1)^D▒(1-∑_(j=1)^i▒1/(D+1-j))^2 ),
with D=102 the total number of deaths. 

Then, the optimal cut-point was determined by the maximum value of Q associated to the µ value: µ=64.1. 



