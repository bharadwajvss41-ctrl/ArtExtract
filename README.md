# ArtExtract Evaluation Task – Artwork Similarity

This repository contains my solution for the ArtExtract evaluation task for the HumanAI GSoC project:

"Painting in a Painting – Explore Hidden Images Beneath Paintings with Artificial Intelligence"

## Task
Build a model to find similarities between artworks using the National Gallery of Art open dataset.

Dataset:
https://github.com/NationalGalleryOfArt/opendata

## Approach

The similarity system is implemented using:

1. YOLOv8 for object detection in artworks
2. CLIP embeddings for semantic representation of detected objects
3. Cosine similarity to retrieve visually similar paintings

Pipeline:

Painting Image  
→ YOLO object detection  
→ Crop detected objects  
→ CLIP embeddings  
→ Cosine similarity search  

## Evaluation Metrics

The model performance is evaluated using:

- Cosine similarity between embeddings
- Top-K similarity retrieval
- Precision@K
- Qualitative evaluation of retrieved artworks

## Example Result

Query artwork: sculpture bust  
Retrieved artworks include statues and artifacts with similarity scores between **0.77–0.88**, demonstrating object-aware similarity retrieval.

## Notebook

The complete implementation and experiments are provided in the notebook:

`art_extract_similarity.ipynb`

A PDF version with outputs is also included.
