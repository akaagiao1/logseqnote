## 安装docker
- ### 更新安装必备条件和环境
  
  ```
  apt-get install sudo
  ```
  
  ```
  apt-get update && apt-get install -y wget vim
  ```
- ### 非大陆安装docker
  
  ```
  wget -qO- get.docker.com | bash
  ```
- ### 查看docker版本
  
  ```
  docker -v
  ```
  
  出现该内容证明安装成功
- ### 开机自启动
  
  ```
  systemctl enable docker
  ```
- ###
- ## 卸载Docker
  
  ```
  sudo apt-get purge docker-ce docker-ce-cli containerd.io
  ```
  
  ```
  sudo rm -rf /var/lib/docker
  sudo rm -rf /var/lib/containerd
  ```
- ### 非大陆Docker-compose安装
  
  ```
  sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
  ```
  
  ```
  sudo chmod +x /usr/local/bin/docker-compose
  ```
  
  ```
  docker-compose --version
  ```
  
  出现版本号证明安装成功。
- ## 
  
  十分的建议大家创建一个专门储藏docker相关的文件夹
  
  ```
  mkdir -p data/docker_data
  ```