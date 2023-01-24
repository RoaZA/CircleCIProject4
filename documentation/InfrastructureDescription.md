### Configure infrastructure for a web application
**Here is a high level diagram for AWS cloud infrastructure and services** 
![](../screenshots/AWS_Infra.png)

####  * AWS RDS

* Crete remote DB for the deployment and connect it with **the API** then create security groups and edit the inbound rules for PostgreSQL.
![](../screenshots/RDS1.png)
![](../screenshots/RDS2.png)
![](../screenshots/RDS3.png)
* Test DB connection
![](../screenshots/DBconn.png)
####  * AWS EB

* Initialize **EB** environment for the Backend project application (**API**) using `eb init --platform node.js-14 --region us-east-1` then create the environment remotely using `eb create --sample udagram-api-dev` then use this environment  with `eb use udagram-api-dev`.
![](../screenshots/EB1.png)
*  Set environment variables using `eb setenv`
![](../screenshots/EB4.png)
*  After deploying the app on **EB** ,  then the URL for **API**will display `http://udagram-api-dev.eba-fmdi6xaa.us-east-1.elasticbeanstalk.com/`
![](../screenshots/EB2.png)
![](../screenshots/API.png)
####  * AWS S3

* Create S3 bucket to deploy **Frontend** with`aws s3api create-bucket --bucket rise-udagram --region us-east-1.
![](../screenshots/S3-1.png)
* Build **Frontend** then deploy to **S3** bucket with `aws s3 cp --recursive --acl public-read ./www s3://rise-udagram`
![](../screenshots/S3-2.png)