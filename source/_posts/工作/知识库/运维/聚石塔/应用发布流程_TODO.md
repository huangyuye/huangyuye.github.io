# 聚石塔—容器部署平台

 聚石塔提供了从资源采购、应用部署到跟阿里巴巴业务链接一整套解决方案。



## 名词术语

- VPC(Virtual Private Cloud)：私有云
  - **对于基础架构服务（IaaS），云就是指资源池。**你或许听过公有云（Public Cloud），私有云（Private Cloud），混合云（Hybrid Cloud）。不过，VPC不属于这三种云中任一种。
  - 这是一种**运行在公有云上，将一部分公有云资源为某个用户隔离出来，给这个用户私有使用的资源的集合。**
  - 向用户提供的隔离资源的集合
- ECS（*Elastic Cloud Server*）：弹性云服务器



## 使用步骤

1. 创建集群
   - 创建VPC、购买ECS、创建集群、添加ECS到集群
2. 创建应用
3. 配置环境
4. 应用发布
5. 流量接入
   - 购买SLB、新建SLB流量接入、Ingress接入



## 应用service访问

**多种方式**

1. 若实例部署配置Deployment如下

```yaml
metadata:
  # 部署名
  #name: ecrp-sg-web
  labels:
    app.kubernetes.io/project: ecrp
    app.kubernetes.io/name: sg-h5
```

集群内访问方式：${ app.kubernetes.io/name}.${app.kubernetes.io/projec}

2. 配置集群服务，获得ClusterIP，使用ClusterIP



## 参考链接

- 聚石塔团队官网：https://www.yuque.com/fczggw/wu7u0k/gfhekf
- 什么是VPC：https://zhuanlan.zhihu.com/p/33658624
- k8s官网：https://kubernetes.io/zh/docs/concepts/services-networking/ingress/#%E6%9C%AF%E8%AF%AD
- 《NodePort vs LoadBalancer vs Ingress》：
  - https://blog.csdn.net/yang75108/article/details/101101384
  - https://blog.csdn.net/yang75108/article/details/101268208