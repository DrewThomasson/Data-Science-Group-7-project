# Complaint findings and dead ends for the presentation

**Drew Thomasson · Group 7 · DSCI 3780**

## The finding to lead with

**How much of the late-response gap was concentrated under two company labels?** In the same 11 full months, November 2025 through September 2026, **24.3%** of published federal student loan debt collection complaints were marked late, compared with **1.4%** of credit card debt collection complaints. The measure is **Timely response? = No**.

**147 of 164** late student-loan responses were recorded under **MOHELA** or **“Servicer under contract with Federal Student Aid.”** When we leave those same entries out of both datasets as a check, the rates are **3.35%** and **1.33%**. The generic label doesn't identify a specific servicer. Say the gap was **concentrated under two labels**. The analysis shows an association and leaves the reason for the late responses open.

[Chart to drop into the slides](Late_Response_Gap.png) · [Notebook with calculations and follow-up checks](Federal_Student_Loan_Debt_Complaints.ipynb)

## Dead ends and oddities worth mentioning

| What we checked | What we found | What to say to the group |
| --- | --- | --- |
| **Which file is bigger?** | The original student-loan export has **730** rows. The credit card export has **35,912**, about **49 times as many**. | A combined raw count would mostly tell the credit card story. We compare percentages within each debt type and show the denominators. |
| **Did the public response field explain anything?** | In the student-loan file, **621** public response values were `None`, and **87** explicitly said the company chose to provide no public response. That leaves **22** rows with any other public response label. Of the 621 `None` rows, **424** were *Closed with explanation* in the separate consumer response field. | `None` means no public label was recorded. The opt-out text is an explicit selection. A company can send an explanation to the consumer while its optional public field is blank, so keep both raw values. [CFPB field definitions](https://www.consumerfinance.gov/complaint/data-use/) |
| **Did the complaint prove the debt was wrong?** | **342 of 730** student-loan complaints reported attempts to collect debt the consumer said they didn’t owe. The CFPB says its complaint process does not verify the allegations. | We can see which issues consumers reported and how recorded outcomes varied across company labels. We can’t determine whether the debt was owed or whether the consumer’s account was accurate. [CFPB statement on verification](https://www.consumerfinance.gov/about-us/newsroom/the-cfpb-to-cease-discretionary-publication-of-complaint-narratives-and-visualizations/) |
| **Did “Untimely response” catch every late reply?** | **161** student-loan complaints had that exact outcome. The separate flag marked **171** as late, including **10** closed with an explanation. | Use the flag when asking about the deadline. Use the outcome field when describing how the complaint was categorized. |
| **Did one issue explain the gap?** | Restricting both files to the same top issue still gave **25.86% vs. 1.27%** marked late. Leaving out the two labels within that issue narrowed it to **1.68% vs. 1.11%**. | The headline gap persisted when we looked at the same complaint topic. The company-label concentration persisted too. |
| **Was one month behind it?** | The generic Federal Student Aid label appeared in **all 11 months** on the student-loan side. Across both files, **128 of 128** complaints under that label were marked late. | The pattern repeated across months. The public label gives us no way to identify the specific servicer or determine how that label was assigned. |
| **Could we compare web, phone, and mail?** | **707 of 730** student-loan complaints came through the web. Only **23** were split across postal mail, phone, and referrals. | The other groups were too small for a strong comparison. One phone complaint would change the phone rate by about 14 percentage points. |
| **Could we say much about monetary relief?** | Just **one** of 730 student-loan complaints was closed with monetary relief. Among complaints about debt the consumer said they didn’t owe, **22** were closed with non-monetary relief. | One case is too little for a pattern. Non-monetary relief means the company reported taking action without paying the consumer. The CSV gives no case details about the action. [CFPB response category definitions](https://files.consumerfinance.gov/f/documents/cfpb_2025-cr-annual-report_2026-03.pdf) |
| **Was the second copy of the student-loan data useful?** | It had the same **730 complaint IDs**, plus **730 empty records** and **45 ZIP codes** that had lost leading zeros. | We used the shared project CSV and read ZIP codes as text. Stacking the two copies would count the same complaints twice. |

## Three slides or talking points

1. **What we compared.** One row is a published complaint. Both datasets cover debt collection. Show the two sample sizes and the shared date window.
2. **What surprised us.** Show the late-response chart. Say that 147 of 164 late student-loan responses were recorded under two company labels.
3. **What we checked.** The pattern persisted within the same issue and across months. Use the public-response blanks or the two timeliness fields as a quick example of why field definitions matter.
