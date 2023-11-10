# Welcome, Fellow MLOps Enthusiasts!

This project presents an end-to-end pipeline utilizing Kubeflow components to construct and deploy TensorFlow models on Vertex AI. The pipeline is organized into separate reusable Kubeflow pipeline components, covering four key stages: data collection, data preparation, model training, and the final deployment to Vertex AI.

## Overview

This project is designed to serve as a foundational example of MLOps in Vertex AI, with a focus on the MNIST dataset. Often regarded as the "hello world" of deep learning, the MNIST dataset provides an ideal starting point to showcase the simplicity and efficiency of the MLOps workflow on Vertex AI.

## Prerequisites

Before getting started, ensure the following prerequisites are in place:

- **Google Cloud Platform (GCP) Project ID:** Replace `Your-Project-ID` with your GCP Project ID.
- **GCP Region:** Replace `Your-Region` with the desired GCP region.
- **GCP Bucket URI:** Replace `Your-Bucket` with the URI of your Google Cloud Storage bucket.
- **Service Account Permissions:** Make sure your service account has the necessary permissions for accessing the Cloud Storage bucket.

```bash
# Set GCP Project ID
! gcloud config set project {PROJECT_ID}

# Allow service account to access Cloud Storage bucket
! gsutil iam ch serviceAccount:{SERVICE_ACCOUNT}:roles/storage.objectCreator $BUCKET_URI
! gsutil iam ch serviceAccount:{SERVICE_ACCOUNT}:roles/storage.objectViewer $BUCKET_URI
