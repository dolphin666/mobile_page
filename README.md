# 移动端布局的方法		
	1.单位用rem   不要用px   不要用bootstrap   
```
<script>
        (function (doc, win) {
            var docEl = doc.documentElement,
                    resizeEvt = 'orientationchange' in window ? 'orientationchange' : 'resize',
                    recalc = function () {
                        var clientWidth = docEl.clientWidth;
                        if (!clientWidth) return;
                        docEl.style.fontSize = 50 * (clientWidth / 375) + 'px';
                    };
            if (!doc.addEventListener) return;
            win.addEventListener(resizeEvt, recalc, false);
            doc.addEventListener('DOMContentLoaded', recalc, false);
        })(document, window);
</script>
```

	把这段js放在页面最开始   body前面    记住引入meta
	```meta
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no">
	```
	完了你用ps量出来的尺寸 直接除以100   单位用rem  不用px   
	例如   width：100px   就是width : 1rem;
	这样就可以完美适配手机端的不同尺寸了   

	不过这是在设计稿为750 的情况下   
	如果设计稿为640   就把js中间   那个375  改为320   就好了
	2.调试
		
