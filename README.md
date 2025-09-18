# biped_robot

## Installation for vast

useradd -m -s /bin/bash alberic
apt-get update && apt-get install -y sudo
usermod -aG sudo alberic
passwd alberic
su alberic


git clone https://github.com/AlbericDeLajarte/biped_robot.git

conda install -n base -c conda-forge mamba

### Install HumanoidVerse
cd biped_robot/HumanoidVerse/
mamba create -n hsim python=3.10
mamba activate 

or
conda init
source ~/.bashrc
conda create -n hsim python=3.10
conda activate hsim


### Install IsaacSim / IsaacLab
cd
wget -O isaacsim.zip "https://download.isaacsim.omniverse.nvidia.com/isaac-sim-standalone-5.0.0-linux-x86_64.zip"

mkdir -p ${HOME}/isaacsim
unzip isaacsim.zip -d ${HOME}/isaacsim

echo -e '\n# Isaac Sim environment variables\nexport ISAACSIM_PATH="${HOME}/isaacsim"\nexport ISAACSIM_PYTHON_EXE="${ISAACSIM_PATH}/python.sh"' >> ~/.bashrc

source ~/.bashrc
