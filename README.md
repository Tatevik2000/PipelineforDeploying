"Build and Deploy" is a pipeline that automates the build and deployment process of a Docker image to a Kubernetes cluster on Google Cloud Platform.

GCP_SA_KEY: The service account key for Google Cloud Platform, used for authentication.

IMAGE_NAME: The name of the Docker image to build and deploy.

IMAGE_TAG: The tag for the Docker image, set to the commit SHA of the push event.

NAMESPACE: The Kubernetes namespace to deploy the application to.

DOCKER_REGISTRY: The Docker registry to push the built image to.

PROJECT_ID: The ID of the Google Cloud Platform project to deploy the application to.

Steps of my pipline

1.Checkout: This step checks out the source code from the repository.

2.Set Image Tag: This step sets the Docker image tag to the first 8 characters of the commit SHA.

3.Login to Docker Hub: This step logs in to Docker Hub using the Docker username and password secrets.

4.Build and Push Docker Image: This step builds a Docker image from the source code and pushes it to the Docker Hub registry.

5.Install kubectl: This step installs the kubectl command-line tool, which is used to manage Kubernetes clusters.

6.Set up Cloud SDK: This step sets up the Google Cloud SDK, which is used to authenticate and interact with the Google Cloud Platform.

7.Download gke-gcloud-auth-plugin: This step downloads and installs the gke-gcloud-auth-plugin, which is used to authenticate with Google Kubernetes Engine clusters.

8.Set active service account: This step activates the service account specified in the GCP_SA_KEY environment variable.

9.Set Image on Deployment: This step updates the image tag in the Kubernetes deployment manifest with the newly built Docker image tag and applies the changes to the Kubernetes cluster.
