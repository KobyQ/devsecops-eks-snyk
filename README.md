# Build a DevSecOps Pipeline for AWS EKS with GitHub Actions and Snyk

An end-to-end Kubernetes-based DevSecOps pipeline for AWS EKS with continuous testing, continuous logging and monitoring, auditing, governance and operations. 
Demonstrates how to integrate various scanning tools, such as Git-Secrets, Snyk and Sysdig Falco for Secret Analysis, SCA, SAST, DAST, and RASP analysis. 
To reduce operations overhead, explore aggregating and managing vulnerability findings in AWS Security Hub as a single view. 

1. Create the EKS Network

aws cloudformation create-stack --region eu-west-1 --stack-name test-devsecops-vpc --template-body file://vpc.yml

2. Create the EKS cluster

aws cloudformation create-stack --stack-name test-devsecops-eks --template-body file://eks.yml --capabilities CAPABILITY_NAMED_IAM

3. Create the ECR Repository

aws cloudformation create-stack --region eu-west-1 --stack-name test-devsecops-repo --template-body file://cloudformation/codecommit-ecr.yml

4. Add secrets to your GitHub Repository
5. Create or clone a sample application 
6. Test the deployment