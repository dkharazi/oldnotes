## Virtual Machines
- Azure Data Science Virtual Machines are offered by Azure and hosted by Azure
- Azure Data Science Virtual Machines are virtual machines with preinstalled data science tools
- Azure Data Science Virtual Machines are used for building models
- We can build models using Python and R code in our local IDE on the virtual machine

## Machine Learning Services
1. Azure Machine Learning service
	- Azure Machine Learning service is a cloud service offered by Azure and hosted by Azure
	- Azure Machine Learning service is a cloud service used for building and deploying models
	- We can build models using Python (not R) code in our local IDE
	- We can write and execute Jupyter notebooks in our browser once signed into Azure Machine Learning service
	- We can deploy models using Azure DevOps
	- Azure Machine Learning service is typically used for the model deployment stage (i.e. web apps), since they provide the compute resources related to clients using the deployed model
2. Azure Machine Learning Studio
	- Azure Machine Learning Studio is a cloud service offered by Azure and hosted by Azure
	- Azure Machine Learning Studio is a cloud service used for building and deploying models
	- We can build models using a GUI-based platform in our browser once signed into Azure Machine Learning Studio
	- We can write and execute Jupyter notebooks in our browser once signed into Azure Machine Learning Studio
	- We can deploy models using Azure DevOps
3. Azure Databricks
	- Azure Databricks is a cloud service offered by Databricks and hosted by Azure
	- Azure Databricks is a cloud service used for building and deploying models
	- We can build models using Python and R code in our local IDE
	- We can write and execute Jupyter notebooks in our browser once signed into Azure Databricks
	- We can deploy models using Azure DevOps
	- Azure Databricks is typically used for the model analysis stage, since they provide the compute resources related to data preprocessing or modeling (i.e. handled by Spark)
4. Azure HDInsight
	- Azure HDInsight is a cloud service offered by Azure and hosted by Azure
	- Azure HDInsight is a cloud service used for setting up cloud-based Hadoop and Spark clusters for computation
	- These Hadoop and Spark clusters are used for processing data via MapReduce or Spark jobs
	- Azure HDInsight is not a data store, but we can use another Azure service (i.e. Azure Data Lake, Azure Data Factory, etc.) for storing any data processed or collected from our clusters
	- Of all Azure's services, HDInsight is the closest to an IaaS, since there is some amount of cluster management involved
5. SQL Server Machine Learning Services
	- SQL Server Machine Learning Services is a cloud service offered by Azure and hosted by Azure
	- SQL Server Machine Learning Services is an add-on for SQL Server
	- SQL Server Machine Learning Services is used for building models
	- It allows you to execute Python and R code on your local SQL Server environment
	- This eliminates the need to switch between the database and machine learning environments

## Workspaces
- A workspace serves as a hub for building and deploying models
- We can create workspaces in the Azure Machine Learning service
- We can access workspaces using Python in an IDE
- A workspace will store the model's compute target and any experiment objects that are required for each model build
- Storing these experiment objects will allows us to track runs and retrieve logs, metrics, outputs, and scripts easily
- A workspace is defined by the following properties:
	- `Workspace name:` Our desired name for the workspace
	- `Subscription:` An Azure subscription to own this resouce (i.e. Visual Studio)
	- `Resource Group:` An Azure resource that has been allocated policies or permissions
	- `Location:` A location where the workspace will be created, so we typically want to select a location near where the workspace will be used

## Images
- We can see our built images in the Azure Machine Learning service
- We can also see any running containers based on those images
- An image is made up of the following components:
	1. A model represented as a pickle file
	2. A scoring script
		- The scoring script (i.e. score.py) is responsible for consuming the model
		- The scoring script only has two functions:
			- An init function, which loads the model
			- A run function, which does the inference (i.e. model.predict(data))
	3. An environment file represented as a YAML file
		- The environment file declares the dependencies that are needed by the model, scoring script, or application
		- For example, we could specify numpy or scikit-learn in our YAML file
- Once a model has been trained and registered, an image will be built for deployment
- We then deploy our model by running a container (Azure container, Docker container, etc.) based on this image
	- Specifically, we refer to these running containers as deployed web services, if the container is a AKS or FPGA container
	- On the other hand, we refer to these running containers as an IoT module, if the container is a Docker container
- Then, we can use Python to access the deployed model in our container

## Pipelines
- A pipeline is a tool used to create and manage workflows during our model deployment process
- This could include the following:
        - Data manipulation
        - Model training and testing
        - Deployment phases
- We can build pipelines in the Azure Machine Learning service
- Here are a few reasons why we would want to build a pipeline:
        - Scheduling tasks and executions, which frees up data scientists' time
        - Allocating compute targets, which makes it easier to scale up or down
        - Reusing pipeline scripts, which makes it faster to setup the process of retraining and scoring models
        - Recording and managing input, output, and data, which makes it easier for improving models later

## Machine Learning Workflow
1. Deploy a model 
	- We would use the Azure Machine Learning service or Azure Databricks to achieve this
2. Build a pipeline to automate the process of deploying this model in the future
	- We will typically want to automatically tune the model
	- We can build a pipeline to avoid going through the process of preparing more data, validating the data, and deploying the model manually
	- We would use the Azure Machine Learning service or Azure Devops to achieve this

## Azure Machine Learning Deployment Example
1. Create a workspace in the Azure Machine Learning service
2. Create a model using regular Python code in any IDE
- This could include creating a model using sklearn, tensorflow, etc.
- We would want to save this model using pickle
3. Initialize the workspace using the Python SDK in an IDE
```
from azureml.core import Workspace
ws = Workspace.create(
	name='myworkspace',
	subscription_id='<azure-subscription-id>',
	resource_group='myresourcegroup',
	create_resource_group=True,
	location='eastus2'
	)
```
4. Register input data and output data using the Python SDK in an IDE
- We want to record the data used to create this model in our workspace
```
from azureml.core import Dataset
datastore = ws.get_default_datastore()
datastore.upload_files(
	files=['./features.csv', './labels.csv'],
	target_path='sklearn_regression/',
	overwrite=True
	)
input_dataset = Dataset.Tabular.from_delimited_files(path=[(datastore, 'sklearn_regression/features.csv')])
output_dataset = Dataset.Tabular.from_delimited_files(path=[(datastore, 'sklearn_regression/labels.csv')])
```
5. Register our model using the Python SDK in an IDE
- We want to record model metadata in our workspace
```
from azureml.core import Model
from azureml.core.resource_configuration import ResourceConfiguration
model = Model.register(
	workspace=ws,
	model_name='my-sklearn-model',
	model_path='./sklearn_regression_model.pkl',
	model_framework=Model.Framework.SCIKITLEARN,
	model_framework_version='0.19.1',
	sample_input_dataset=input_dataset,
	sample_output_dataset=output_dataset,
	resource_configuration=ResourceConfiguration(cpu=1, memory_in_gb=0.5),
	description='Ridge regression model to predict diabetes progression.',
	tags={'area': 'diabetes', 'type': 'regression'}
	)
```
6. Deploy our model using the Python SDK in an IDE
- Our model is deployed as a containerized web app (or web service)
- In other words, Azure deploys our model by building an image (from the model) and running containers based on that image
- For a deployed web service, we can choose from the following container instances: Azure Container Instance (ACI), FPGA, or Docker
- If we wanted to run our web service locally (rather than running it on Azure ML service), then we would want to deploy our model to a local Docker container instead
- If we wanted to run a more production-ready web service on Azure ML, then we want to deploy our model to the Azure Kubernetes service instead
```
from azureml.core import Webservice
service = Model.deploy(ws, 'my-sklearn-service', [model])
```
7. Run the deployed web service using the Python SDK in an IDE
```
import json
input_payload = json.dumps({
	'data': [[1, 2, 3, 4, 5, 4, 3, 2, 9, 187]],
	'method': 'predict'
	})
output = service.run(input_payload)
```

## More about Python SDK: Runs and Experiments
- The Run class, within the context of the Azure Machine Learning service, refers to Python code for a specific task; for example, training a model or tuning hyperparameters
- A run logs metrics and uploads the result to the Azure platform, and it's a more natural way to track jobs in a workspace
- The Experiment class is a term that refers to a composition of a series of runs
- For example, we could have one run for a logistic regression model, another run for a kNN model, and together they make up an experiment
- We create runs and experiments to easily monitor and review a model throughout its training, testing, or tuning process
- We can observe details about runs or experiments in the Azure Machine Learning service, and navigating to the workspace associated with the runs or experiments
```
from azureml.core import Experiment
#Create an experiment
experiment = Experiment(workspace = ws, name = "my-first-experiment")
#Create a run
run = experiment.start_logging()
run.log("trial",1)
run.complete()
```

## Other Deployment Options
- We can deploy an image already created from a model
	- In this case, we would use the `deploy_from_image` method from the Webservice class
	- We could also use the `deploy` method from the Webservice class
- We can deploy a model already registered in the workspace
	- In this case, we could use the `deploy_from_model` method from the Webservice class
	- We could also use the `deploy` method from the Model class
	- This method will create an image

## Autuomated Machine Learning
- Automated machine learning (or AutoML) provides an automated solution to hyperparameter tuning and model selection
- It achieves this by letting the Azure Machine Learning service run all of our pickle models concurrently, comparing the results, and recommending the best model for the job based on the training scores
- Therefore, we don't need to have already deployed our models in order to use AutoML (i.e. can just use AutoML in the model training process)
- The AutoML HyperDrive service makes it possible to find optimal hyperparameter values automatically
- Azure Databricks has its own AutoML capabilities, and therefore doesn't really need AutoML from the Azure Machine Learning service
- Typically, AutoML involves the following steps:
	1. Select your experiment type
		- This could be classification, regression, or forecasting
	2. Ingest the data
		- We can ingest the data either from our local computer or from cloud storage
		- A popular storage service for Azure is Azure Blob Storage
	3. Configure the targets
		- We must configure the compute targets which will run the experiment
		- This can be a local machine or a cloud resource, such as Azure Machine Learning Computer, Azure HDInsight, or a remote virtual machine
	4. Configure the AutoML job
		- We need to configure the parameters used as Azure Machine Learning iterates over different models and hyperparameter settings
		- We also identify which metrics AutoML should look at to determine the best model
	5. Submit the training run

## References
- https://docs.microsoft.com/en-us/learn/certifications/azure-data-scientist
- https://github.com/Microsoft/MLOpsPython
- https://github.com/Azure/MachineLearningNotebooks/blob/master/how-to-use-azureml/deployment/deploy-to-cloud/model-register-and-deploy.ipynb
- https://docs.microsoft.com/en-us/azure/devops/pipelines/targets/azure-machine-learning?view=azure-devops&tabs=yaml
- https://www.youtube.com/watch?v=tXZMYB3ByKE&feature=emb_logo
- https://www.clearpeaks.com/cloud-analytics-on-azure-databricks-vs-hdinsight-vs-data-lake-analytics/
