# 3D Road Lane and Traffic Detection - Training Script

This folder contains a portable training + visualization script that:
- extracts a dataset zip,
- trains a small CNN classifier,
- saves the best model,
- produces pseudo-3D visualizations (Sobel-based depth maps).

Files:
- code/train_and_visualize.py  -- main script
- requirements.txt             -- Python dependencies
- .gitignore                   -- recommended git ignores
- .gitattributes               -- sample LFS patterns

Quick start (local / Colab):
1. Install dependencies:
   pip install -r requirements.txt

2. Run (example):
   python code/train_and_visualize.py \
     --zip_path /path/to/data_road.zip \
     --extract_dir ./dataset \
     --model_out models/cnn_3d_classifier.h5 \
     --epochs 5 \
     --num_samples 5 \
     --save_vis outputs/visualization.png

Notes:
- Do NOT commit large zipped datasets or trained models directly to the repo if they exceed GitHub's 100 MB limit.
  Use Git LFS (git lfs track "*.h5") for model files or attach large artifacts to a GitHub Release.
- If running on a headless CI server, the script saves the visualization as a PNG rather than attempting to display it.

Reproducibility:
- Use the --seed flag to control randomness.
- Provide a small representative sample subset in the repo for demos; link to full dataset externally.

License / Contact:
- Repo owner: @Pardhu4777
