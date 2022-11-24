## 快速部署
### [](https://github.com/xiaoxinpro/nginx-proxy-manager-zh#1-%E7%8E%AF%E5%A2%83%E9%83%A8%E7%BD%B2) 1. 环境部署

安装Docker和Docker-compose
- [Docker官方安装文档（英文）](https://docs.docker.com/install/)
- [Docker-Compose官方安装文档（英文）](https://docs.docker.com/compose/install/)
- **[Docker和Docker-compose安装文档（中文）](https://blog.csdn.net/zhangzejin3883/article/details/124778945)**
### 2. 创建YAML文件

创建一个  `docker-compose.yml`  文件:

```
version: '3'
services:
app:
  image: 'chishin/nginx-proxy-manager-zh:latest'
  restart: always
  ports:
    - '80:80'
    - '81:81'
    - '443:443'
  volumes:
    - ./data:/data
    - ./letsencrypt:/etc/letsencrypt
```
	-
### [](https://github.com/xiaoxinpro/nginx-proxy-manager-zh#3-%E9%83%A8%E7%BD%B2%E8%BF%90%E8%A1%8C) 3. 部署运行

```
docker-compose up -d
```
### [](https://github.com/xiaoxinpro/nginx-proxy-manager-zh#4-%E7%99%BB%E5%BD%95%E7%AE%A1%E7%90%86%E9%A1%B5%E9%9D%A2) 4. 登录管理页面

当你的docker容器成功运行，使用浏览器访问 `81` 端口。 有些时候需要稍等一段时间。

[http://127.0.0.1:81](http://127.0.0.1:81/)

默认管理员信息:

```
Email:    admin@example.com
Password: changeme
```

使用这个默认用户登录后，系统会立即要求您修改详细信息和密码。
### [](https://github.com/xiaoxinpro/nginx-proxy-manager-zh#5-%E5%BF%AB%E9%80%9F%E5%8D%87%E7%BA%A7) 5. 快速升级

```
docker-compose down
docker-compose pull
docker-compose up -d
```

这个项目将自动更新任何数据库或其他要求，所以你不必遵循任何疯狂的指示。上面的这些步骤将提取最新的更新并重新创建docker容器。
## [](https://github.com/xiaoxinpro/nginx-proxy-manager-zh#%E6%9B%B4%E5%A4%9A) 更多
### [](https://github.com/xiaoxinpro/nginx-proxy-manager-zh#1-%E5%AE%98%E6%96%B9%E6%96%87%E6%A1%A3%E8%8B%B1%E6%96%87) 1. 官方文档（英文）

关于本应用的更多用法请访问官方文档：
- [项目源码](https://github.com/NginxProxyManager/nginx-proxy-manager)
- [项目官网](https://nginxproxymanager.com/)
- [安装手册](https://nginxproxymanager.com/setup/)
- [高级配置](https://nginxproxymanager.com/advanced-config/#best-practice-use-a-docker-network)
- [常见问题](https://nginxproxymanager.com/faq/#do-i-have-to-use-docker)
### [](https://github.com/xiaoxinpro/nginx-proxy-manager-zh#2-%E6%9B%BF%E6%8D%A2%E4%B8%AD%E6%96%87%E9%95%9C%E5%83%8F) 2. 替换中文镜像

当你使用官方示例的 `docker-compose` 时需要注意，将image镜像 `jc21/nginx-proxy-manager` 替换为 `chishin/nginx-proxy-manager-zh` 即可实现中文部署。
### [](https://github.com/xiaoxinpro/nginx-proxy-manager-zh#3-%E5%85%B3%E4%BA%8E%E4%B8%AD%E6%96%87%E9%95%9C%E5%83%8F) 3. 关于中文镜像

中文镜像并没有重新构建后端代码，由[Dockerfile-zh](https://github.com/xiaoxinpro/nginx-proxy-manager-zh/blob/develop-zh/docker/Dockerfile-zh)文件可以得知，中文镜像基于官方镜像替换前端代码来实现的，所以中文版本的全部功能与官方版本完全相同，只是显示界面的文字不同的区别。
## [](https://github.com/xiaoxinpro/nginx-proxy-manager-zh#%E6%8D%90%E8%B5%A0) 捐赠

如果您觉得本项目对你有帮助，欢迎给予我们一定的捐助来翻译项目的长期发展。