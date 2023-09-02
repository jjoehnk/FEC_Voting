# Funding Sources and Congressional Voting Patterns
*Wiki*

Data Dictionaries of all Tables used can be found [here](/plans_background/sources/data_dictionaries.md)
## Table of Contents
1. [Data Collection and Wrangling](#data-collection-and-wrangling)

#### Data Collection and Wrangling
*Each section is linked to the corresponding Jupyter Notebook for a step-by-step guide*

[CONGRESS DATA](/fec_voting/EA_113congressdata.ipynb)

1. Pull flat files on congressional session 113th from Voteview and DIME PLUS and read into python application, such as Jupyter Notebook. 
    - Datasets include:
        [] Voteview Member Ideology
        [] Voteview Congressional Votes
        [] Voteview Member Votes
        [] DIME PLUS Congressional Bills
    - Additional datasets need to be created to interpret encoded categories in Voteview:
        [] Party Codes
        [] Cast Codes

2. Remove columns with irrelevant information and those made up entirely of null values.

3. Filter data to only include details of the House of Representatives in the 113th congressional session. 


[FEDERAL ELECTION COMMISSION DATA](/fec_voting/EA_api_from_fec.ipynb)

1. Requested APIs from FEC and Congress to pull funding information and bill information from the 113th congress

[SQLite DATABASE SET-UP](/fec_voting/sqldb.ipynb)
1. Set up API KEY at [Open FEC API](https://api.open.fec.gov/developers/)

2. Create referential tables of registered committees and candidates in the 2011-2012 election cycle
    - build url requests from the following sections at Open FEC respectively:
        - /v1/candidates/search
        - /v1/committees
    - example codeblock to build dataframes:

`committees_all_pages = []
for i in range(1,11):
    committees_rq = rq.get(f'{url}&api_key={api_key_fec}')
    
    committees = committees_rq.json()
    committees_all_pages.append(committees)
    
blank_list = []
for i in range(0,10):
    blank_list.extend(committees_all_pages[i]['results'] )     
    
committees_df = pd.DataFrame(blank_list)`

3. Drop superfluous and null columns, and rename remaining ones for clarity