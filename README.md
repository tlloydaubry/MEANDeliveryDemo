MEAN Stack Delivery Demo
========================
Overview
--------
A simple MEAN (MongoDB, ExpressJS, AngularJS, NodeJS) Stack application with fully automated delivery all hosted using Amazon Web Services (EC2, S3, ElasticBeanstalk)
The Delivery
------------
Jenkins, running on an EC2 instance (accesible here 52.24.119.235:8080), monitors the health of the repository and automates the testing/deployment to seperate QA and Production hosts. When changes are pushed to the repository Jenkins pulls the code and runs test on the API and static web content of the web application. Then the static web content is built for development/QA/production (to utilize local storage or EC2 monogodb server(54.172.184.199)), compiled, optimized, and then pushed to an Amazon S3 bucket (https://s3.amazonaws.com/tlademo-qa/index.html). The NodeJS/SailsJS code is then pushed to an Amazon Elastic Beanstalk (tlademo-eb-qa-env.elasticbeanstalk.com)  
The Application: http://tlademo-qa.s3-website-us-east-1.amazonaws.com/#/home