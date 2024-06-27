
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
    v-model:collapse="isCollapse"
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
      <p class="menu" :style="{ width: '200px' }" onclick="jumpToSection('intro')">实践团队介绍</p>
    </el-menu-item>
    <el-menu-item @click="jumpToSection('plan')">  
      <p class="menu" :style="{ width: '200px' }">实践计划</p>  
    </el-menu-item>
    <el-sub-menu index="daily" :unique-opened="true" class="submenu" style="">
      <template #title >  
        <p class="submenu">日常推送</p>  
      </template>
    </el-sub-menu>
    <el-sub-menu index="diary" :unique-opened="true" class="submenu" style="">
      <template #title >  
        <p class="submenu">实践日记</p>  
      </template>
    </el-sub-menu>
    <el-menu-item index="3" class="menu" @click="jumpToSection('activity')">
      <p >实践活动</p>
    </el-menu-item>
    <el-menu-item index="4" class="menu" @click="jumpToSection('achievement')">
      <p >实践心得</p>
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
  <el-divider /><h1 class="title" id="intro">实践团队介绍</h1>
  <div>
    <el-row>
      <el-col :span="12">
  <el-card class="card" >
    <template #header >
      <div class="titleofperson">
        <span>指导学姐</span><h2>霍晓平</h2>
      </div>
    </template>
    <header>
        <div class="photo">
          <span><img 
            src="./components/person/senior.png" 
            class="imgofperson" alt="senior"
             width="300px" style="top: 0px;left: 180px;">
          </span>
        </div>
      </header>
  </el-card>
</el-col>
<el-col :span="12">
  <el-card class="card" >
    <template #header >
      <div class="titleofperson">
        <h2>个人介绍</h2>
      </div>
    </template>
    <!-- 介绍文本 -->
    <div class="cardcontentforheader" >
      <p>{{ textofsenior[0] }}</p>
      <p>{{ textofsenior[1] }}</p>
    </div>
  </el-card>
</el-col>
</el-row>
<el-row>
  <el-col :span="6">
  <el-card class="card" >
    <template #header >
      <div class="titleofperson">
        <span>队长</span><h2>丁岚</h2>
      </div>
    </template>
    <header>
        <div class="photo">
          <span><img 
            src="./components/person/header.png" 
            class="imgofperson" alt="senior"
             width="300px" style="top:6px">
          </span>
        </div>
      </header>
  </el-card>
</el-col>
<el-col :span="6">
  <el-card class="card" >
    <template #header>
      <div class="titleofperson">
        <p>个人介绍</p>
      </div>
    </template>
    <!-- 介绍文本 -->
    <div class="cardcontent" v-for="(item, index) in textofheader" :key="index" >
      <span>
        {{item}}
      </span>
    </div>
  </el-card>
</el-col>
<el-col :span="6">
  <el-card class="card" >
    <template #header >
      <div class="titleofperson">
        <span>副队长</span><h2>柴福来</h2>
      </div>
    </template>
    <header>
        <div class="photo">
          <span><img
            src="./components/person/coheader.jpg" 
            class="imgofperson" alt="senior"
             width="300px" style="top:6px">
          </span>
        </div>
      </header>
  </el-card>
</el-col>
<el-col :span="6">
  <el-card class="card" >
    <template #header>
      <div class="titleofperson">
        <p>个人介绍</p>
      </div>
    </template>
    <!-- 介绍文本 -->
    <div class="cardcontent" v-for="(item, index) in textofcoheader" :key="index" style="font-size: 18px; line-height: 24px;">
      <span>
        {{item}}
      </span>
    </div>
  </el-card>
</el-col>
</el-row>
</div>

<div class="titleofperson">
  <h1>队员</h1>
</div>

<div v-for="(name1, index) in membername1" :key="index" >
  <el-row>
  <el-col :span="6">
  <el-card class="card" >
    <template #header >
      <div class="titleofperson">
        <h2>{{name1}}</h2>
      </div>
    </template>
    <header>
        <div class="photo">
          <span><img 
            :src=img[name1] 
            class="imgofperson" alt="senior"
             width="300px" style="top:6px">
          </span>
        </div>
      </header>
  </el-card>
</el-col>
<el-col :span="6">
  <el-card class="card" >
    <template #header>
      <div class="titleofperson">
        <p>个人介绍</p>
      </div>
    </template>
    <!-- 介绍文本 -->
    <div class="cardcontent" v-for="(text, index) in members1[name1]" :key="index" >
      <span style="font-size: 18px; line-height: 21px;">
        {{text}}
      </span>
    </div>
  </el-card>
</el-col>
<el-col :span="6">
  <el-card class="card" >
    <template #header >
      <div class="titleofperson">
        <h2>{{membername2[name1]}}</h2>
      </div>
    </template>
    <header>
        <div class="photo">
          <span><img 
            :src=img[membername2[name1]]
            class="imgofperson" alt="senior"
             width="300px" style="top:6px">
          </span>
        </div>
      </header>
  </el-card>
</el-col>
<el-col :span="6">
  <el-card class="card" >
    <template #header>
      <div class="titleofperson">
        <p>个人介绍</p>
      </div>
    </template>
    <!-- 介绍文本 -->
    <div class="cardcontent" v-for="(text, index) in members2[membername2[name1]]" :key="index" >
      <span style="font-size: 18px; line-height: 21px;">
        {{text}}
      </span>
    </div>
  </el-card>
</el-col>
</el-row>
</div>
</template>

<script>
import { ElCalendar, ElCard, ElCarousel, textProps } from 'element-plus';

export default {
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      kkk: 0,
      day: ['星期一','星期二','星期三','星期四','星期五','星期六','星期日'],
      week: ['第一周','第二周'],
      textofsenior: [
        '霍晓平，法学221，曾带队前往河北邯郸东沙村进行“支教+非遗传承”社会实践，很开心今年能够作为指导学长继续参与社会实践，延续长青的种子。'
        ,'社会实践给了大家一次更深入地了解社会，了解自己，做有意义的事情的机会。愿你们在实践中始终保持谦逊和热情，不断吸收新知识，获得成长。希望这个夏天大家共同努力，用大手拉起小手，心有暖阳，我们爱意长青~'
      ],
      textofheader: [
        '哈喽大家好，我是长青青睐队长丁岚。',
        '来自河北保定，土资学院安全2301班,是个有点e的小i人。',
        '性格很随和😋,期待与大家共同实践的14天，缘分让我们相遇~',
      ],
      textofcoheader: [
        '大家好，我是柴福来，笔名柴不染，河北邯郸人，北京科技大学2023级本科生，学院团委宣传部成员。很荣幸担任此次实践团副队长。本人格局谨严而不乏情采，潇洒随性而自有法度。时而严肃，时而幽默。'
        ,'文墨客诗人天许，柴不染却染红尘。曾多次获得邯郸市学生硬笔书法一等奖，征文三等奖等奖项，北京科技大学诗词大会决赛“十二强”，经管分站亚军等证书。有一定的文化和艺术底蕴。我的故事，还有很长很长，想用14天的时间慢慢告诉你......'
        ,'“相逢一醉是前缘”，天青色等烟雨，而我在长青等你。非常期待暑期中与诸位相遇！'
        ],
      membername1: ['黄 琛', '刘巨哲',  '陈一鸣',  '侯若琰'],
      membername2:{ '黄 琛':'卓 玛','刘巨哲':'陈芝杰','陈一鸣':'张渤易', '侯若琰':'龚晓勇'},
      members1: {
              '黄 琛': [
                '我，黄琛，来自祖国西北边缘，世界上唯一以石油命名的城市——克拉玛依，在土木与资源工程学院土木类2305就读。'
                ,'我的血液里流淌着三代石油人逆境中不退缩、坚韧执着、顽强不屈的胡杨精神，擅长有效沟通与协作。我加入了社团排球协会，4月在校第十九届“三好杯”排球赛中所在团队获得季军。追求个人兴趣爱好，擅长文笔写作，中学时期曾多次获奖（在克拉玛依日报发表诗作，在全国“语文报杯”中学生主题征文获得铜牌等），偏好围棋竞技（业余三段）。'                ,'给不给我一双翅膀，我都会飞翔。'
                
              ],
              '刘巨哲': [
                '大家好，我是来自北京科技大学土木与资源工程学院的刘巨哲，来自安徽省亳州市利辛县。'
                ,'平时喜欢在健身房或者宿舍锻炼，为人朴实宽厚，待人真诚友善，期待与你相遇！'
              ],
              '陈一鸣': [
                '大家好，我是能源2302班的陈一鸣，很高兴能够参与青睐暑期支教活动，成为小队的一员。',
                '本人i中带e（不喜欢自我介绍），心怀热忱，乐于探索，善于乐于与孩子们打交道，喜爱摄影、运动，希望能够和大家共同努力，共同进步，携手同心，势在必行。'
              ],
              '侯若琰': [
                '我叫侯若琰，来自北京科技大学机械工程学院，是一名理科生，但也喜欢文学，喜欢音乐。',
                '期待和同学们一起与孩子们进行多方面的交流。'
              ]
            },

    members2: {
      '卓 玛': [
        '我目前就读于北京科技大学的土木类。我对支教活动一直有着浓厚的兴趣和热情，喜欢有唱歌，跳舞、社交、踢球、打篮球、拍短视频。非常高兴能够加入这次的实践团。',
        '在个人性格方面，我既开朗乐观，又不失沉稳细致。我善于与人沟通交流，能够与团队成员建立良好的关系，共同协作完成任务，会全力以赴地去做好每一件事。',
        '日常中比较随性，热爱生活，大胆享受生活，活出自我，自信的样子最帅最酷最美！'
      ],
      '陈芝杰': [
        '我是来自土木与资源工程学院安全2301班的陈芝杰。',
        '本人自幼便开始接触乐器，对音乐有浓厚的兴趣，在音乐方面有独特的见解。',
        '平日里喜欢打篮球，羽毛球球等，也会练习一会儿吉他。帮助他人解决问题也是我所乐于做的事。希望在未来能够结交更多的朋友。'
      ],
      '张渤易': [
        '大家好，我是张渤易，来自计算机2301班。',
        '我喜欢独自一个人在宁静的夜晚，在荧幕前闭上眼睛体验音乐的诗篇，喜欢生活中那一瞬间的错愕，转眼发现夕阳漫天。我会把自己的所有情感宣泄行动上，以此作为这份情感存在的证明。',
        '每当想起山村孩子还在艰苦的环境中学习，我知道教育平等是他们最大的愿景。我希望在这次社会实践中，自己作为一个大学生也能担当起这份责任，让偏远地区的孩子也能享受到优质的教育资源，实现他们所向往的美好未来。'
      ],
      '龚晓勇': [
        '本人龚晓勇，来自贵州省织金县，是北京科技大学2023级机械2310班的一名学生。',
        '为人比较乐观开朗，上进心比较强，容易相处，情绪稳定，善于沟通交流。平时爱好踢足球，骑行和跑步，也爱好摄影与读书，特别喜欢读诗词和读史，这能让我陶冶心境与开拓视野。',
        '摄影也是我的一大爱好，我平时喜欢用相机记录生活中的美好瞬间，定格绝胜的美景。'
      ]
     },
    img:{'黄 琛':"/src/components/person/HS.png",
    '卓 玛': "/src/components/person/ZM.png",
    '刘巨哲': "/src/components/person/LJZ.png",
    '陈芝杰': "/src/components/person/CZJ.png",
    '陈一鸣': "/src/components/person/CYM.png",
    '张渤易': "/src/components/person/ZBY.png", 
    '侯若琰': "/src/components/person/HRY.png",
    '龚晓勇': "/src/components/person/GXY.png"
      }
    }
  },
  methods: {
    jumpToSection(section) {
      var target = document.getElementById(section);
      if (target) {
        window.scrollTo({
          top: target.offsetTop,
          behavior: 'smooth'
        });
      }
    },
    add(index){
      this.index+=1;
    }
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
  width: 12%;
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
  margin-top: 30px; /* 顶部外边距 */
  padding: 20px; /* 内边距 */
  text-align: center; /* 文本居中对齐 */
  font-size: 24px; /* 字体大小 */
  font-weight: bold; /* 字体加粗 */
  color: #333; /* 字体颜色 */
  /*background-color: green; /* 背景颜色 */
  line-height: 24px;
  background-image: url(./components/icons/OIP-C.jpg);
  height: 850px;
} 
.card .cardcontentforheader {
  text-align: left; /* 文本居左对齐 */
  padding: 20px; /* 内边距 */
  color: #666; /* 字体颜色 */
  line-height: 36px;
  font-size: 24px; /* 字体大小 */
  white-space: pre-wrap; /* 保持空白符和换行符 */
  margin-right: 100px;
}
.card .cardcontent {
  text-align: left; /* 文本居左对齐 */
  padding: 20px; /* 内边距 */
  color: #666; /* 字体颜色 */
  line-height: 36px;
  font-size: 24px; /* 字体大小 */
  white-space: pre-wrap; /* 保持空白符和换行符 */
  
}
.card .imgofperson{
  width: 300px;
  border-radius: 50%;
  position: absolute;
  left: 10px;
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
.el-row {
  margin-bottom: 20px;
}
.el-row:last-child {
  margin-bottom: 0;
}
.el-col {
  border-radius: 4px;
}

.grid-content {
  border-radius: 4px;
  min-height: 36px;
}
</style>