# Funding Sources and Congressional Voting Patterns
*Data Dictionaries*

## Table of Contents
1. [Party Codes](#party-codes)
2. [Cast Codes](#cast-codes)
3. [Members](#members)
4. [Votes](#votes)
5. [Roll Call](#roll-call)
6. [Bills Dime](#bills-dime)
7. [Candidates](#candidates)
8. [Committees](#committees)
9. [Funding Sources](#disbursements-receipts-expenditures)


#### Voteview Datasets

###### Party Codes
1. Party_Code -- INTEGER
    - Unique id for all U.S political parties
2. Party_Name -- TEXT
    - Long-form text name of U.S. political parties

###### Cast Codes
1. Cast_Code -- INTEGER
    - Numerical representation of vote responses
2. Description -- TEXT
    - Long-form text description of vote responses
3. Simplified_Grouping -- TEXT
    - Self-defined grouping of all 10 possible responses into Yea, Nay, Present, or Abstain

###### Members
1. Chamber -- TEXT
    - House or Senate
2. ICPSR_ID -- INTEGER
    - Unique id for all U.S. elected officials used by Voteview
3. District -- TEXT
    - The U.S. district the congressperson represents
4. State -- TEXT
    - The U.S. state the congressperson represents
5. Party -- INTEGER
    - The party code of a congressperson 
6. Name -- TEXT
    - The name of the elected official
7. Congress_ID -- TEXT
    - The unique id of all elected officials as represented on government websites
8. Nominate_Dim1 -- REAL
    - The estimated placement of a congressperson along the first dimension of the NOMINATE scale. This dimension (often represented along the x-axis) corresponds to the left-right or liberal-conservative spectrum on economic matters.
9. Nominate_Dim2 -- REAL
    - The estimated placement of a congressperson along the second dimension of the NOMINATE scale. This dimension (often represented along the y-axis) corresponds to social, salient issues of the time, such as civil rights, abortion, gun rights, and so on.

###### Votes
1. ICPSR_ID -- INTEGER
    - Unique id for all U.S. elected officials used by Voteview
2. Cast_Code -- INTEGER
    - Numerical representation of vote responses
3. Rollnumber -- INTEGER
    - Serial id of roll call vote that begins at 1 the start of every new congressional session
4. Prob -- REAL
    - Estimated probability, based on NOMINATE, of the member making the vote as recorded

###### Roll Call
1. Rollnumber -- INTEGER
    - Serial id of roll call vote that begins at 1 the start of every new congressional session
2. Date -- TEXT
    - Date a roll call vote took place
3. Session -- INTEGER
    - Either 1 or 2, corresponding to which session of congress the vote took place during
4. Yea_Count -- INTEGER
    - The number of votes in favor of a decision
5. Nay_Count -- INTEGER
    - The number of votes against a decision
6. Nominate_mid_1 -- REAL
    - First-dimension midpoint estimate based on the Nominate scale
7. Nominate_mid_2 -- REAL
    - Second-dimension midpoint estimate based on the Nominate scale
8. Nominate_spread_1 -- REAL
    - First-dimension spread estimate based on the Nominate scale
9. Nominate_spread_2 -- REAL
    - Second-dimension spread estimate based on the Nominate scale
10. Bill_number -- TEXT
    - Unique id of the bill
11. Vote_Result -- TEXT
    - Official result of the roll call
12. Vote_Desc -- TEXT
    - Description of the roll call as assigned by Congressional staff
13. Vote_Question -- TEXT
    - Question addressed by the roll call
14. Issue_Codes -- TEXT
    - Poole and Rosenthal specific issue codes.
15. Peltzman_Codes -- TEXT
    - Peltzman (1984) issue-area codes.
16. Clausen_Codes -- TEXT
    - Clausen (1973) issue-area codes.
17. CRS_Policy_Area -- TEXT
    - Congressional Research Service policy area.
18. CRS_Subjects -- TEXT
    - Congressional Research Service subject area.
19. Congress_url -- TEXT
    - Link to the bill description on congress.gov 

#### Stanford DIME PLUS Datasets

###### Bills Dime
1. Bill_ID -- TEXT
    - Unique id of the bill
2. Year -- INTEGER
    - Year roll call vote took place
3. Date -- TEXT
    - Date roll call vote took place
4. Bill_Desc -- TEXT
    - Description of the bill
5. Sponsors -- TEXT
    - Congressperson that sponsored the bill
6. Cosponsors -- TEXT
    - Additional sponsors of the bill
7. TW_Latent1 -- REAL
    - Topic weight for the latent category calculated by the authors of the DIME PLUS repository. All below columns are the topic weight calculations for their corresponding header name.
8. TW_Abortion_and_Social_Conservatism -- REAL
9. TW_Agriculture -- REAL
10. TW_Banking_and_Finance -- REAL
11. TW_Civil_Rights -- REAL
12. TW_Congress_and_Procedural -- REAL
13. TW_Crime -- REAL
14. TW_Defense_and_Foreign_Policy -- REAL
15. TW_Economy -- REAL
16. TW_Education -- REAL
17. TW_Energy -- REAL
18. TW_Environment -- REAL
19. TW_Fair_Elections -- REAL
20. TW_Federal_Agencies_and_Gov_Regulation -- REAL
21. TW_Guns -- REAL
22. TW_Healthcare -- REAL
23. TW_Higher_Education -- REAL
24. TW_Immigration -- REAL
25. TW_Indian_Affairs -- REAL
26. TW_Intelligence_and_Surveillance -- REAL
27. TW_Labor -- REAL
28. TW_Law_Courts_and_Judges -- REAL
29. TW_Transportation -- REAL
30. TW_Veterans_Affairs -- REAL
31. TW_Womens_Issues -- REAL

#### Federal Election Commission Datasets

###### Candidates
1. Candidate_ID -- TEXT
    - Unique id from the FEC of all candidates who run for office in the U.S.
2. Status -- TEXT
    - Whether or not a candidate is statutory, or in the future/past
3. District -- INTEGER
    - Corresponding district a candidate is running for election in
4. Has_Raised_Funds -- BOOLEAN
    - Whether a candidate has received funds or not
5. Incumbent_Challenge -- TEXT
    - Whether a candidate is an incumbent or challenger
6. Name -- TEXT
    - Name of candidate
7. Office -- TEXT
    - House, Senate, or Presidency
8. Party -- TEXT
    - U.S. Political Party candidate is running under
9. Committees -- LIST OF DICTIONARIES
    - This contains all the committee ids a candidate is associated with. Needs considerable cleaning at this time.
10. State -- TEXT
    - Corresponding state a candidate is running for election in

###### Committees
1. Affiliated_Committee_Name -- TEXT
    - Affiliated organization name (such as the company or association)
2. Committee_ID -- TEXT
    - Unique ID from the FEC for committees that donate to federal election candidates and/or expend funds for election purposes
3. Committee_Type -- TEXT
    - Type of committee, such as PAC or Political Party
4. Designation_Type -- TEXT
    - Subcategory type of committee such as Lobbyist PAC
5. Name -- TEXT
    - Name of the committee as registered with the FEC
6. Organization_Type -- TEXT
    - Type of the affiliation organization
7. State --    TEXT
    - Location the committee is registered in

###### Disbursements, Receipts, Expenditures
** These datasets are not yet clearly defined at the time of the project plan. 
