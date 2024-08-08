# Creating-your-own-basic-ATS-with-Excel

Applicant Tracking Systems (ATS) are the cornerstone of recruitment in modern HR departments, as they easily provide an overview of what stage the candidate is in during the recruitment process, something especially important as recruiters tend to create pipelines of multiple concurrent individuals. 

However, most companies need to rely on external pieces of software to use as ATS, that are costly and tend to suck up ludicrous and often indispensable amounts of money that businesses sometimes cannot afford, like in the case of a start-up with restricted starting capital or a smaller business with other investment priorities. 

Thankfully, Microsoft Excel, a versatile, albeit subscription-based, tool can act as a useful alternative, as it offers database and data analysis capabilties, similiar to other modern ATS in a fraction of the price. 

**Our database**

The attached Excel database serves as an unofficial ATS that can be used as a substitute to other established ATS. Despite the fact that it might not be an exact competitor of other more expensive pieces of software, as mentioned before, the beauty of excel lies in its' versatility: if one feature is missing, there would be a close-enough mark-up for that, depending on the user's proficiency of course. The following ATS has been constructed in accordance to what has been necessary for me so far in my work, as a testament of what i have encountered. Therefore, impressions might differ. 

Starting off, Position titles, upload date, required seniority level, lookout department, required experience and some social media analytics (N of people viewed and suitable applicants) are given. Besides posotion title and upload date and the analytics, other fields were data validated, so as to have pre-filled options that automated a significant amount of manual work. Then of course, applicant information is filled manually, which would make sense as you cannot have these options as a list. This is not valid for the recruiter column, nevertheless, as there is a predetermined number of recruiters. 

The stage column describes the current stage the candidates are in and how far they have progressed in the recruitment procedure in a given point in time, more static in that sense. There is also room for CV comments and the panes are freezed just at the candidate's name, so that the recruiter doesn't have to go back and fourth. 

Conditional formatting has been applied to all results columns, so that it can be even more intuitive. These columns are simultaneously data validated. Special mention to the results column, where instead of Data validation, the following function was used: 
  =IF(W13=""; ""; IF(W13<0,5; "Failed - Inexperienced"; IF(W13<=0,7; "Passed-Experienced"; IF(W13<=0,89; "Passed- Very Experienced"; "Passed- Exceptional")))). 

Then, conditional formatting would highlight green a cell that contained the word "Passed" in any way, and the opposite for the word "Failed". 

You might have noticed that we skipped the first column. This is because there is a function there as well: 
  =IF(COUNTIF(AA4:AA14; "Hired") > 0; "Closed"; "Open")
Basically, if there is the Hired word in the relevant column, the positions flips to closed automatically, futher saving time and ensuring the recruiter does not forget anything. 

**Making the information presentable**

Presenting our monthly recruiting activites would require Pivot Tables in Excel and Power BI (Power BI alone could pull it off in any case). 

Our Power BI file shiftly presents the amount of individuals that progressed through each stage and where we are currently at in the process. It also breaks down hiring by recruiting agent, which could then be easily used to identify accordance with various KPIs. 
