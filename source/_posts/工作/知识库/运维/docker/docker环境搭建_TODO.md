- docker 镜像仓库配置

- docker 镜像搜索

  ```shell
  $ docker search activemq 
  ```

- docker 镜像拉取

  ````shell
  $ docker pull webcenter/activemq
  ````

- docker 容器运行

  ```shell
  # -d 后台运行
  # --name 指定容器名称
  # -p 端口映射
  # 最后指定镜像
  $ docker run -d --name activemq -p 61617:61616 -p 8162:8161 webcenter/activemq
  ```

- 进入容器

  ```shell
  # -i：表示以“交互模式”运行容器
  # -t：表示容器启动后会进入其命令行 
  # [/bin/bash] 表示执行容器内的该命令
  $ docker exec -it activemq /bin/bash 
  ```



