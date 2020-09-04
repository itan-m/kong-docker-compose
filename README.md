# kong + konga + docker
轻松搭建kong环境，并基于postgres做数据持久化

## 注意点
depends_on是在依赖容器启动后再启动自身容器，而非等待依赖容器启动结束。
由于kong和konga都依赖postgres容器，所以需等postgres容器启动结束后，kong和konga容器才能运行成功，此处用了restart: on-failure或restart: always来反复重试直到容器顺利运行。

## 参考站点
https://qhh.me/2019/08/14/%E5%9F%BA%E4%BA%8E-docker-compose-%E5%AE%B9%E5%99%A8%E5%8C%96%E6%9E%84%E5%BB%BA-Kong-%E5%BE%AE%E6%9C%8D%E5%8A%A1%E7%BD%91%E5%85%B3%E5%B9%B3%E5%8F%B0/

https://gist.github.com/pantsel/73d949774bd8e917bfd3d9745d71febf

https://github.com/Kong/docker-kong/blob/master/compose/docker-compose.yml

[kong/konga使用教程](https://www.jianshu.com/p/83cb4c79a1bd)