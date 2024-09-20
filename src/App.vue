<script setup lang="ts">
import Header from '@/components/Header.vue'
import Bar from '@/components/Bar.vue'
import Line from '@/components/Line.vue'
import Pie from '@/components/Pie.vue'
import Panel from '@/components/Panel.vue'
import Bar2 from '@/components/Bar2.vue'
import Line2 from '@/components/Line2.vue'
import Pie2 from '@/components/Pie2.vue'
import Map from '@/components/Map.vue'
import Map1 from '@/components/Map1.vue'
import Map2 from '@/components/Map2.vue'
import Map3 from './components/Map3.vue'
</script>

<template>
  <div class="app">
    <Header></Header>
    <!-- 页面主体部分 -->
    <section class="mainbox">
      <!-- 左侧内容 -->
      <div class="column">
        <Panel title="前端就业类别">
          <Bar></Bar>
        </Panel>
        <Panel title="就业人员变化">
          <Line></Line>
        </Panel>
        <Panel title="人员年龄分布">
          <Pie></Pie>
        </Panel>
      </div>
      <!-- 居中内容 -->
      <div class="column">
        <!-- no模块制作 -->
        <div class="no">
          <div class="no-hd">
            <ul>
              <li>125811</li>
              <li>100000</li>
            </ul>
          </div>
          <div class="no-bd">
            <ul>
              <li>前端需求人数</li>
              <li>市场供应人数</li>
            </ul>
          </div>
        </div>
        <!-- 地图模块 -->
        <div class="map">
          <Map1></Map1>
          <Map2></Map2>
          <Map3> </Map3>
          <Map></Map>
        </div>
      </div>
      <!-- 右侧内容 -->
      <div class="column">
        <Panel title="技能掌握情况">
          <Bar2></Bar2>
        </Panel>
        <Panel title="网络资料播放量">
          <Line2></Line2>
        </Panel>
        <Panel title="人员地区分布">
          <Pie2></Pie2>
        </Panel>
      </div>
    </section>
    <footer>2024-9-20 Lil-y</footer>
  </div>
</template>

<style lang="scss">
/* 声明字体*/
@font-face {
  font-family: electronicFont;
  src: url(./assets/DS-DIGIT.TTF);
}
body {
  background: url('@/assets/image/bg.jpg') no-repeat top center;
  line-height: 1.15;
  box-sizing: border-box;
}
.mainbox {
  display: flex;
  min-width: 1024px;
  max-width: 1920px;
  margin: 0 auto;
  padding: 0.125rem 0.125rem 0;
  .column {
    flex: 3;
  }
  .column:nth-child(2) {
    flex: 5;
    margin: 0 0.125rem 0.1875rem;
    overflow: hidden;
    // no数字模块
    .no {
      background: rgba(101, 132, 226, 0.1);
      // padding: 0.1875rem;
      .no-hd {
        position: relative;
        border: 1px solid rgba(25, 186, 139, 0.17);
        &::before {
          position: absolute;
          top: 0;
          left: 0;
          content: '';
          width: 30px;
          height: 10px;
          border-top: 2px solid #02a6b5;
          border-left: 2px solid #02a6b5;
        }
        &::after {
          position: absolute;
          bottom: 0;
          right: 0;
          content: '';
          width: 30px;
          height: 10px;
          border-right: 2px solid #02a6b5;
          border-bottom: 2px solid #02a6b5;
        }
        ul {
          display: flex;
          list-style: none;
          li {
            position: relative;
            flex: 1;
            line-height: 1rem;
            font-size: 0.875rem;
            color: #ffeb7b;
            text-align: center;
            font-family: 'electronicFont';
            &::after {
              content: '';
              position: absolute;
              top: 25%;
              right: 0;
              height: 50%;
              width: 1px;
              background: rgba(255, 255, 255, 0.2);
            }
          }
        }
      }
      .no-bd {
        ul {
          display: flex;
          list-style: none;
          li {
            flex: 1;
            text-align: center;
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.225rem;
            height: 0.5rem;
            line-height: 0.2rem;
            // padding-top: 0.125rem;
          }
        }
      }
    }
    // map模块
    .map {
      position: relative;
      height: 10.125rem;
    }
  }
}
footer {
  color: rgb(13, 45, 186);
  text-align: center;
  font-size: 0.25rem;
}
/* 约束屏幕尺寸 */
@media screen and (max-width: 1024px) {
  html {
    font-size: 42px !important;
  }
}
@media screen and (min-width: 1920px) {
  html {
    font-size: 80px !important;
  }
}
</style>
