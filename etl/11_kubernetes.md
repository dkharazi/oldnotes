## General Description
- Kubernetes is a platform for orchestrating containers
- In other words, Kubernetes is a platform for managing containers
- The basic idea behind Kubernetes is to further abstract machines, storage, and networks away from their physical implementations
- Kubernetes tries to achieve this goal by providing an interface to deploy containers to a cluster

## Container Orchestration
- Container orchestration refers to container management, which includes:
	- Automating deployment of containers running applications
	- Scaling up or down the number of containers running
		- We may need more containers if more people want to run instances of an application
		- We may also need more containers if we need more memory, storage, or CPU for any already established container
	- Monitoring resources dedicated to containers
- Kubernetes allows us to lower the any unnecessary costs associated with cloud computing be removing any inactive containers

## Nodes and Pods
- A node is a physical or virtual machine
- We can create nodes using a cloud service (i.e. we can use AWS EC2 to create an EC2 instance, which is a node)
- A pod is one or more containers that are logically grouped together
- One node can run more than one pod
- We could spin up two Nginx instances (load balancers) and assign them to a public IP address on a Google Compute Engine after starting a Kubernetes cluster

## References
- https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/
- http://www.developintelligence.com/blog/2017/02/kubernetes-actually-use/
- https://stackoverflow.com/questions/51693716/apache-hadoop-yarn-vs-kubernetes
- https://mapr.com/products/kubernetes/
- https://www.reddit.com/r/explainlikeimfive/comments/8ur2z7/eli5_what_is_kubernetes_and_how_different_better/e1hsmg6/
