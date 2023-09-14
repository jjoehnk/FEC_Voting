# Funding Sources and Congressional Voting Patterns
*Data Dictionaries*

## Table of Contents
1. [Party Codes](#party-codes)
   - U.S. political parties and the short-hand code used in other tables
2. [Cast Codes](#cast-codes)
   - Roll call cast codes used in Congress and their descriptive meaning
3. [Members](#members)
   - Members of the U.S. House of Representatives, with basic descriptive and electoral funding details
4. [Votes](#votes)
   - Roll call votes by bill and member
5. [Roll Call](#roll-call)
    - Bills put forth by the House of Representatives, with categorical descriptions and nominate scales
6. [Bills Dime](#bills-dime)
    - Alternative table of bills put forth that are weighted by subject matter occurence
7. [Committees](#committees)
    - Electoral committees registered through the Federal Electoral Commission active in the 2011-2012 election cycle
8. [Disbursements](#disbursements)
   - Detail of money spent by committees (shows where funds donated to third-party arms connect to electoral candidates)
9. [Receipts](#receipts)
    - Detail of money received by electoral candidates
10. [Expenditures](#expenditures)
    - Detail of funds spent by third-party arms such as Super PACs that were spent in support or opposition of a candidate but not given directly to the individual or their associated committee


#### Voteview Datasets

###### Party Codes
1. party_code -- INTEGER
    - Unique id for all U.S political parties
2. party_name -- TEXT
    - Long-form text name of U.S. political parties

###### Cast Codes
1. cast_code -- INTEGER
    - Numerical representation of vote responses
2. description -- TEXT
    - Long-form text description of vote responses
3. simplified_grouping -- TEXT
    - Self-defined grouping of all 10 possible responses into Yea, Nay, Present, or Abstain

###### Members
1. icpsr -- INTEGER
    - Unique id for all U.S. elected officials used by Voteview
2. candidate_id -- TEXT
    - Unique id for each electoral candidate assigned by the Federal Election Commission
3. principal_committee_id -- TEXT
   - Unique id for the principal committee attached to an electoral candidate assigned by the Federal Election Commission
4. party -- INTEGER
    - The party code of a congressperson
5. name -- TEXT
    - The full name of the elected official
6. district -- TEXT
    - The U.S. district the congressperson represents
7. state -- TEXT
    - The U.S. state the congressperson represents
8. ici -- TEXT
   - the incumbent challenger status (I = incumbent, C = challenger, O = open seat)
9. ttl_receipts -- REAL
    - sum of all receipt categories for candidate (all funds directly donated to candidate or their primary committee)
10. comm_receipts -- REAL
    - sum of all transfers from primary committee to candidate
11. ttl_disb -- REAL
    - sum of all disbursements by candidates (explains how candidates spent their money)
12. comm_disb -- REAL
    - sum of all disbursements by a candidates primary committee
13. start_cash -- REAL
    - reported starting balance by candidate 
14. end_cash -- REAL
    - reported ending balance by candidate
15. cand_contrib -- REAL
    - sum of contributions from other registered candidates
16. cand_loans -- REAL
    - sum of loans from other registered candidates
17. ind_contrib -- REAL
    - sum of receipts coming from individuals to candidate
18. other_comm_contrib -- REAL
    - sum of receipts from other committees to candidate
19. pty_contrib -- REAL
    - sum of receipts from official party organizations
20. nominate_dim1 -- REAL
    - The estimated placement of a congressperson along the first dimension of the NOMINATE scale. This dimension (often represented along the x-axis) corresponds to the left-right or liberal-conservative spectrum on economic matters.
21. nominate_dim2 -- REAL
    - The estimated placement of a congressperson along the second dimension of the NOMINATE scale. This dimension (often represented along the y-axis) corresponds to social, salient issues of the time, such as civil rights, abortion, gun rights, and so on.

###### Votes
1. icpsr -- INTEGER
    - Unique id for all U.S. elected officials used by Voteview
2. cast_code -- INTEGER
    - Numerical representation of vote responses
3. rollnumber -- INTEGER
    - Serial id of roll call vote that begins at 1 the start of every new congressional session
4. prob -- REAL
    - Estimated probability, based on NOMINATE, of the member making the vote as recorded

###### Roll Call
1. rollnumber -- INTEGER
    - Serial id of roll call vote that begins at 1 the start of every new congressional session
2. date -- TEXT
    - Date a roll call vote took place
3. session -- INTEGER
    - Either 1 or 2, corresponding to which session of congress the vote took place during
4. yea_Count -- INTEGER
    - The number of votes in favor of a decision
5. nay_Count -- INTEGER
    - The number of votes against a decision
6. nominate_mid_1 -- REAL
    - First-dimension midpoint estimate based on the Nominate scale
7. nominate_mid_2 -- REAL
    - Second-dimension midpoint estimate based on the Nominate scale
8. nominate_spread_1 -- REAL
    - First-dimension spread estimate based on the Nominate scale
9. nominate_spread_2 -- REAL
    - Second-dimension spread estimate based on the Nominate scale
10. bill_number -- TEXT
    - Unique id of the bill
11. vote_result -- TEXT
    - Official result of the roll call
12. vote_desc -- TEXT
    - Description of the roll call as assigned by Congressional staff
13. vote_question -- TEXT
    - Question addressed by the roll call
14. issue_codes -- TEXT
    - Poole and Rosenthal specific issue codes.
15. peltzman_codes -- TEXT
    - Peltzman (1984) issue-area codes.
16. clausen_codes -- TEXT
    - Clausen (1973) issue-area codes.
17. crs_policy_area -- TEXT
    - Congressional Research Service policy area.
18. crs_subjects -- TEXT
    - Congressional Research Service subject area.
19. congress_url -- TEXT
    - Link to the bill description on congress.gov 

#### Stanford DIME PLUS Datasets

###### Bills Dime
1. bill_id -- TEXT
    - Unique id of the bill
2. bill_desc -- TEXT
    - Description of the bill
3. sponsors -- TEXT
    - Congressperson that sponsored the bill
4. cosponsors -- TEXT
    - Additional sponsors of the bill
5. TW_Latent1 -- REAL
    - Topic weight for the latent category calculated by the authors of the DIME PLUS repository. All below columns are the topic weight calculations for their corresponding header name.
6. TW_Abortion_and_Social_Conservatism -- REAL
7. TW_Agriculture -- REAL
8. TW_Banking_and_Finance -- REAL
9. TW_Civil_Rights -- REAL
10. TW_Congress_and_Procedural -- REAL
11. TW_Crime -- REAL
12. TW_Defense_and_Foreign_Policy -- REAL
13. TW_Economy -- REAL
14. TW_Education -- REAL
15. TW_Energy -- REAL
16. TW_Environment -- REAL
17. TW_Fair_Elections -- REAL
18. TW_Federal_Agencies_and_Gov_Regulation -- REAL
19. TW_Guns -- REAL
20. TW_Healthcare -- REAL
21. TW_Higher_Education -- REAL
22. TW_Immigration -- REAL
23. TW_Indian_Affairs -- REAL
24. TW_Intelligence_and_Surveillance -- REAL
25. TW_Labor -- REAL
26. TW_Law_Courts_and_Judges -- REAL
27. TW_Transportation -- REAL
28. TW_Veterans_Affairs -- REAL
29. TW_Womens_Issues -- REAL

#### Federal Election Commission Datasets

###### Committees
1. affiliated_committee_name -- TEXT
    - Name of organization, committee, or other third-party group associated with the committee
2. committee_id -- TEXT
    - Unique ID for committees that donate to federal election candidates and/or expend funds for election purposes assigned by the FEC
3. committee_type -- TEXT
    - Type of committee, such as PAC or Political Party
    - Full list of committee codes and descriptions can be found [here](!https://www.fec.gov/campaign-finance-data/committee-type-code-descriptions/)
4. designation_type -- TEXT
    - Subcategory type of committee (A = Authorized by candidate, B = Lobbyist/Registrant PAC, D = Leadership PAC, J = Joint fundraiser, P = Principal campaign committee of a candidate, U = unauthorized)
5. name -- TEXT
    - Name of the committee as registered with the FEC
6. organization_type -- TEXT
    - Type of the affiliation organization, such as company or labor union
7. state --    TEXT
    - Location the committee is registered in

###### Disbursements
1. committee_id -- TEXT
    - Unique ID for committees that donate to federal election candidates and/or expend funds for election purposes assigned by the FEC
2. committee_name -- TEXT
    - Name of the committee as registered with the FEC
3. count -- INTEGER
   - Reported number of disbursements from a committee to a particular recipient
4. recipient_id -- TEXT
   - Unique ID for the recipient of the disbursement as assigned by the FEC
5. receipient_name -- TEXT
   - Full name of recipient
6. total -- TEXT
   - sum of disbursement funds from a committee to a particular recipient
  
###### Receipts
1. committee_id -- TEXT
    - Unique ID for committees that donate to federal election candidates and/or expend funds for election purposes assigned by the FEC
2. committee_name -- TEXT
    - Name of the committee as registered with the FEC
3. count -- INTEGER
   - Reported number of disbursements from a committee to a particular recipient
4. recipient_id -- TEXT
   - Unique ID for the recipient of the disbursement as assigned by the FEC
5. receipient_name -- TEXT
   - Full name of recipient
6. total -- TEXT
   - sum of disbursement funds from a committee to a particular recipient
  

###### Expenditures
1. candidate_id -- TEXT
    - Unique ID of the candidate that the expenditure is aimed at
2. candidate_name -- TEXT
    - Full name of candidate
3. committee_id -- TEXT
    - Unique ID for committees that donate to federal election candidates and/or expend funds for election purposes assigned by the FEC
4. committee_name -- TEXT
    - Full name of committee
5. count -- INTEGER
   - Reported number of expenditures from a committee aimed at a particular candidate
6. support_oppose_indicator -- TEXT
   - "S" for an expenditure in support of a candidate, "O" for expenditure in opposition
6. total -- TEXT
   - sum of expenditures from a committee aimed at a particular candidate
