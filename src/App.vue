<template>
  <div id="app">
    <div class="nav-bar">
      <router-link :to="{name: 'Home'}" class="weike">微客</router-link>
      <div class="nav-view">
        <ul>
          <li><router-link :to="{name: 'Home'}" activeClass="active">首页</router-link></li>
          <!--<li><router-link :to="{name: 'About'}" activeClass="active">About</router-link></li>-->
        </ul>
      </div>

    </div>

    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style lang="scss" scoped>

  #app {
    
    $light-gray: rgb(238,238,238);
    width: 100%;
    max-width: 1000px;
    min-width: 800px;
    padding-top: 61px;
    /*头部导航栏*/
    .nav-bar {
      $bar-height: 60px;
      $title-color: gray;
      display: flex;
      height:$bar-height;
      position: fixed;
      width: 100%;
      min-width: 768px;
      max-width: 1440px;
      top: 0;
      border-bottom: 1px solid $light-gray;

      .weike {
        cursor: pointer;
        height: $bar-height;
        line-height: $bar-height;
        margin-left: 20px;
        font-size: 30px;
        text-decoration: none;
        color: $title-color;
        font-weight: 500;
      }
      .nav-view {
        height: $bar-height;
        ul {
          list-style: none;

          li {
            a {
              position: relative;
              top: 50%;
              transform: translateY(-50%);
              padding: 8px 20px;
              color: $title-color;
              font-size: 20px;
              text-decoration: none;
              height: inherit;
              background-color: white;
            }
          }
        }
      }
    }


  }
</style>
