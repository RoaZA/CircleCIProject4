# Hosting a Full-Stack Application (Udagram)

[![CircleCI](https://dl.circleci.com/status-badge/img/gh/RoaZA/CircleCIProject4/tree/main.svg?style=shield)](https://dl.circleci.com/status-badge/redirect/gh/RoaZA/CircleCIProject4/tree/main)


### **We use [ Udagram app](https://github.com/udacity/nd0067-c4-deployment-process-project-starter) a Full-Stack web application that provided from Udacity as a starter code in order to implement the deployment process.**
---
### Configure infrastructure for a web application

####  * AWS RDS

* Crete remote DB for the deployment and connect it with **the API** then create security groups and edit the inbound rules for PostgreSQL.

####  * AWS EB

* Initialize **EB** environment for the Backend project application (**API**) using `eb init --platform node.js-14 --region us-east-1` then create the environment remotely using `eb create --sample udagram-api-dev` then use this environment  with `eb use udagram-api-dev`.
*  Set environment variables using `eb setenv` .
*  After deploying the app on **EB** ,  then the URL for **API**will display `http://udagram-api-dev.eba-fmdi6xaa.us-east-1.elasticbeanstalk.com/`

####  *AWS S3

* Create S3 bucket to deploy **Frontend** with`aws s3api create-bucket --bucket rise-udagram --region us-east-1.
* Build **Frontend** then deploy to **S3** bucket with `aws s3 cp --recursive --acl public-read ./www s3://rise-udagram`


####  * CIrcleCI
1. install dependencies
2. build the project -> get .zip file 
3. test and lint 
4.  deploy .zip file in BE and FE

**All the variables found in the application are configured inside CircleCi project setting**