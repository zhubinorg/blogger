# 用法
1.在 blogger 布局设置中添加一个新的 HTML/JavaScript 微件，标题内容随意；

2.在主题背景设置自定义下拉菜单选择修改 HTML，用你填写的标题内容找到相应代码块；
```
<b:widget id='HTML1' locked='false' title='微件标题' type='HTML' version='2' visible='true'>
<b:widget-settings>
<b:widget-setting name='content'>微件内容</b:widget-setting>
</b:widget-settings>
<b:includable id='main'>
这里是你需要替换的内容
</b:includable>
</b:widget>
```

3.将下面的内容修改后在合适的地方替换，保存后记得在布局设置中**启用**这个微件。
```
<b:includable id='main'>
<!-- Promise Polyfill -->
<script src="https://cdn.jsdelivr.net/npm/promise-polyfill@8/dist/polyfill.min.js"></script>
<!-- Fetch Polyfill -->
<script src="https://cdn.jsdelivr.net/npm/whatwg-fetch@3.0.0/dist/fetch.umd.min.js"></script>
<!-- Unpkg -->
<link rel="stylesheet" href="https://unpkg.com/disqusjs@1.3/dist/disqusjs.css"></link>
<script src="https://unpkg.com/disqusjs@1.3/dist/disqus.js"></script>
<b:if cond='data:blog.pageType == "item"'>
<style type='text/css'>
#comments {display:none;}
</style>
<!-- shortname.disqus.com/blogger_item.js -->
<script>
(function () {
    "use strict";
    var get_comment_block = function () {
        var block = document.getElementById('comments');
        if (!block) {
            block = document.getElementById('disqus-blogger-comment-block');
        }
        return block;
    };
    var comment_block = get_comment_block();
    if (!!comment_block) {
        var disqus_div = document.createElement('div');
        disqus_div.id = 'disqus_thread';
        comment_block.innerHTML = '';
        comment_block.appendChild(disqus_div);
        comment_block.style.display = 'block';
        (document.getElementsByTagName('head')[0] || document.body).appendChild(dsq);
    }
})();</script>
<script>
var dsqjs = new DisqusJS({
    shortname: "自己填写",
    siteName: "",
    identifier: "<data:blog.url/>",
    url: "<data:blog.url/>",
    title: "",
    api: "https://disqus.skk.moe/disqus/详阅文档",
    apikey: "自己申请",
    admin: "",
    adminLabel: ""
});
</script>
</b:if>
<style type='text/css'>
.post-comment-link { visibility: hidden; }
</style>
</b:includable>
```
