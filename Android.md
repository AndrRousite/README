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