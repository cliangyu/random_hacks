## 🛠 Tools

### 🕸️ Computer Network

##### WDS Bridging Checklist

1. Reset WDS settings of the extended router, because the channel of the main router might has changed. If can't reset, reset the whole extended router.

2. Follow the instructions thoroughly. 

How to configure WDS function on TP-Link Wireless Routers(green UI)
https://www.tp-link.com/us/support/faq/227/

Remember to 1) change the LAN IP address of the extended router; 2) set the channel the same as the main router; 3) turn off the DHCP of the extened router.

3. If cannot connect with Ethernet LAN only, while wireless connection succeeds, it should be problems with desktop side. Follow the insturctions thoroughly.

Resetting Network Devices and Network Stack
https://www.intel.com/content/www/us/en/support/articles/000058982/wireless/intel-killer-wireless-products.html

```
Type ipconfig /release and press Enter.

Type ipconfig /flushdns and press Enter.

Type ipconfig /renew and press Enter. (This will stall for a moment.)
```



<br>

##### Download files from Google drive

The download method is from [gdown](https://github.com/wkentaro/gdown). To install the project, you can type the following command.

```
pip install gdown
```
Then you can use gdown to download files from Google drive as follow(just an example).
```
gdown https://drive.google.com/u/0/uc?id=1gxXalk9O0p9eu1YkIJcmZta1nvvyAJpA&export=download
```
Plus, if you use shell  ```zsh```, you need to type as follow.
```
gdown "https://drive.google.com/u/0/uc?id=1gxXalk9O0p9eu1YkIJcmZta1nvvyAJpA&export=download"
```

<br>

##### Set up Docker on Linux OS

1. Download the latest DEB package. (You can check the detail in [Website](https://docs.docker.com/desktop/install/ubuntu/))

2. For non-Gnome Desktop environments, ```gnome-terminal``` must be installed:
    ```
    sudo apt install gnome-terminal
    ```

3. Uninstall the tech preview or beta version of Docker Desktop for Linux. Run:
    ```
    sudo apt remove docker-desktop
    ```

4. For a complete cleanup, remove configuration and data files at ```$HOME/.docker/desktop```, the symlink at ```/usr/local/bin/com.docker.cli```, and purge the remaining systemd service files.
    ```
    rm -r $HOME/.docker/desktop
    sudo rm /usr/local/bin/com.docker.cli
    sudo apt purge docker-desktop
    ```

5. Set up Docker’s package repository. (**this step is indispensable.**)
    ```
    sudo apt install -y ca-certificates curl gnupg lsb-release
    sudo mkdir -p /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    sudo apt update -y
    ```

6. Install the package
    ```
    sudo apt-get update
    sudo apt-get install ./docker-desktop-<version>-<arch>.deb
    ```

7. Check Docker's version
    ```
    docker --version
    ```

<br>


##### How to change docker's root directory([details](https://zhuanlan.zhihu.com/p/95533274))
1. stop the docker.
    ```
    systemctl stop docker
    ```
2. check docker's information.
    ```
    docker info
    ```
3. change the file ```/etc/docker/daemon.json```. (you need to use ```sudo```)
    
    **Attention: you have to make a new directory as the data root!!!**
    ```
    {
        "data-root": "/data/docker"
    }
    ```
4. restart the docker.
    ```
    systemctl restart docker
    ```
5. check the latest information
    ```
    docker info
    ```
    
<br>

#### CUDA Init Error

nvidia-smi 那边显示的是 display driver，nvcc -V 显示的才是跟 pytorch 相关的

Install [here](https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=20.04&target_type=deb_network)

<br>

##### How to delete docker's image

1. check the docker's images and find the target image ID (front 3 words is okay).
    ```
    docker images
    ```
2. try to delete the image (e.g. ```eca```)
    ```
    docker rmi eca
    ```
3. usually, the image couldn't be deleted directly. you need to delete the container first.

   check all containers.
   ```
   docker ps -a
   ```
   find the target container ID, front 3 words is okay. (e.g. ```39a```)

   stop the container (if it's running).
   ```
   docker stop 39a
   ```
   delete the container.
   ```
   docker rm 39a
   ```
4. then, delete the image.
   ```
   docker rmi eca
   ```

##### When I suck with linux settings but can't reboot
logout all the processes
pkill -SIGKILL -u chen24
