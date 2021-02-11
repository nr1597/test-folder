eks-workshop-sample-api-service-go
A sample Kubernetes service used in the EKS Workshop CI/CD Pipeline module.

The Dockerfile is a multi-stage build that compiles the Go application and then packages it in a minimal image that pulls from scratch. The size of this Docker image is ~ 3.2 MiB.

The buildspec.yml file is used by the AWS CodeBuild stage. In this file, it pulls down kubectl, builds the container image, pushes the image to Amazon ECR and then deploys the change to the Amazon EKS Cluster.

In the hello-k8s.yml file, you will find the Kubernetes service and deployment definitions. The service is configured with a LoadBalancer which prompts Kubernetes to launch an external load balancer using an AWS ELB.
