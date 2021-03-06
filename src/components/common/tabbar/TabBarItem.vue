<template>
	<div class="tab-bar-item" @click="itemClick">
		<div v-if="!isActive" class="item-img"><slot name="item-icon"></slot></div>
		<div v-else class="item-img"><slot name="item-icon-active"></slot></div>
		<div :style="activeStyle"><slot name="item-text"></slot></div>
	</div>
</template>

<script>
  export default {
    name: "TabBarItem",
	  props:{
      path:String,
      activeColor:{
        type:String,
	      default:'pink'
      }
	  },
	  computed:{
      isActive(){
        return this.$route.path.indexOf(this.path) !== -1
      },
		  activeStyle(){
        return this.isActive?{color:this.activeColor}:{}
		  }
	  },
	  methods:{
      itemClick(){
        console.log('哈哈哈哈，点击了吧')
	      this.$router.replace(this.path)
      }
	  }
  }
</script>

<style>
	.tab-bar-item {
		flex: 1;
		text-align: center;
		height: 49px;
		font-size: 14px;
	}

	.item-img img{
		width: 24px;
		height: 24px;
		margin-top: 3px;
		margin-bottom: 2px;
		vertical-align: middle;
	}

</style>
