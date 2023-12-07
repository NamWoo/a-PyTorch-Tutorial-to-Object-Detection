# Unity install

```bash
#https://forum.unity.com/threads/how-to-install-unity-hub-3-4-1-in-ubuntu-22-04-lts.1311612/

sudo sh -c 'echo "deb https://hub.unity3d.com/linux/repos/deb stable main" > /etc/apt/sources.list.d/unityhub.list'
wget -qO - https://hub.unity3d.com/linux/keys/public | sudo tee /etc/apt/trusted.gpg.d/myrepo.asc

sudo apt-get update
sudo apt-get install -y unityhub

```


# command check

```bash
#over 100MB -> wget --no-check-certificate ‘https://docs.google.com/uc?export=download&id=1bvJfF6r_zYl2xZEpYXxgb7jLQHFZ01Qe’ -O checkpoint_ssd300.pth.tar
#under 100MB
wget --no-check-certificate 'https://docs.google.com/uc?export=download&id=1LG989tBhA4H_qRIEDuiAI2kkmExZsehn' -O input.zip

#over 100MB
wget -load-cookies ~/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget -quiet -save-cookies ~/cookies.txt -keep-session-cookies -no-check-certificate 'https://docs.google.com/uc?export=download&id={1bvJfF6r_zYl2xZEpYXxgb7jLQHFZ01Qe}' -O- | sed -rn 's/.confirm=([0-9A-Za-z_]+)./\1\n/p')&id={1bvJfF6r_zYl2xZEpYXxgb7jLQHFZ01Qe}" -O {checkpoint_ssd300.pth.tar} && rm -rf ~/cookies.txt

```


# set


https://velog.io/@minukiki/Ubuntu-20.04%EC%97%90-OpenCV-4.4.0-%EC%84%A4%EC%B9%98
https://rodosingh.medium.com/using-cmake-to-build-and-install-opencv-for-python-and-c-in-ubuntu-20-04-6c5881eebd9a
https://github.com/opencv


---

# ros

https://docs.ros.org/en/foxy/Installation/Alternatives/Ubuntu-Development-Setup.html
Ubuntu Linux - Focal Fossa (20.04)

https://docs.ros.org/en/iron/Installation/Ubuntu-Install-Debians.html
Ubuntu Linux - Jammy Jellyfish (22.04)


---

# cuda

https://ingu627.github.io/tips/install_cuda_linux/#fn:4

https://developer.nvidia.com/cudnn
https://developer.nvidia.com/rdp/cudnn-archive

---

pip install pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cudatoolkit=11.3 -c pytorch
pip install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 --extra-index-url https://download.pytorch.org/whl/cu113

---
#https://developer.nvidia.com/cuda-11.0-download-archive?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=2004&target_type=deblocal


wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-ubuntu2004.pin
sudo mv cuda-ubuntu2004.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget http://developer.download.nvidia.com/compute/cuda/11.0.2/local_installers/cuda-repo-ubuntu2004-11-0-local_11.0.2-450.51.05-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu2004-11-0-local_11.0.2-450.51.05-1_amd64.deb
sudo apt-key add /var/cuda-repo-ubuntu2004-11-0-local/7fa2af80.pub
sudo apt-get update
sudo apt-get -y install cuda


