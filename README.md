> 客户端 `dubbo` 接入大众点评 `CAT` 监控平台

安装到本地仓库命令：

```sh
mvn clean install
```

客户端依赖声明方式：

```xml
<!-- 客户端dubbo接入CAT -->
<dependency>
    <groupId>org.fanlychie</groupId>
    <artifactId>cat-client-dubbo</artifactId>
    <version>1.0.0</version>
</dependency>
```

---

或者使用我托管的仓库`fanlychie-maven-repo`直接声明依赖：

```xml
<repositories>
    <repository>
        <id>fanlychie-maven-repo</id>
        <url>https://raw.github.com/fanlychie/maven-repo/releases</url>
    </repository>
</repositories>
<dependencies>
    <!-- 客户端dubbo接入CAT -->
    <dependency>
        <groupId>org.fanlychie</groupId>
        <artifactId>cat-client-dubbo</artifactId>
        <version>1.0.0</version>
    </dependency>
</dependencies>
```

---

接入方式：

在`dubbo`生产者端或消费者端的配置文件中，如消费者端配置文件中，加入过滤器配置：

```xml
<dubbo:consumer filter="CatClientFilter"/>
```

生产者端则为：

```xml
<dubbo:provider filter="CatClientFilter"/>
```

建议配置在消费者端就可。

---

效果图（接入前）：

![image](https://raw.githubusercontent.com/fanlychie/mdimg/master/cat-client-dubbo-pre.png)

效果图（接入后）：

![image](https://raw.githubusercontent.com/fanlychie/mdimg/master/cat-client-dubbo-post.png)