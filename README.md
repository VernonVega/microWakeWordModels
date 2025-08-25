# microWakeWordModels

Took some effort to make it work for me but finally. 

# Steps:
Docker container with ubuntu:22.04 (and exposed port for jupyter notebook, 8888 by default)

apt update
apt-get install mc -y
apt-get install python3.10 -y
apt-get install git git-lfs
apt-get install wget
git lfs install
apt install -y build-essential crossbuild-essential-arm64
apt install -y python3.10-dev
python3.10 -m venv venv
source ./venv/bin/activate
pip install jupyter
pip install ipywidgets

jupyter notebook
----------
After downloading piper-sample-generator need to edit it's generate_samples.py. Replace torch_model = torch.load(model_path) to torch_model = torch.load(model_path, weights_only=False) (thanks to aegjoyce)
