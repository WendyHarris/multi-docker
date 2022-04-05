# multi-docker-elasticbeanstalk -- Fibonacci Calculator

## Overview
Created along with the https://ibm-learning.udemy.com/course/docker-and-kubernetes-the-complete-guide By: Stephen Grider. 

Built a Fibonacci Calculator in React, that takes an index from the user and then calculates the value of that index in the Fibonacci sequence.
The indexes are stored in a Postgres relational database and the results of the calculations are stored in a Redis server that acts as a cache.
The calculations of the Fibonacci index are done by a separate nodejs worker that in sends the results to redis.

Built custom images using Docker and learned Docker CLI for debugging and inspecting running containers.
Built a pipeline for CI + CD utilizing Github, Travis CI, AWS ElasticBeanstalk.

### Travis CI 
Travis CI triggered by a commit/pull request to the main branch on Github, and being responsible for testing, building Docker images, pushing to Docker Hub, and deploying to AWS.  

### AWS 
Within AWS utilizing Elastic Beanstalk app with Docker Multi-Container settings defined.
An S3 bucket is configured automatically when you create the Elastic Beanstalk app, and will host the project contents for AWS to deploy.
Creation of a Security Group under VPC AWS service.
Creation of a Postgres instance under RDS AWS service.
Associate the security group to Postgres instance.
Creation of a Redis instance unser ElastiCache AWS service.
Associate the security group to Redis instance.
Define the necessary environment variables in Elastic Beanstalk AWS service for Postgres and Redis instances.
Create new user under IAM AWS service to use in TravisCI to later deploy to AWS.

