## Link 
- [GitHub](https://github.com/)
- [泡在网上的日子](http://www.jcodecraeer.com/)
- [Android开发技术周报](http://www.androidweekly.cn/)
- [干货集中营](http://gank.io/)


## 架构
1. 保存Log信息
    > 以下为log4j1的日志管理，在android 6.0 一下能正常使用，时候更加高级的胃log4j2,持续跟新
2. 使用ARouter实现页面跳转
    > https://github.com/alibaba/ARouter
    
    
## Dagger常见问题
1. 未生成apt目录
    需要run project 才能生成 build 是不想生效的
2. 生成了apt 目录 但没有任何文件
    只引入了dagger库，未引用dagger-compiler，且dagger-compiler每个库都需要引入
3. gradle3.0 以下是需要引入apt插件才能编译的，每个库目录都需要引入，gradle3.0之后不需要引入
4. apt目录生成了java文件，未生成class文件
    调试时只能在debug环境中才会生成class文件，所以需要在gradle中定义debug环境，且每个library都需要定义debug
    
## Lambda 常见问题
Gradle 3.0之前使用Java8 Lambda 需要配置
```angular2html
jackOptions {
        enabled true
    }
```
```angular2html
compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
```
问题：当module中想要使用Lambda特性时 ，不能引入jackOptions，就会报错如下：
```angular2html
Error:Library projects cannot enable Jack. Jack is enabled in default config.
```
解决办法，在module的gradle中添加：
```angular2html
gradle.projectsEvaluated {
    tasks.withType(JavaCompile) {
        options.compilerArgs << "-Xbootclasspath/a:" + System.properties.get("java.home") + "/lib/rt.jar"
    }
}
```

## Bintray Gradle常见问题
> Bintray中依赖的库必须为当前库中的Lib或者同样的Jcenter或者Maven中已经存在的库才行，分库无法依赖的，所以存在多个库，必须每个库都上传到Bintray，然后依赖

详细教程  
[Android Library项目发布到JCenter最简单的配置方法](http://www.cnblogs.com/shiwei-bai/archive/2015/11/24/4991636.html)
<br>  
坑一：错误: 编码GBK的不可映射字符->请正确配置javadoc编码
```apple js
//生成java文档
task javadoc(type: Javadoc) {
   options.encoding "UTF-8"
   options.charSet 'UTF-8'
}
```
坑二：错误: 不允许使用自关闭元素->请删除javadoc注释里面所有的含有html标签，
```apple js

```
坑三： 错误: 程序包android.support.v7.widget不存在；错误: 找不到符号 ->在javadoc中加入忽略错误配置
```apple js
//生成文档
task javadoc(type: Javadoc) {
  failOnError false
}
```
坑四：Could not create version ‘0.1’: HTTP/1.1 401 Unauthorized [message:This resource requires authentication]，->没有配置正确的API Key
```apple js

```
坑五：没有有效的POM文件->一定要按步骤执行并没有配置正确的API Key:
```apple js

```
坑六：没有Add to JCenter按钮：
注意：在这个地址注册：https://bintray.com/signup/oss；不是https://bintray.com/signup；这两个地址不一样的
```apple js

```

## 移除某个第三方的依赖
```
debugImplementation ('me.ele:uetool:1.0.15'){
  exclude group: 'com.android.support', module: 'support-v7'
}

debugImplementation ('me.ele:uetool:1.0.15'){
  exclude group: 'com.android.support'
}
```

#### 更加方便的方式
> 有时候，乱七八糟的依赖过多，可以使用如下方案：
```
在 app的module中：

android{
	configurations.all {
        resolutionStrategy.eachDependency { DependencyResolveDetails details ->
            def requested = details.requested
            if (requested.group == 'com.android.support') {
                if (requested.name.startsWith("appcompat-v7")) {
                    details.useVersion '25.3.0'
                }
                if (requested.name.startsWith("appcompat-v4")) {
                    details.useVersion '25.3.0'
                }

                if (requested.name.startsWith("recyclerview-v7")) {
                    details.useVersion '25.3.0'
                }
            }
        }
    }

}

这样可以强制使用某个版本，不用再一个个去过滤了。
```
