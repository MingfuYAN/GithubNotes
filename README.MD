# 安装 Docker Compose

```shell
sudo curl -L "https://github.com/docker/compose/releases/download/v2.27.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

# 安装miniconda

```shell
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh

mkdir -p miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p miniconda3
rm -rf miniconda3/miniconda.sh

miniconda3/bin/conda init bash
```

# Label Studio
```shell
docker run -it -p 8080:8080 -v $(pwd)/mydata:/label-studio/data heartexlabs/label-studio:latest
```

```shell
python3 -m venv env
source env/bin/activate
sudo apt install python3.9-dev
python -m pip install label-studio
```

# ubuntu 电源管理

```shell
sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target
echo -1 | sudo tee /sys/bus/usb/devices/*/power/autosuspend

```

```shell
# 修改为图形界面
systemctl set-default graphical.target

# 修改为命令行界面
sudo systemctl set-default multi-user.target
```

# zsh
```shell
sudo apt install zsh autojump -y
# 设成默认shell
chsh -s $(which zsh)
# 安装 oh my zsh
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# 下载插件
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

ZSH_THEME="junkfood"
plugins=(git zsh-autosuggestions zsh-syntax-highlighting autojump)
/home/mfyan/miniconda3/bin/conda init zsh
```
