# handlebarsjs
## 1.前后端分离原理图 ##
![](https://i.imgur.com/MrToILM.png)
## 2.字符串拼接 ##
`<div class="card">
</div>
<script>
//数据
var data={
	name:'小林',
	birth:'1991.02.07',
	home:'中国',
	job:'前端'
};
var str = "";
str += "<div>姓名："+data.name+"</div>";
str += "<div>出生日期："+data.birth+"</div>";
str += "<div>出生地："+data.home+"</div>";
str += "<div>职业："+data.job+"</div>";
$(".card").html(str);
</script>`
## 3. handlebarsjs ##
    1.一条渲染
    <script src="https://cdnjs.cloudflare.com/ajax/libs/handlebars.js/2.0.0/handlebars.js"></script>
    <script id="card-template" type="text/x-handlebars-template">
    	<div>姓名：{{name}}</div>
    	<div>出生日期：{{birth}}</div>
    	<div>出生地：{{home}}</div>
    	<div>职业：{{job}}</div>
    </script> 
    <div class="card">
    </div>
    <script>
    	//数据
    	var data={
    		name:'小林',
    		birth:'1991.02.07',
    		home:'中国',
    		job:'前端'
    	};
    	var t = $("#card-template").html();
    //			console.log(t);
    	var f = Handlebars.compile(t);
    //			console.log(f);s
    	var h = f(data);
    	$(".card").html(h);
    </script> 
    2.二条渲染
    <script id="card-template" type="text/x-handlebars-template">
    	{{#each this}}
    	<div class="card">
    		<div>姓名：{{name}}</div>
    		<div>出生日期：{{birth}}</div>
    		<div>出生地：{{home}}</div>
    		<div>职业：{{job}}</div>
    	</div>
    	{{/each}}
    </script>
    <div class="card">
    </div>
    <script>
    	//数据
    	var data=[
    		{
    			name:'小林',
    			birth:'1991.02.07',
    			home:'中国',
    			job:'前端'
    		},
    		{
    			name:'小飞',
    			birth:'1992.02.07',
    			home:'中国',
    			job:'前端'
    		}
    	]
    	var t = $("#card-template").html();
    //			console.log(t);
    	var f = Handlebars.compile(t);
    //			console.log(f);s
    	var h = f(data);
    	$(".card").html(h);
    </script>
## 4. handlebarsjs特点 ##
    1.避免在js中写"html代码"
    2.可读性好
    3.易维护