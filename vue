<!DOCTYPE html>
<html lang="zh">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta http-equiv="X-UA-Compatible" content="ie=edge">
	<title></title>
</head>
<body>
	
	<div id="app">
		<com>
			<!-- 如果组件标签中的元素想要和组件模板中的插槽对应，可以给标签元素设置slot属性，属性值和插槽的name值保持一致-->
			<span slot="name">张三</span>
			<!-- 对于不需要标签包裹的内容，可以使用template标签 -->
			<template slot="sign">vue真简单</template>
			<!-- 如果不设置slot属性，则放入匿名插槽位置 -->
			<span>.....</span>
		</com>
		
	</div>
	
	<script type="text/html" id="com">
		<div>
			<!--slot插槽标签可以设置name属性,表示插槽名称-->
			<h1><slot name="name"></slot></h1>
			<p><slot name="sign"></slot></p>
			<!-- 没有name属性的slot插槽，就是匿名插槽 -->
			<p><slot></slot></p>
		</div>
	</script>
	<script src="js/vue.js"></script>
	<script>
		
		let com = {
			template:"#com"
		}
		
		new Vue({
			el:"#app",
			data:{
				
			},
			components:{
				com
			}
		})
		
	</script>
</body>
</html>
