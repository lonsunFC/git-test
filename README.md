1.首先，是选择器
后代选择器：$("form input") 后代选择器，选择ancestor的所有子孙节点 

     子代选择器：$("#main > span")main下一级的的所有span子节点 

     兄弟选择器：$("label + input") 兄弟相邻选择器，选择所有label相邻的第一个input节点 

     兄弟选择器：$("#prev ~ div") 相邻后边的所有，选择prev的所有后面的div同胞节点

$('.li_2','.ul') $([子节点],[父节点])
　　$("div,span,p.myClass"); 这是取出 所有div span 和 class名叫 myClass 的p标签 ，  这里经常会有朋友在书写/检查代码时，

习惯性的认为自己选中的是div中的span、p标签。而忽略了div外部的，这种多条件的选择器，容易记错。了解的语言太多，难免会混。

  $("tr:eq(1)")；只要是带索引值的东西，都可以选中，这个就是直接按索引值选择，选中索引值为1的元素。eq的索引是从0开始计算的。
  

data=‘’

2.其次，是事件

文档就绪函数ready（）：

　　　　$(document).ready(function(){ // 在这里写你的代码... }); 作用是，处理完完HTML代码后再加在js代码

　　　　避免出现js代码无法取到HTML代码的情况　
　　　　$(function(){}); 这是文档就绪函数的简写形式，通过匿名函数的写法

他与window.onload（）方法的区别：
　　　　(1)window.onload需要在网页所有内容都加载完成后才能执行，包括那些视频之类的；而文档就绪函数只要dom结构加载完成就可以执行

　　　　(2)window.onload如果写了好几个，只会执行最后一个，但是文档就绪函数不会，他每个都会执行
http://ex8yanshi.lonsun.cn/site/tpl/2653871

当使用js方法的时候，会在整个页面的document全部加载完成以后执行。不幸的这种方式不仅要求页面的DOM tree全部加载完成，而且要求所有的外部图片和资源全部加载完成。更不幸的是，
如果外部资源加载时间过长，例如图片需要很长时间来加载，那么这个js效果就会让用户感觉失效了，所以当这个情景下，使用这种方法的用户体验是非常差的。 
使用jquery方法：就仅仅只需要加载所有的DOM结构，在浏览器把所有的HTML放入DOM tree之前就执行js效果，包括在加载外部图片和资源之前。




$(this).index()方法 ：
$("button").on("click", function(){

　　　　　　console.log($(this).html());

　　　　}) 



$("button").on("mouseover click",function(){

　　　　　　console.log($(this).html());

　　　　}) 


这是事件委派，是将原本要绑定到某元素上的事件，绑定到父容器乃至根节点上，然后再委托到想绑定事
$("body").on("click","button",function(){

　　　　　　alert("1");

})

1. 修改:

    样式: 1. 修改css属性: $(...).css()

             2. 修改class:

               $(...).addClass()  $(...).removeClass() $(...).hasClass()

               $(...).toggleClass("类名"): 在有或没有指定类名之间切换。
			   
			   2. 遍历节点: 节点间关系

    1. 父子关系:

       $(...).parent()

       $(...).children([selector]) 只获得直接子元素

       $(...).find(selector) 获得所有子代元素

        强调: children可不加selector，但find必须加selector

    2. 兄弟关系:

       $(...).next([selector])  下一个兄弟元素

       $(...).prev([selector])  前一个兄弟

          强调: 如果加selector，必须满足:

            1. 必须是相邻，2. 必须满足selector的要求

       $(...).siblings([selector]) 其它兄弟

 

3. 添加，删除，替换:

  添加:

   DOM: 3步:

       1. 创建空元素对象，

       2. 设置关键属性,

       3. 添加到父元素下

   jq: 2步:  

      1. 创建节点: var $elem=$("完整html元素代码段");

      2. 将节点添加到指定父元素下:

          追加: $(parent).append($elem); 追加到parent下的所有子节点末尾——appendChild

          插入: $(parent).prepend($elem); 作为parent下的第一个子节点插入

                   $(child).after($elem); 插入到child之后

                   $(child).before($elem); 插入到child之前

 

   删除: $(要删除的元素).remove();

       强调: 删除时，不必查找父元素

ajax



在Elements面板中拖放元素

Settings → General → Elements → Show user agent shadow DOM
使用CSS选择器查找元素

https://cssreference.io/

