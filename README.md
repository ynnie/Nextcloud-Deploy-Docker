# Nextcloud-Deploy-Docker

Using this project to deploy Nextcloud service (nginx-fdm-postgres-redis-cron) on your server. The redis and cron are optional, installing them may improve the performance. If you don't want them, just check out the older commit.

## How to use:

### 0. Install docker and docker-compose

You must install docker and docker-compose before using this repo.

### 1. Clone this repo

```shell
git clone https://github.com/ynnie/Nextcloud-Deploy-Docker.git
```

### 2. Set database password

Open `db.env` file and modify `POSTGRES_PASSWORD` item.

### 3. Set your local data directory and hostname

Open and modify `.env` file.

```shell
# Local data directory
DATA_DIR_DB=/XXX/Nextcloud/db # The local directory for database.
DATA_DIR_APP=/XXX/Nextcloud/app # The local directory for Nextcloud.
DATA_DIR_CERT=/XXX/Nextcloud/certs # The local directory for certificates, ignore this if you don't need https.
DATA_DIR_VHOST=/XXX/Nextcloud/vhost.d # The local directory for vhost.d.
DATA_DIR_HTML=/XXX/Nextcloud/html # The local directory for html.

# Host name
HOST_NAME=cloud.xxx.com # Host name, set to you domain name or IP address.
```

**Note: **

You need to create above folders by yourself.  If you have a domain and a SSL certificate, you need to setup the `HOST_NAME` in `.env` file and put your certificate files in the `DATA_DIR_CERT` folder. The certificate files should be nginx format and named as `your_domain.crt` and `your_domain.key`. If you don't have a domain, you can set  `HOST_NAME` as you server's IP address.

### 4. Deploy with docker compose

Create and setup docker containers with docker-compose.

```shell
docker-compose up -d
```

At this point, you should be able to access your Nextcloud site with your browser. 

# 部署Nextcloud服务

使用本项目可以利用docker-compose部署Nextcloud服务（nginx-fdm-postgres-redis-cron）。 其中，redis和cron是可选项目，不配置这两项Nextcloud也可以正常工作，但是配置这两项对性能会有提升。如果你不想配置它们，可以check out之前的commit。

## 使用方法:

### 0. 安装 docker 和 docker-compose

你必须提前将docker和docker-compose安装配置好。本项目不包含相关配置。

### 1. Clone本项目

```shell
git clone https://github.com/ynnie/Nextcloud-Deploy-Docker.git
```

### 2. 设置数据库密码

Open `db.env` file and modify `POSTGRES_PASSWORD` item.

打开`db.env`文件，将``POSTGRES_PASSWORD` `配置为你的希望的数据库密码。

### 3. 设置本地数据目录和Hostname

修改 `.env` 文件：

```shell
# Local data directory
DATA_DIR_DB=/XXX/Nextcloud/db # The local directory for database.
DATA_DIR_APP=/XXX/Nextcloud/app # The local directory for Nextcloud.
DATA_DIR_CERT=/XXX/Nextcloud/certs # The local directory for certificates, ignore this if you don't need https.
DATA_DIR_VHOST=/XXX/Nextcloud/vhost.d # The local directory for vhost.d.
DATA_DIR_HTML=/XXX/Nextcloud/html # The local directory for html.

# Host name
HOST_NAME=cloud.xxx.com # Host name, set to you domain name or IP address.
```

**注意: **

在配置好上述目录之后，你需要自行创建这些目录。如果你有自己的域名和SSL证书，将`HOST_NAME`设置为你的域名地址，然后把证书文件放入`DATA_DIR_CERT`中。证书必须是`nginx`格式，并命名为`your_domain.crt` 和 `your_domain.key`。如果你没有自己的域名，则可以将`HOST_NAME`设置为你服务器的IP地址。

### 4. 使用docker-compose部署

利用docker-compose完成docker容器的创建和部署：

```shell
docker-compose up -d
```

至此，你应该已经可以通过浏览器访问你的Nextcloud网站了。

