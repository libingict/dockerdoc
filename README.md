# dockerdoc
## Docker Overview 
docker 文档的翻译版本
## Docker
Docker是个开发的平台，支持应用的开发，部署和运行。Docker的功能是更快的交付应用。Docker支持基础设施和上层开发的应用分离，基础设施和架构可看做一个可管理的应用程序。有助于代码更快的开发、部署、测试，缩短代码开发和运行之间的周期。
内核可容器化与工作流和工具化结合之后，Docker帮助开发者管理和部署应用。

Docker的核心任何程序都可以安全的运行在容器中，容器之间隔离。这种安全隔离允许一台主机上运行多个容器。容器是轻量级概念，它的启动不需要hypervisor, 能够更多的without the extra load of a hypervisor, means you can get more out of your hardware.
-	程序（及配套程序）运行在容器中
- 将容器分发和装载给开发团队，以便继续开发和测试
- 无论生产环境是本地数据中心或者云，应用很好部署上去。

## Docker Engine
Docker engine(引擎)是服务器-客户端的应用，主要部件包括：
- Daemon process：一个长时间运行的程序，作为server。Daemon创建和管理Docker对象，Docker对象包括images，containers, networks, data volumes等。
- REST API: 接口，与daemon交互和指导daemon运行。
- CLI：命令行接口。CLI 通过命令或者脚本通过调用REST API控制Docker daemon的实际运行。
 
## Docker’s architecture

Client 与daemon交互，daemon负责编译、运行和分发container。Client和daemon能运行在同一个系统上,Docker client能连接到远程的daemon上。Client与daemon通过socket或者RESTful API通信。 
 
### Docker daemon

Daemon 在主机上运行，用户通过client与daemon交互。
Docker client 是“docker”可运行命令的形式，是Docker主要的用户接口。接收用户命令，与daemon反复通信。
Docker 内部三个组件
- Docker images镜像
- Docker registries镜像仓库
- Docker containers 容器

### Docker images
一个Docker images 是一个只读镜像。譬如，一个镜像可以是安装了apache和web应用的Ubuntu操作系统。镜像用来创建容器。Docker编译新的镜像和更新已有镜像的命令非常简单。镜像是Docker的构建组件。
### Docker registries
仓库存放镜像。有公共和私有仓库用来上传和下载镜像。公共的镜像仓库由[Docker hub](http://hub.docker.com/) 提供。Docker HUB存放海量已有镜像供下载。镜像仓库包含自己创建的和他人创建的镜像。Docker registries是Docker的分发组件。
### Docker containers
容器类似目录。容器包含了程序运行需要的所有内容。每个容器由一个镜像创建。容器能运行、开始、停止、移动和删除。容器是被隔离的安全的程序平台。容器是Docker中的运行组件。
## Docker镜像的工作
每个镜像包含多层。Docker利用union file systems将多层组合成单独的镜像。

