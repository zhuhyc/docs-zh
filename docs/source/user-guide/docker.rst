Docker
-----------------------

在docker目录下，run_docker.sh工具用来方便运行ChubaoFS docker-compose试用集群。

执行下面的命令，可完全重新创建一个最小的ChubaoFS集群。注意的是**/data/disk**是数据根目录，至少需要30GB大小空闲空间。

.. code-block:: bash

    $ docker/run_docker.sh -r -d /data/disk

客户端启动成功后，在客户端docker容器中使用`mount`命令检查目录挂载状态：

.. code-block:: bash

    $ mount | grep chubaofs

在浏览器中打开http://127.0.0.1:3000，使用`admin/123456`登录，可查看chubaofs的grafana监控指标界面。

或者使用下面的命令分步运行:

.. code-block:: bash

    $ docker/run_docker.sh -b
    $ docker/run_docker.sh -s -d /data/disk
    $ docker/run_docker.sh -c
    $ docker/run_docker.sh -m

更多命令:

.. code-block:: bash

    $ docker/run_docker.sh -h

监控的Prometheus和Grafana相关配置位于`docker/monitor`目录下。
