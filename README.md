Food Item Detection Web App
Introduction
This project is part of a series of computer vision projects focusing on object detection. The application developed here is a web app designed to accept images containing food items. If the system successfully identifies any of the food items within the picture, it will return a labeled version of the image with the detected items highlighted. If no recognizable food items are detected, the application will respond by indicating that the food items cannot be identified.

In this project, we focus on detecting 12 specific types of food items using the YOLO (You Only Look Once) model for object detection. The project primarily serves as a demonstration of how object detection concepts can be applied in a real-world scenario using computer vision techniques.

Concepts
The key concepts explored and implemented in this project include:

Computer Vision: Techniques for analyzing and interpreting visual data from the world around us, specifically in the context of identifying objects within images.
YOLO: A state-of-the-art object detection algorithm that processes images and predicts the bounding boxes and labels for detected objects in a single pass through the network.
Object Detection: The process of identifying specific objects within an image and marking them with bounding boxes and class labels.
Tools
The following tools and technologies were used to build the project:

Google Drive: Used for storing training data and models in a centralized location, facilitating easy sharing and access across environments.
YOLO Library: The main tool for the object detection model, providing pre-trained weights and support for training our own custom models on new datasets.
DVC (Data Version Control): Used for pipeline building and data versioning, ensuring that data, models, and code are all version-controlled and can be reproduced.
MLflow: Used for managing model versioning and registry, allowing for tracking model metrics and managing deployments.
Flask: A lightweight web framework for serving the model and application to end-users via an HTTP interface.
Project Structure
The project follows a modular and expandable structure to support both the development and production environments. The components are organized in such a way that additional features, services, and compute resources can easily be added.

Here is an overview of the main folders and files:

notebook/: Contains random experiments, ideas, and exploratory analysis using Jupyter notebooks.
src/
infra/: Set up for the required compute resources and configuration of services such as Google Drive, DVC, and MLflow.
remote-storage/: Configuration files for external storage (e.g., Google Drive).
mlflow/: Directory for model versioning and tracking MLflow configurations.
dvc/: All configurations and pipeline scripts related to DVC for data management and versioning.
setup/: Setup scripts for initializing project resources.
application/: Contains the core application logic, including the model inference code and Flask server code.
userapp/: Houses the front-end interface that users interact with to upload images and receive predictions.
pipeline/: Scripts for creating the end-to-end pipeline, from data processing to inference.
setup/: Initial setup scripts for application-specific configurations and model loading.
variables/: Contains shared infrastructure and application configurations used across different components.
Installation and Setup
Clone the repository to your local machine:

bash
Copy code
git clone <repository_url>
cd <repository_name>
Install the required Python packages:

bash
Copy code
pip install -r requirements.txt
Set up DVC for data versioning and tracking:

bash
Copy code
dvc init
Configure remote storage for DVC:

bash
Copy code
dvc remote add -d gdrive <remote_drive_url>
Configure MLflow for model versioning:

bash
Copy code
mlflow server
Run the Flask application:

bash
Copy code
flask run
Access the application at http://localhost:5000.

project_name: food-item-detection
version: 1.0.0

tools:
  - name: YOLO
    description: Object detection model used for food item detection
  - name: DVC
    description: Data version control for pipeline building and data tracking
  - name: MLflow
    description: Model tracking and versioning
  - name: Flask
    description: Web framework for serving the application
  - name: Google Drive
    description: Remote storage for dataset and model files

project_structure:
  notebook: 
    description: Jupyter notebooks for random experiments and ideas
  src:
    infra:
      description: Setup for compute resources and service configurations
    remote-storage:
      description: Remote storage configuration for data and model files
    mlflow:
      description: MLflow configurations for model tracking
    dvc:
      description: DVC pipelines for data versioning and management
    setup:
      description: Scripts to set up the project infrastructure
  application:
    userapp:
      description: Application logic and model inference code
    pipeline:
      description: End-to-end pipeline setup for data processing to model inference
    setup:
      description: Application-specific setup and configuration scripts
  variables:
    description: Shared configurations for infrastructure and application

dependencies:
  - python==3.8
  - flask==2.1.2
  - mlflow==1.21.0
  - yolo==5.0
  - dvc==2.8.3
