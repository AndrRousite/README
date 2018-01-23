- FileZilla FTP Client
- Node.js
- PremiumSoft Navicat
- Fiddler
- Total Control / TC 
- UltraISO Premium
- VMware Workstation 
- Xshell 
- Apache/Tomcat/Nginx


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
        - more： 
        
        | 语法        | 描述    |
        | ----------- | ------- |
        | $('*')      | 选取所有元素 |
        | $(this)      | 选取当前 HTML 元素 |
        | $("p.intro")    | 选取 class 为 intro 的 <p> 元素 |
        | $("p:first")      | 选取第一个 <p> 元素 |
        | $("ul li:first")    | 选取第一个 <ul> 元素的第一个 <li> 元素 |
        | $("ul li:first-child")      | 选取每个 <ul> 元素的第一个 <li> 元素 |
        | $("[href]")     | 选取带有 href 属性的元素 |
        | $("a[target='_blank']")      | 选取所有 target 属性值等于 "_blank" 的 <a> 元素 |
        | $("a[target!='_blank']")      | 选取所有 target 属性值不等于 "_blank" 的 <a> 元素 |
        | $(":button")      | 选取所有 type="button" 的 <input> 元素 和 <button> 元素 |
        | $("tr:even")     | 选取偶数位置的 <tr> 元素 |
        | $("tr:odd")     | 选取奇数位置的 <tr> 元素 |
