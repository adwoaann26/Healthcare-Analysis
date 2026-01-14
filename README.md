# Healthcare-Analysis
Overview
This report provides a comprehensive analysis of the medical claims process. It highlights key trends, approval rates,
and claim amounts, with a focus on identifying inefficiencies and opportunities for improvement.

Through visual data representation, the presentation aims to:
Showcase trends in claim amounts and approval rates across different claim types and diagnoses.
Provide insights into the distribution and variability of claim approvals by source and diagnosis.
Highlight key findings regarding the performance of the claims process.
Offer actionable recommendations to streamline the claims process and improve overall efficiency and effectiveness.

# Data Preparation
Tools Used: Excel And PowerBi

# Missing Data:
The source from Pharmacy lacked: ICD-10 Codes, Diagnosis, Date of Diagnosis
Action Taken: Left missing ICD-10 codes and diagnoses with Blank as it affected the whole pharmacy source
Updated the currency column for consistency

# Negative Claim Amounts:
Found 2 entries with claim amounts of -1 and -2.
Status: Declined; no impact on overall analysis.
Action Taken: Record was deleted

# Date Corrections:
4 dates identified as incorrect.
Action Taken: Corrected based on trend analysis to maintain data integrity.
Assigned the right Data types for each column

# Calculations
TotalClaims = COUNTROWS(Claims)
Total Claim Amount = SUM(Claims[Claim Amount])
Total Approved Claim Amount = SUM(Claims[Approved Claim Amount])
StDevClaimAmount = STDEV.P(Claims[Claim Amount])
StDevApprovedClaimAmount = STDEV.P(Claims[Approved Claim Amount])
MedianClaimAmount = MEDIAN(Claims[Claim Amount])
MedianApprovedClaimAmount = MEDIAN(Claims[Approved Claim Amount])
MeanClaimAmount = AVERAGE(Claims[Claim Amount])
MeanApprovedClaimAmount = AVERAGE(Claims[Approved Claim Amount])
DiagnosisCount = COUNT('Claims'[Diagnosis])
ApprovalRate = DIVIDE(SUM(Claims[Approved Claim Amount]), SUM(Claims[Claim Amount]), 0)

# Key Findings
Seasonal Trends: The peaks in December for 2022 and 2013 suggest a seasonal pattern, possibly due to policy renewals,
fiscal year-end activities, or seasonal incidents. However in 2024, it maintained peaks from January to march until it started
to decline.

Stable Mid-Year: The stable claim amounts from March to October indicate a more predictable and manageable workload
during these months.
