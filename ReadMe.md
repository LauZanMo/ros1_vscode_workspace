# ROS1 vscode workspace

> author：刘正武
>
> 基于vscode的ROS开发模板

## 说明

该仓库为vscode里开发ROS的模板，需要安装以下vscode插件：

- ms-vscode.cpptools-extension-pack
- ms-iot.vscode-ros
- VisualStudioExptTeam.vscodeintellicode
- betwo.b2-catkin-tools

额外插件(可选)：

- nvidia.nsight-vscode-edition(nvidia开发)
- zoneorz.ros-package-variable(ROS调试插件)
- pijar.ros-snippets(launch文件自动补全)
- ms-vscode-remote.vscode-remote-extensionpack(微软的远程开发插件)

## docker开发环境(可选)

需要进行docker开发则需要参考[教程](https://athackst.github.io/vscode_ros2_workspace/)

- docker安装

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

- nvidia docker安装(可选)

```bash
distribution=$(. /etc/os-release;echo $ID$VERSION_ID) \
   && curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add - \
   && curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
sudo apt-get update
sudo apt-get install -y nvidia-docker2
sudo systemctl restart docker
```

**注意**：需要使用nvidia docker需要在[devcontainer.json](.devcontainer/devcontainer.json)中取消注释gpu的内容