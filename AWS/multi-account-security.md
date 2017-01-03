AWS Account is the **largest level of isolation between resources**

Some orgs use single account (usually 1 app with 1 dev team)

### Why one isn't enough ###

+ Many Teams (YES)
+ Resource isolation (like dev/demo/prod resource?)


### Goals 🏁 ###

+ Automated setup of accounts
+ Scalable
+ Self-service: Teams can be enabled to deplay their own infrastructure.

### Accounts we want ###
+ Single accounts
  + Security acconunt
  + Shared services (dev and deployment pipelines?)
  + Billing
+ Multiple Instances

### Account Security Day 1 ###
For each account

+ You will get the root credentials. LOCK THEM AWAY.
+ Enable Cloud Trail
+ Map Enterprise Roles (via Federation TODO: Ilya to talk about Federation)
+ Custom Actions & Conditions (for elevated privliages).


# Types accounts

### Billing ###

+ No connection to data center (doensn't need it)
+ Link all accounts to Billing account (visibility into spending)

### Security Account ###
> Very important

+ Enable cloud trail accorss ALL Regions!
  + If account is compromised and resources get deployed in a different location, you will want to see that.
+ Enable MFA delete.
+ X-account read/write. Security account can go into other accounts and scan resources. Read for scanning (automated tools). Write for if there is an issue, go in and fix.
+ Encryption keys (within security account) allows you to shut down a key if compromised.

### Sandbox Account ###
+ Experiment
+ New Initiatives
+ Disconnected from data center (isolated)

### Non-prod account ###
+ Production-like, but close to prod as possible
+ Federation into account.
+ Staging!
+ QA!
+ Pipelines yayyy!

### Production Account ###
+ Same isolation, but connected to production network
+ Connection to Data Center
+ Possibly no human access. Available through CI/CD.


### ❓ For Ilya ###
+ Best way to lock away root creds?

### Further things to look at ###
+ [AWS Tagging Strategies](https://aws.amazon.com/answers/account-management/aws-tagging-strategies/)
+ [Enabling Federation to AWS](https://aws.amazon.com/blogs/security/enabling-federation-to-aws-using-windows-active-directory-adfs-and-saml-2-0/)
