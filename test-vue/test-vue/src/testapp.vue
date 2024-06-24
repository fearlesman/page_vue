
<template>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <el-menu
    :default-active="activeIndex"
    class="el-menu-demo"
    mode="horizontal"
    :ellipsis="false"
    @select="handleSelect"
    :unique-opened="true"
    background-color="#545c64"
    text-color="#fff"
    id="app-menu"
  >
    <el-menu-item index="0" id="logo">
      <img
        style="width: 100px"
        src="./components/icons/teamlogo.png"
        alt="Element logo"
      />
    </el-menu-item>
    <div class="flex-grow" />
    <el-menu-item  @click="jumpToSection('intro')">
      <p class="menu" :style="{ width: '200px' }">实践团队介绍</p>
    </el-menu-item>
    <el-menu-item @click="jumpToSection('plan')">  
      <p class="menu" :style="{ width: '200px' }">实践计划</p>  
    </el-menu-item>
    <el-sub-menu index="diary" :unique-opened="true" class="submenu" style="margin-left: 100px;">
      <template #title >  
        <p class="submenu">实践日记</p>  
      </template>
      <div v-for="(item, index) in week" :key="index" >
        <el-sub-menu index="week" @click="handleSelect" >
          <template #title>
            <p class="menucontent">{{item}}</p>
          </template>
          <el-menu-item index="day" v-for="(itemw, index) in day" :key="index" @click="jumpToSection('index')">
            <p class="menucontent">{{itemw}}</p>
          </el-menu-item>
        </el-sub-menu>
      </div>
    </el-sub-menu>
    <el-menu-item index="3" class="menu" @click="jumpToSection('activity')">
      <p >实践活动</p>
    </el-menu-item>
    <el-menu-item index="4" class="menu" @click="jumpToSection('achievement')">
      <p >实践心得</p>
    </el-menu-item>

    <el-menu-item index="5" class="menu" @click="jumpToSection('contact')">
      <p >联系我们</p>
    </el-menu-item>
    <el-menu-item index="6" class="menu" @click="jumpToSection('support')">
      <p >赞助我们</p>
    </el-menu-item>
  </el-menu>
  <div class="poem" >
    <div class="img-content">
        <img src="./components/icons/1.webp" alt="OIP-C">
    </div>
    <p>碧空如洗，万里无雁影</p>
    <p>喜听朗声背诗文，孩童乐学可期</p>
    <p>忽闻乡里客归，却无佳品相寄</p>
    <p>凭己一腔热怀，支教初心不移</p>
    <p>选择长青，不负芳华新时代</p>
    <p>融合创新支教，助未来孩童梦想成真</p>
    <p>为社会做出作为北科大青年的贡献</p>
    <p>齐心协力筑长青风华正茂书青春</p>
  </div>
  <br>
  <el-divider />
  <h1 class="title">实践团队介绍</h1>
  <h3 class="titleofteam">指导学姐</h3>
  <div style="background-color: blue">
  <el-card class="card" >
    <template #header >
      <div class="titleofperson">
        <h2>霍晓平</h2>
      </div>
    </template>
    <header>
        <div class="photo">
          <span><img 
            src="./components/person/senior.png" 
            class="imgofperson" alt="senior"
             width="500px" style="top:1400px">
          </span>
        </div>
      </header>
    <div class="cardcontent" >
      <p style="margin-left: 800px;">
        霍晓平，法学221，曾带队前往河北邯郸东沙村进行“支教+非遗传承”社会实践，
        很开心今年能够作为指导学长继续参与社会实践，延续长青的种子。</p>
      <p style="margin-left: 800px;">
        社会实践给了大家一次更深入地了解社会，了解自己，做有意义的事情的机会。
        愿你们在实践中始终保持谦逊和热情，不断吸收新知识，获得成长。
        希望这个夏天大家共同努力，用大手拉起小手，心有暖阳，我们爱意长青~
      </p>
    </div>
  </el-card>
</div>
  <br>
  <h3 class="titleofteam">队长</h3>

  <el-card class="card">
    <template #header > 
      <div class="titleofperson">
        <h2>丁岚</h2>
      </div>
    </template>
    <header>
        <div class="photo">
          <span><img 
            src="./components/person/header.png" 
            class="imgofperson" alt="senior"
             width="500px" style="top:1900px">
          </span>
        </div>
      </header>
    <div class="cardcontent" >
      <p style="margin-left: 800px;">
        哈喽大家好，我是长青青睐队长丁岚。
      </p>
      <p style="margin-left: 800px;">
        我来自土资学院安全2301班,河北保定人。
      </p>
      <p style="margin-left: 800px;">
          我是个有点e的小i人，
      </p>
      <p style="margin-left: 800px;">
          风向，性格很随和😋
      </p>
      <p style="margin-left: 800px;">
          期待与大家共同实践的14天
          缘分让我们相遇~
      </p>
    </div>
  </el-card> 
  
</template>

<script>
import { ElCalendar, ElCard, ElCarousel } from 'element-plus';

export default {
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      kkk: 0,
      day: ['星期一','星期二','星期三','星期四','星期五','星期六','星期日'],
      week: ['第一周','第二周'],
    }
    
  },
  methods: {
    
  }
}
function jumpToSection(section) {
  var target = document.getElementById(section);
  if (target) {
    window.scrollTo({
      top: target.offsetTop,
      behavior: 'smooth'
    });
  }
}
</script>
<style>
#app-menu {
  height: 10%;
  margin-top: 0;
  margin-bottom: 0;
  padding: 0;
  background-color: #545c64;
}
#logo {
  background: white;
  padding: 1px;
}
.menu {
  font-size: 24px;
  font-weight: bold;
  color: #fff;
  text-align: center;
  width: 13%;
}
.menucontent {
  font-size: 24px;
  font-weight: bold;
  color: #fff;
  margin-top: 20px;
  margin-bottom: 20px;
}
.submenu {
  font-size: 24px;
  font-weight: bold;
  color: #fff;
  width: 13%;
}
.title {
  font-size: 48px;
  font-weight: bold;
  margin-top: 60px;
  margin-bottom: 30px;
  text-align: center;
}
.card {
  width: 100%;
  max-width:max-content;
  margin-top: 30px; /* 顶部外边距 */
  padding: 20px; /* 内边距 */
  text-align: center; /* 文本居中对齐 */
  font-size: 24px; /* 字体大小 */
  font-weight: bold; /* 字体加粗 */
  color: #333; /* 字体颜色 */
  /*background-color: #f2f2f2; /* 背景颜色 */
  line-height: 24px;
  white-space: pre-wrap; /* 保持空白符和换行符 */
  background-image: url(./components/icons/OIP-C.jpg);
  height: 1000px;
} 
.card .cardcontent {
  text-align: left; /* 文本居左对齐 */
  margin-top: 30px; /* 顶部外边距 */
  padding: 20px; /* 内边距 */
  color: #666; /* 字体颜色 */
  line-height: 48px;
  font-size: 32px; /* 字体大小 */
  white-space: pre-wrap; /* 保持空白符和换行符 */
  margin-right: 100px;
  
}
.photo {
  display: flex;
  padding: 80px;
  margin-top: 60px;
  height: 500px;
  width: 100%;
  position: absolute;
}
.titleofperson {  
  justify-content: center;
  align-items: center;
  height: 100px;
  width: 100%;
  color: #333;
  font-size: 32px;
  font-weight: bold;
  text-align: center;
}
.titleofteam{
  justify-content: center;
  padding: 80px;
  
  font-size: 36px;
}
.poem {
  margin-top: 60px;
  padding: 20px;
  text-align: center;
  font-size: 36px;
  font-weight: bold;
  color: #34334e;
  line-height: 24px;
  white-space: pre-wrap;
}
.poem .img-content {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 500px;
  width: 100%;
  filter:blur(3px);
  position: absolute;
  z-index: -1;
}
</style>