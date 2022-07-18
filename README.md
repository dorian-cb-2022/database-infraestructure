# database-infraestructure

This repository contains the infraestructure needed to deploy an RDS database using Postgres.

# CI/CD

This repository has a single GitHub Actions workflow (.github/workflows/cloudformation-deploy.yml), however it doesn't trigger automatically, as some accidental changes might replace the database and cause a loss of data.

# Possible improvements

The VPC for this database should be created here or in another repository, currently it is using the default VPC and that creates a problem when making reusable CFN templates (As it can't access the VPC's Id through exports).

There are also several security risks that have been ignored for simplicity in this project. (For example, the security group of the Database allowing all incoming/outgoing traffic).