# 前端静态资源的部署

```
自动化部署
  静态资源文件与html模板文件分别部署
    什么是动态资源？什么是静态资源？
    先看一看构建出的dist目录里都有哪些文件
    为何要分开发布？放在一起发布会有什么问题？
    如果前端服务是一个规模很大的服务（一百多个实例），分组部署，在这种实际场景中会遇到什么问题？
      我们的前端自动化部署流程：
        自动化部署脚本的作用
        发布时，远程服务器上运行部署脚本，先对仓库master分支的源代码进行构建，生成静态资源文件和模板文件。
        每次发布上线时，先部署静态资源文件，再部署模板文件
        静态资源文件部署到华为云服务器，通过cdn访问静态资源
        静态资源文件为什么要增量发布？发布无风险，回滚快速
        模板文件打包为docker镜像，随后通过matrix容器云平台发布上线
```

#### Dynamic vs Static Resources

Before diving into the deployment process, it's essential to understand the difference between dynamic and static resources.

* **Dynamic Resources**: These are resources that are often changing and need to be computed or generated on-the-fly. Examples include personalized pages, search results, or user dashboards.
* **Static Resources**: In contrast, static resources are those that do not change frequently. These include images, CSS, and JavaScript files, which are usually cached by browsers for better performance.

#### The `dist` Directory

Let's examine the `dist` directory that is created after the build process:

* **Directory Contents**: This folder typically contains a structured set of files and folders that are ready to be deployed to a server, including both static assets and HTML template files.

#### Deployment Strategy

**Why Separate Deployments?**

Deploying static files and templates separately can:

* **Optimize Performance**: Static files can be served from a CDN, which reduces latency and improves load times for users globally.
* **Minimize Risks**: Updating static files independently reduces the risk of impacting dynamic content and allows for quicker rollback if necessary.

**Challenges in Large-Scale Deployments**

With a large-scale frontend service:

* **Scaling Issues**: Managing deployments across 100+ instances requires a robust automation system to prevent errors and ensure consistency.
* **Group Deployments**: This approach can introduce complexities in synchronization and might require special strategies for load balancing and version management.

#### Automated Deployment Process

1. **Deployment Script**: This script is responsible for automating the build and deployment tasks.
2. **Static Resource Deployment**: Static files are uploaded to a Huawei cloud server and distributed via CDN for optimal access.
   * **Incremental Updates**: These ensure that only changed files are updated, leading to safer deployments and faster rollbacks.
3. **Template Deployment**:
   * **Docker Packaging**: Template files are packaged into Docker images.
   * **Container Cloud Platform**: The Docker images are subsequently deployed through a matrix container cloud platform, ensuring scalable and consistent rollouts.
