<template>
  <div id="app">
    <div class="nav-bar">
      <router-link :to="{name: 'Home'}" class="weike">微客</router-link>
      <div class="nav-view">
        <ul>
          <li>
            <router-link :to="{name: 'Home'}" activeClass="active">首页</router-link>
          </li>
          <li>
            <div class="search-wapper">
              <input type="text" class="search-article" placeholder="搜索">
              <button style="background-image: url('images/search.png')"></button>
            </div>

          </li>
        </ul>
      </div>
      <div class="nav-login">

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
    /*引入公用样式*/
    @import "assets/common";
    $light-gray: rgb(238,238,238);
    width: 100%;
    margin: 0 auto;
    padding-top: 61px;
    /*头部导航栏*/
    .nav-bar {
      $bar-height: 60px;
      $title-color: gray;
      display: flex;
      height:$bar-height;
      position: fixed;
      width: 100%;
      top: 0;
      border-bottom: 1px solid $light-gray;
      min-width: 500px;
      .weike {
        @include vertical-middle;
        /*为了nav-view 相对于父视图居中*/
        position: absolute;
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
        margin: 0 auto;
        ul {
          list-style: none;
          display: inline-flex;
          li.search-wrapper {
            position: relative;
          }
          li {
            a {
              cursor: pointer;
              @include vertical-middle-norel;
              color: $title-color;
              font-size: 20px;
              text-decoration: none;
              height: inherit;
              background-color: white;
            }
            .search-wapper {
              $search-height: 40px;
              position: relative;
              .search-article {
                margin-left: 50px;
                height:$search-height;
                margin-top: -3px;
                padding: 0 $search-height/2;
                border: {
                  radius: $search-height/2;
                  width: 0;
                };
                background-color: #EEEEEE;
                outline: none; //去除选中外边框
              }
              button {
                $iconWrapper-W: 30px;
                position: absolute;
                right: 0;
                top: 0;
                vertical-align: middle;
                width: $iconWrapper-W;
                height: $iconWrapper-W;
                border: 0;
                box-sizing: border-box;
                border-radius: $iconWrapper-W/2;
                /*background-color: gray;*/
                text-align: center;
                button {
                  background: url('./images/search.png') no-repeat center;
                  background-size: contain;
                  width: 18px;
                  @include vertical-middle;
                }
              }
            }
            }
        }
      }
    }


  }
</style>
