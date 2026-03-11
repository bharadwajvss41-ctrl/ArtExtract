# ArtExtract Evaluation Task – Artwork Similarity

This repository contains my solution for the ArtExtract evaluation task for the HumanAI GSoC project:

"Painting in a Painting – Explore Hidden Images Beneath Paintings with Artificial Intelligence"

## Task

Build a model to find similarities between artworks (e.g., portraits with similar faces or poses) using the National Gallery of Art dataset.

## Dataset

The dataset used for this task is from the National Gallery of Art Open Data repository:

https://github.com/NationalGalleryOfArt/opendata

For this implementation, the **`published_images.csv`** file from the dataset was used.

This file contains metadata and image URLs for artworks in the NGA collection.

From this file:

- The **`iiifthumburl`** field was used to download artwork images
- Only images marked as **open access** were used
- A subset of images was sampled for experimentation

## Approach

The similarity system is implemented using a combination of:

- **YOLOv8** for object detection within artworks
- **CLIP embeddings** for semantic representation of detected objects
- **Cosine similarity** for retrieving visually similar artworks

Pipeline:

Painting Image  
→ YOLO object detection  
→ Crop detected objects  
→ CLIP embeddings  
→ Cosine similarity retrieval  

## Evaluation Metrics

The system performance was evaluated using:

- Cosine similarity between CLIP embeddings
- Top-K similarity retrieval
- Precision@K
- Qualitative evaluation of retrieved artworks

## Example Result

Query artwork: sculpture bust

The system successfully retrieved artworks containing statues and artifacts with similarity scores between **0.77–0.88**, demonstrating object-aware similarity retrieval.

## Notebook

The full implementation and experiments are available in:

`art_extract_similarity.ipynb`

A PDF version with outputs is also included.
