# Run a batch on Google Kubernetes Engine (GKE) from Google Cloud Functions

cd docker
docker build -t hello-kubernetes ./
docker run --rm -it hello-kubernetes