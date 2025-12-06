Sign Language Detection App – Summary

App Overview

Flask-based web app for predicting hand signs from images.

Uses a trained CNN model (sign_language_model.h5).

Dockerized for easy deployment locally or on Railway.

Input Image Requirements

Size: Must match model’s training size (e.g., 28×28 pixels).

Color: Grayscale if model trained on grayscale.

Preprocessing Steps:

Read image from upload.

Convert to grayscale.

Resize to 28×28.

Normalize pixel values (divide by 255).

Add batch and channel dimensions → shape (1, 28, 28, 1).

Flask App Routes

/ → Home page with image upload form.

/predict → Receives uploaded image, preprocesses it, predicts sign, and returns result.

Docker Deployment

Dockerfile uses TensorFlow base image.

Exposes port 5000.

Flask app must run on host="0.0.0.0" for external access.

Railway Deployment

Push project to GitHub.

Connect GitHub repo to Railway → auto-build and deploy Docker image.

Public URL serves the app online.

GitHub README

Explains installation, usage, Docker instructions, API endpoint, and project structure.

Key Notes

Always preprocess uploaded images to match model input.

Uploading random-sized images without resizing will break the prediction.

Docker + Railway make deployment portable and accessible online.
