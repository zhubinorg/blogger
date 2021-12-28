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
