<template>
	<div class="display_box container">
		<h4 class="tilte">
			<a href="#">可选图形</a>
		</h4>
		<div class="row">
			<div class="pic_box" v-for="imgM in imgMessages">
				<div class="head">
					<div class="pic_img"><img :src="imgM.src" :alt="imgM.alt"></div>
					<h4 class="pic_title">{{imgM.name}}</h4>
					<p>{{imgM.des}}</p>
				</div>
				<router-link :to="imgM.link" ><button class="btn" @click="midifType(imgM.type)" >编辑此图</button></router-link>
			</div>
		</div>
	</div>
</template>
<style scoped>
	.display_box p{ margin: 0;}
	.display_box{ padding: 30px 0 114px 0; }
	.display_box .tilte{ height: 40px; line-height: 40px;text-align: center; color: #fd5d1e; font-size: 36px; font-weight: normal; margin-bottom: 30px;}
	.display_box .tilte a{ color: #fd5d1e; }
	.pic_box{ width: 250px; height: 360px; border: 1px solid #cfcfcf; float: left; margin: 0 20px; overflow: hidden; background: white;  }
	.pic_box .head{ padding: 10px; }
	.pic_box .head h4,.pic_box .head p{ height: 20px; line-height: 20px;}
	.pic_box:hover{ border: 1px solid #e6732e}
	.pic_box h4{ margin-top: 10px; margin-bottom: 10px; }
	.pic_img,.pic_img img{ width: 230px; height: 240px; }
	.display_box .btn{ width: 250px; height: 40px;  background: #FF4500; color: #fff; font-size: 20px;}
	.display_box .btn a{ color: #fff; }
</style>
<script>
	export default{
		 data () {  
            return {  
               imgMessages: [
               		{ src:"../../static/bubble.png", alt: "气泡展示图", name:"气泡图",des:"这是一个最基本的Bubble图",link:"/bubbleconfig",type: "scatter"},
               		{ src:"../../static/barShow.png", alt: "chord展示图", name:"堆叠条形图",des:"这是一个最基本的chord图",link:"bubbleconfig", type: "bar"},
               		{ src:"../../static/tree.png", alt: "tree展示图", name:"tree图",des:"这是一个最基本的tree图",link:""},
               		{ src:"../../static/sigma.png", alt: "sigma展示图", name:"sigma图",des:"这是一个最基本的sigma图",link:""}
               ]
            }  
      },
      methods:{
      	midifType(type){
      		this.$store.state.pictureType = type;
      	}
      },
       mounted:function(){
       		console.log(this.$store.state.pictureType);
       }
	}

</script>