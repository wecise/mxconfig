<template>
  <el-container class="m3 m3config">
    <el-header>
        <Header :auth="auth" v-if="auth"></Header>
      </el-header>
    <el-main>
      <MainView :global="global" v-if="global"></MainView>
    </el-main>
  </el-container>
</template>

<script>

import MainView from './components/MainView';
import Header from './components/layout/Header';

export default {
  name: 'app',
  components: {
    Header,
    MainView
  },
  data(){
    return {
      global:null,
      auth: null
    }
  },
  mounted(){
    setTimeout(()=>{
      this.global = this.m3.global;
      this.auth = this.m3.auth.signedUser;
    },500)
  }
}
</script>

<style>
  body{
    overflow: hidden!important;
    font-size: 12px;
    font-family: "PingFang SC",Arial,"Microsoft YaHei",sans-serif;
    margin: 0px;
    padding: 0px;
  }
  
  .el-menu .svg-icon{
    width: 1.2em!important;
    height: 1.2em!important;
    padding: 0px 5px 0 0;
  }

.gutter {
    background-color: #eee;

    background-repeat: no-repeat;
    background-position: 50%;
}
.gutter.gutter-vertical {
    background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAB4AAAAFAQMAAABo7865AAAABlBMVEVHcEzMzMzyAv2sAAAAAXRSTlMAQObYZgAAABBJREFUeF5jOAMEEAIEEFwAn3kMwcB6I2AAAAAASUVORK5CYII=');
}

.gutter.gutter-horizontal {
    background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUAAAAeCAYAAADkftS9AAAAIklEQVQoU2M4c+bMfxAGAgYYmwGrIIiDjrELjpo5aiZeMwF+yNnOs5KSvgAAAABJRU5ErkJggg==');
}
</style>
