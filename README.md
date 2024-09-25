# README for snowflake-cortex-rag-assistant-lab

Please refer to the following Snowflake Cortex RAG Assistant Hands-On Lab Prerequisites before beginning this lab:

Snowflake Cortex RAG Assistant Hands-On Lab Prerequisites

Snowflake
A Snowflake account with a user created with ACCOUNTADMIN permissions. This user will be used to get things setup in Snowflake.
It is strongly recommended to sign up for a free 30 day trial Snowflake account for this lab.
Once you've registered, you'll get an email that will bring you to Snowflake so that you can sign in. Make sure to Activate your account and pick a username and password that you will remember. This will be important for logging in later on.

Github
A GitHub account. If you don't already have a GitHub account you can create one for free. Visit the Join GitHub page to get started.
It is strongly recommended to use your personal GitHub profile, as you will need permissions to enable actions at a later step.

Connecting GIT with Snowflake
1. Sign into your Snowflake account
2. Click + Create
  a. SQL Worksheet
    i. Save the worksheet as: GITHUB_INTEGRATION
    ii. Paste and run the following code:

 // A user with the CREATE INTEGRATION privilege granted may run this query to create an API integration allowing users to connect to a git provider.
 // For more information, see: https://docs.snowflake.com/en/developer-guide/git/git-setting-up#create-an-api-integration-for-interacting-with-the-repository-api
create or replace api integration GIT_INTEGRATION
    api_provider = git_https_api
    api_allowed_prefixes = ('https://github.com/')
    enabled = true
    allowed_authentication_secrets = all
    -- comment='<comment>';

3. Return to the Snowflake homepage & refresh the page
4. Click + Create
  a. Git Repository
    i. Name your repository: GITHUB_REPOSITORY
    ii. Paste the repository URL (https://github.com/phdata/snowflake-cortex-rag-assistant-lab/)
    iii. Select the API Integration you created in Step 2.a
    iv. Create a database for this lab: Cortex_HOL_DB
    v. Click Create
5. Click + Create
  b. Notebook
    i. From Git Repository
    ii. Select the file location in repository
    iii. Select CORTEX_HOL_DB
    iv. Select GITHUB_REPOSITORY
    v. Navigate to and select the Cortex_HOL.ipynb file
    vi. Click Create


Using Snowflake to commit code to GIT (not required for this lab):

Create a Personal Access Token in your Github repository. Scroll down to "Creating a fine-grained personal access token" here: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens
