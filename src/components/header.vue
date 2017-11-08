<template>
  <div>
    <header class="header">
      <div v-show='!searchShow' class="header-one">
        <i class="menu"></i>
        <h3 class="one-title">one</h3>
        <i class="search" @click='searchFn'></i>
      </div>
      <div v-show='searchShow' class="search-input">
        <input v-model='searchString' type="text" placeholder="Please enter key word"/>
        <i class="search-act"></i>
        <i class="cancle" @click='searchFn'></i>
      </div>
    </header>
  </div>
</template>
<script>
export default {
  name: 'header',
  data () {
    return {
      searchShow: false,
      searchString: ''
    }
  },
  methods: {
    searchFn: function () {
      this.searchShow = !this.searchShow
    }
  }
}
</script>
<style>
/*样式代码*/
.search-input{
	width: 100%;
	padding: 0 .3rem;
  display:flex;
  width:100%;
  justify-content: space-between;
  align-items: center;
}
.search-input input[type=text]{
	height: .3rem;
	width: 4.5rem;
	padding: .1rem .2rem;
	font-size: .24rem;
	border: none;
	outline: none;
}
.search-act,.cancle{
	float:right;
}
.search-result{
	height: calc(100vh - .8rem);
    width: 100%;
    position: absolute;
    z-index: 5;
    top: .8rem;
    background-color: rgba(0,0,0,.3);
}
</style>
