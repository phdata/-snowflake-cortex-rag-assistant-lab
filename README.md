# README for snowflake-cortex-rag-assistant-lab

# Snowflake Cortex RAG Assistant Hands-On Lab 

## Prerequisites

### Snowflake Trial Account 
A Snowflake account with a user created with ACCOUNTADMIN permissions. This user will be used to get things setup in Snowflake.
We recommend completing this lab in a free 30-day trial account, since it will allow full account administration to configure integrations.

To sign up for a trial account:
1. Navigate to https://signup.snowflake.com/ in your browser
2. Select "Enterprise" as your Snowflake Edition
3. Select a cloud provider and region – we have validated this lab on AWS cloud in the `US East (Northern Virginia)` region.

Once you've registered, you'll get an email that will bring you to Snowflake so that you can sign in. Make sure to Activate your account and pick a username and password that you will remember. This will be important for logging in later on.

### GitHub (optional)

If you'd like to commit changes to a fork of this repository, you will need a GitHub account.
If you don't already have a GitHub account you can create one for free.
Visit the Join GitHub page to get started.
It is strongly recommended to use your personal GitHub profile, as you will need permissions to enable actions at a later step.

### Snowflake Integration with GitHub

Connecting GIT with Snowflake
1. Sign into your Snowflake account
2. Click + Create: `SQL Worksheet`
3. Save the worksheet as: GITHUB_INTEGRATION
4. Paste and run the following code:
```
 // A user with the CREATE INTEGRATION privilege granted may run this query to create an API integration allowing users to connect to a git provider.
 // For more information, see: https://docs.snowflake.com/en/developer-guide/git/git-setting-up#create-an-api-integration-for-interacting-with-the-repository-api
create or replace api integration GIT_INTEGRATION
    api_provider = git_https_api
    api_allowed_prefixes = ('https://github.com/')
    enabled = true
    allowed_authentication_secrets = all
    -- comment='<comment>';
```
### Clone the Git repository
1. Return to the Snowflake homepage & refresh the page
2. Click + Create: `Git Repository`
3. Name your repository: `CORTEX_HOL_REPOSITORY`
4. Paste the repository URL (https://github.com/phdata/snowflake-cortex-rag-assistant-lab/)
5. Select the API Integration you created in Step 2.a  (`GIT_INTEGRATION`)
6. Click + Database to create a database for this lab, with the name: `CORTEX_HOL_DB`
7. Click Create

### Create Notebook 
1. Click + Create: `Notebook`
2. Select From Git Repository
3. Select the file location in repository
4. Select `CORTEX_HOL_DB`
5. Select `CORTEX_HOL_REPOSITORY`
6. Navigate to and select the Cortex_HOL.ipynb file
7. Click Create

## Complete the lab in the notebook!
You can now open the notebook you created in the prerequisites above.  

### Using Snowflake to commit code to GIT (optional not required for this lab):

Create a Personal Access Token in your Github repository. Scroll down to "Creating a fine-grained personal access token" here: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens
