##### View
![View](android.jpg)

- FileZilla FTP Client
- Node.js
- PremiumSoft Navicat
- Fiddler
- Total Control / TC 
- UltraISO Premium
- VMware Workstation 
- Xshell 
- Apache/Tomcat/Nginx
- Composer


###### TOOLS
- [kotlin-记账(需求笔记)](/tools/kotlin记账.xmind)
- [Android反编译工具](/tools/Androidfby)
- [apktool](/tools/apktool)
- [多彩便签](/tools/dcbq)
- [dex2jar](/tools/dex2jar-0.0.9.15)
- [FlashFXP](/tools/FlashFXP)
- [jd-gui](/tools/jd-gui)
- [DES加密解密工具](/tools/DES加密解密工具.exe)
- [FSCapture](/tools/FSCapture_单文件.exe)
- [getcolor](/tools/getcolor.exe)
- [HiJson](/tools/HiJson%202.1.2_jdk64.exe)
- [Shadowsocks](/tools/Shadowsocks.exe)
- [参考手册](/tools/参考手册)
- [2018-1-26书签](/bookmarks_2018_1_26.html)


###### jQuery
- 功能：
    - 元素的选取和操作
    - CSS操作
    - HTML事件函数
    - Javascript特效和动画
    - HTML DOM遍历和修改
    - AJAX
    - Utilities
    
- jQuery2.0版本不支持IE6、7、8
    ```angular2html
    <!--[if lt IE 9]>
        <script src="jquery-1.9.0.js"></script>
    <![endif]-->
    <!--[if gte IE 9]><!-->
        <script src="jquery-2.0.0.js"></script>
    <!--<![endif]-->
    ```
- jQuery安装
   > - Production version - 用于实际的网站中，已被精简和压缩。
   > - Development version - 用于测试和开发（未压缩，是可读的代码）
    - 下载引用js文件
    - CDN分发

- 语法
    - 基础语法： $(selector).action()
    - 文档就绪事件：防止在文档没有完全加载之前就运行函数，操作可能失败
        ```angular2html
        1. $(document).ready(function(){
              // todo 
           })
        2. $(function(){
              // todo
           })
        简洁写法
        ```
    - 选择器：基于css选择器
        - 元素选择器：$('p')
        - id选择器：$("#id")
        - class选择器：$('.class'')
        - more：更多实例   

            |语法        |描述   |
            |-----------|-------|
            | $('*')      | 选取所有元素 |
            | $(this)      | 选取当前 HTML 元素 |
            | $("p.intro")    | ```选取 class 为 intro 的 <p> 元素``` |
            | $("p:first")      | ```选取第一个 <p> 元素``` |
            | $("ul li:first")    | ```选取第一个 <ul> 元素的第一个 <li> 元素``` |
            | $("ul li:first-child")      | ```选取每个 <ul> 元素的第一个 <li> 元素``` |
            | $("[href]")     | 选取带有 href 属性的元素 |
            | $("a[target='_blank']")      | 选取所有 target 属性值等于 "_blank" 的 <a> 元素 |
            | $("a[target!='_blank']")      | 选取所有 target 属性值不等于 "_blank" 的 <a> 元素 |
            | $(":button")      | 选取所有 type="button" 的 <input> 元素 和 <button> 元素 |
            | $("tr:even")     | 选取偶数位置的 <tr> 元素 |
            | $("tr:odd")     | 选取奇数位置的 <tr> 元素 |
    - jQuery事件:  
    常见的DOM事件
    
        |鼠标事件|键盘事件|表单事件|文档/窗口事件|
        |-------|-------|-------|------------|
        |click|keypress|submit|load|
        |dbclick|keydown|change|resize|
        |mouseenter|keyup|focus|scroll|
        |mouseleave| |blur|upload|
    - jQuery效果
        - 隐藏/显示：show()、hide()、toggle()
        - 淡入/淡出：fadeIn()、fadeOut()、fadeToggle()、fadeTo()
        - 滑动：slideDown()、slideUp()、slideToggle()
        - 动画/停止动画：animate()/stop(stopAll,goToEnd)
    - jQuery元素
        - 设置或获取内容：
            ```html
            text() - 设置或返回所选元素的文本内容
            html() - 设置或返回所选元素的内容（包括 HTML 标记）
            val() - 设置或返回表单字段的值
            ```
        - 设置或获取属性：
            ```html
            attr(): 
              实例
              $("button").click(function(){
                alert($("#a").attr("href"));
              });
            ```
        - 添加元素: 
            ```html
            append() - 在被选元素的结尾插入元素
            prepend() - 在被选元素的开头插入元素
            after() - 在被选元素之后插入元素
            before() - 在被选元素之前插入元素
            总结：
                append/prepend 是在选择元素内部嵌入。
                after/before 是在元素外面追加。
            ```
        - 删除元素：
            ```html
            remove() - 删除被选元素（及其子元素）
            empty() - 从被选元素中删除子元素
            ```
        - 操作css：
            ```html
            addClass() - 向被选元素添加一个或多个类
            removeClass() - 从被选元素删除一个或多个类
            toggleClass() - 对被选元素进行添加/删除类的切换操作
            css() - 设置或返回样式属性
            ```
        - 操作尺寸：
            ```html
            width()
            height():元素高度
            innerWidth()
            innerHeight():height+padding
            outerWidth(default:false):
            outerHeight(default:false):if true?height+padding+border+margin：height+padding+border
            ```
    - jQuery遍历
        - 祖先：
            ```html
            parent()
            parents()
            parentsUntil():回介于两个给定元素之间的所有祖先元素
            实例
                $(document).ready(function(){
                  $("span").parentsUntil("div");
                });
            ```
        - 后代：
            ```html
            children():返回被选元素的所有直接子元素
            find():被选元素的所有后代元素
            ```
        - 同胞：
            ```html
            siblings():返回被选元素的所有同胞元素
            next()
            nextAll()
            nextUntil()
            prev()
            prevAll()
            prevUntil()
            ```
        - 过滤方法：
            ```html
            三个最基本的过滤方法是:
            first():返回被选元素集合的首个元素
            last():返回被选元素集合的最后一个元素
            eq():返回被选元素列表中带有指定索引号的元素
            其它：
            filter():不匹配这个标准的元素会被从集合中删除，匹配的元素会被返回
            not():返回不匹配标准的所有元素
            ```
- AJAX = 异步 Javascript 和 XML(Asynchronous Javascript and XML)
    - load():从服务器加载数据，并把返回的数据放入被选元素中
        ```html
        语法：$(selector).load(URL,data,callback);
        实例：$("#div1").load("demo_test.txt")
        ```
    - $.get(URL,callback) 和 $.post(URL,data,callback)
    - $.ajax({
        url:'',
        type:'GET',
        dataType:'JSONP',
        success:function(result){
            console.log(result)
        }
    })
    - 问题：Ajax跨域的问题?
- Others
    - $.noConflict()：释放对$标识符的控制，可以使用jQuery代替$符,也可以自定义变量代替$
        ```html
        var jq = $.noConflict()
        jq(document).ready(function(){
              // todo list 
        })
        jq(function(){
              // todo list
        })
        ```
