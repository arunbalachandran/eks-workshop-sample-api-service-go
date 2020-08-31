我是光年实验室高级招聘经理。
我在github上访问了你的开源项目，你的代码超赞。你最近有没有在看工作机会，我们在招软件开发工程师，拉钩和BOSS等招聘网站也发布了相关岗位，有公司和职位的详细信息。
我们公司在杭州，业务主要做流量增长，是很多大型互联网公司的流量顾问。公司弹性工作制，福利齐全，发展潜力大，良好的办公环境和学习氛围。
公司官网是http://www.gnlab.com,公司地址是杭州市西湖区古墩路紫金广场B座，若你感兴趣，欢迎与我联系，
电话是0571-88839161，手机号：18668131388，微信号：echo 'bGhsaGxoMTEyNAo='|base64 -D ,静待佳音。如有打扰，还请见谅，祝生活愉快工作顺利。

# eks-workshop-sample-api-service-go

A sample Kubernetes service used in the [EKS Workshop](https://eksworkshop.com/) CI/CD Pipeline module.

The Dockerfile is a [multi-stage](https://docs.docker.com/develop/develop-images/multistage-build/) build that
compiles the Go application and then packages it in a minimal image that pulls from [scratch](https://hub.docker.com/_/scratch/).
The size of this Docker image is ~ 3.2 MiB.

The buildspec.yml file is used by the [AWS CodeBuild](https://aws.amazon.com/codebuild/) stage. In this file, it pulls down
kubectl, builds the container image, pushes the image to [Amazon ECR](https://aws.amazon.com/ecr/) and then deploys the change to the
[Amazon EKS Cluster](https://aws.amazon.com/eks/).

In the hello-k8s.yml file, you will find the Kubernetes [service](https://kubernetes.io/docs/concepts/services-networking/service/) and
[deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) definitions. The service is configured with
a [LoadBalancer](https://kubernetes.io/docs/tasks/access-application-cluster/create-external-load-balancer/) which prompts Kubernetes
to launch an external load balancer using an [AWS ELB](https://aws.amazon.com/elasticloadbalancing/).
