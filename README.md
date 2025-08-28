# README.md

## Voice Model Training & Inference Environment

This repository contains trained voice models, their configurations, and a Jupyter Notebook for training and inference. It also provides full reproducibility instructions for setting up the environment.

---

### 🛠️ Environment Setup

The training environment is based on **Ubuntu 22.04** in a Docker container.

#### Docker Run Command
```bash
docker run -it --rm -p 8888:8888 ubuntu:22.04
```

#### Required System Packages
```bash
apt update
apt-get install mc -y
apt-get install python3.10 -y
apt-get install git git-lfs -y
apt-get install wget -y
git lfs install
apt install -y build-essential crossbuild-essential-arm64
apt install -y python3.10-dev
```

#### Python Virtual Environment
```bash
python3.10 -m venv venv
source ./venv/bin/activate
pip install jupyter ipywidgets
```

#### Launch Jupyter Notebook
```bash
jupyter notebook --ip=0.0.0.0 --port=8888 --allow-root
```

Access the UI at: `http://localhost:8888` with correct ip.

---

### 📝 Training Instructions

1. Open the Jupyter Notebook `micro_wake_word_generation.ipynb`.
2. Run the second cell to download `piper-sample-generator`.
3. **Edit `generate_samples.py`**:
   Replace:
   ```python
   torch.load(model_path)
   ```
   With:
   ```python
   torch.load(model_path, weights_only=False)
   ```
   This ensures backward compatibility with PyTorch 2.0+ (thanks to aegjoyce).

4. Proceed with model generation and training.
 
