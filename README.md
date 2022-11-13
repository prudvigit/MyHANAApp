# Getting Started

Welcome to your new project.

It contains these folders and files, following our recommended project layout:

File or Folder | Purpose
---------|----------
`app/` | content for UI frontends goes here
`db/` | your domain models and data go here
`srv/` | your service models and code go here
`package.json` | project metadata and configuration
`readme.md` | this getting started guide


## Next Steps

- Open a new terminal and run `cds watch` 
- (in VS Code simply choose _**Terminal** > Run Task > cds watch_)
- Start adding content, for example, a [db/schema.cds](db/schema.cds).


## Learn More

Learn more at https://cap.cloud.sap/docs/get-started/.


CDS Commands:
Run the below command after the wizard creating the project for CAP
cds add hana --> to add db info in mta file

## Excesice of the tutorial
https://developers.sap.com/tutorials/hana-cloud-cap-create-database-cds.html

get header and items data

https://github.com/SAP-samples/hana-opensap-cloud-2020


## To run the app locally, we need to do the following steps
Step1: Create the respective service keys
Step2: Run the npm for all package.json for the app, db and main project
Step3: Run --> cds deploy --to hana:MyHANAApp-dev(name of the hdi)
Step4: Run --> cds add approuter


CF and HANA-CLI Commands

1. cf services
2. cf create-service hana-shared MyHANAApp-dev
3. cf service MyHANAApp-dev
4. cf create-service-key MyHANAApp-dev SharedDevKey
5. cf create-service xsuaa application MyHANAApp-auth -c xs-security.json --> create xsuaa service
6. cf create-service-key MyHANAApp-auth default



HANA-CLI:

hana-cli hc
hana-cli start
hana-cli stop
hana-cli tables
hana-cli dbx --> database explorer
hana-cli querySimple -q "select * from APP_INTERACTIONS_INTERACTIONS_HEADER"

hana-cli inspectView -v V_INTERACTION -o cds

1.hana-cli createModule

CDS Commands:

cds add hana --> to add db info in mta file
cds deploy --to hana:MyHANAApp-dev  ---> deploy the databse artifacts
cds watch --profile hybrid --> Connect the remote source and service is running on the locally
cds add approuter   --> add approuter to our project
cds compile srv/ --to xsuaa > xs-security.json  --> add the xsuaa security
cds bind -2 MyHANAApp-auth:default --> Binding the XSUAA service for local testing
cds bind --exec npm run app


Kill Processor:
sudo lsof -PiTCP -sTCP:LISTEN  --> List of ports
kill -9 26772

User api:
http://localhost:5000/user-api/attributes

Github Key: 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
