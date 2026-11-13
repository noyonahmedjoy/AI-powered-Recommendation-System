# Movie Recommendation Experiments

A small notebook-based project for exploring movie ratings and recommendation techniques. It contains two separate experiments: one compares movies through user rating patterns, and the other demonstrates text generation with a pretrained language model.

## What is included

### Rating-based recommendations

`AIRecoSystem.ipynb` combines the collected ratings with their movie titles, summarizes average ratings and rating counts, then compares movies using correlations across users. Its example uses *Star Wars (1977)* and filters out movies with 100 or fewer ratings to reduce the effect of sparse data.

### Language-model example

`AIRecoSystem_LLM.ipynb` prompts GPT-Neo 1.3B to generate recommendations from a short, hard-coded movie list. This is a separate demonstration; it does not train a model on, or automatically retrieve recommendations from, the collected ratings files.

## Collected data

The project’s dataset has been collected and is available in `datasets/`:

- `u.data` contains user IDs, movie IDs, ratings, and timestamps.
- `Movie_Id_Titles.txt` maps movie IDs to movie titles.

## Getting started

Install Jupyter and the packages used by the rating-based notebook:

```bash
pip install jupyter numpy pandas matplotlib seaborn
```

To run the language-model notebook, install its additional dependencies:

```bash
pip install torch transformers datasets accelerate
```

The LLM notebook downloads GPT-Neo 1.3B from Hugging Face when run and sends generation inputs to CUDA. Use a compatible CUDA-enabled PyTorch setup and GPU for that notebook.

Open either notebook in Jupyter and run its cells from top to bottom. The rating-based notebook reads `u.data` and `Movie_Id_Titles.txt` from its current working directory. Start it with `datasets/` as the working directory, or change the two file paths in the notebook to `datasets/u.data` and `datasets/Movie_Id_Titles.txt`.
