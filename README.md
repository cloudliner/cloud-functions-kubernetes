# Run a batch on Google Kubernetes Engine (GKE) from Cloud Functions for Firebase

cd docker
docker build -t hello-kubernetes ./
docker run --rm -it hello-kubernetes

gcloud auth configure-docker
docker tag hello-kubernetes gcr.io/{PROJECT_ID}/hello-kubernetes
docker push gcr.io/{PROJECT_ID}/hello-kubernetes

gcloud container clusters get-credentials your-first-cluster-1 --zone us-central1-a
kubectl run hello-batch --image=gcr.io/{PROJECT_ID}/hello-kubernetes --restart=OnFailure
kubectl delete job hello-batch

