# Counterfeit Drug Detection — Synthetic Sample Generator

This project uses **Stable Diffusion XL (SDXL)** to generate synthetic drug images from authentic samples. The purpose is to augment a dataset used to train a machine learning model for detecting counterfeit medications from a med packaging context.

By generating high-quality synthetic images that resemble real samples, we improve the variety and generalization of training data—especially when real counterfeit examples are limited or unavailable.

## Project Purpose

To build a reliable counterfeit drug detection model, it's important to train on a broad and diverse dataset. This project expands on authentic images using generative AI, helping to simulate realistic counterfeit variations and improve model performance.

## Dataset Source

Authentic drug images are sourced from:

**druga Dataset**  
Roboflow Universe  
Link: [https://universe.roboflow.com/test-z3p84/druga](https://universe.roboflow.com/test-z3p84/druga)  
Visited on: 2025-07-29

```bibtex
@misc{
druga_dataset,
title = { druga Dataset },
type = { Open Source Dataset },
author = { test },
howpublished = { \url{ https://universe.roboflow.com/test-z3p84/druga } },
url = { https://universe.roboflow.com/test-z3p84/druga },
journal = { Roboflow Universe },
publisher = { Roboflow },
year = { 2024 },
month = { nov },
note = { visited on 2025-07-29 },
}

## How It Works

- Load a reference image from the authentic dataset.
- Use the `StableDiffusionXLImg2ImgPipeline` from Hugging Face to generate new images based on the input.
- The pipeline applies image-to-image diffusion to create visually similar, but distinct, images that simulate natural variations.
- These synthetic images are saved and added to the training dataset for counterfeit detection.
- Even if the exact internals of `img2img` are abstract, it essentially reimagines the original image in a new but controlled way using the power of generative diffusion models.

## Requirements

- Python 3.9+
- `diffusers`
- `transformers`
- `torch` with CUDA support
- `huggingface_hub`
- `Pillow`
- Google Colab (recommended for setup and GPU access)

### GPU Requirements (if running locally)

- A high-memory GPU such as NVIDIA RTX 3090, A100, or equivalent
- At least 16 GB of VRAM
- CPU-only environments are not recommended due to the model’s size and performance requirements

## License and Disclaimer

This project is for **research and educational purposes only**. Please ensure you comply with:

- The licensing terms of the Roboflow dataset used
- The terms of use of Hugging Face and Stability AI models
- Applicable laws and ethical guidelines

Do **not** use the generated outputs or this pipeline for medical decisions or real-world drug validation.

