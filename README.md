# 1、获得源代码

从 Github 上下载源码方式
```
git clone https://github.com/alibaba/nacos.git
cd nacos/
mvn -Prelease-nacos -Dmaven.test.skip=true clean install -U  
ls -al distribution/target/

// change the $version to your actual path
cd distribution/target/nacos-server-$version/nacos/bin
```

# 2、修改源代码
参考这篇文章：https://blog.csdn.net/qq_24101357/article/details/119318033?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~aggregatepage~first_rank_v2~rank_aggregation-3-119318033.pc_agg_rank_aggregation&utm_term=nacos%E4%BD%BF%E7%94%A8%E8%BE%BE%E6%A2%A6&spm=1000.2123.3001.4430

# 3、构建
进入到源代码目录执行：
```
mvn -Prelease-nacos -Dmaven.test.skip=true -Dpmd.skip=true -Dcheckstyle.skip=true clean install -U
```

# 4、获得构建完成后的工程
构建后，在 进入到源代码目录 中的 文件夹：
```
distribution/target/nacos-server-$version 下的  nacos 文件夹 就是最终的输出物。
```

# 5、完成了，那么启动 nacos

### 启动 nacos
sh startup.sh -m standalone
### 查看启动日志
tail -f /Users/zhangyunfei/git/1.tongweizhidian/支持达梦改造后的Nacos/nacos/logs/start.out

# 6、最后检查
看看数据库中，Nacos 已经使用 达梦数据库来存储了。

END

# 参考：
https://nacos.io/zh-cn/docs/quick-start.html

https://blog.csdn.net/qq_24101357/article/details/119318033?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~aggregatepage~first_rank_v2~rank_aggregation-3-119318033.pc_agg_rank_aggregation&utm_term=nacos%E4%BD%BF%E7%94%A8%E8%BE%BE%E6%A2%A6&spm=1000.2123.3001.4430

https://blog.csdn.net/denight_alan/article/details/103646314
