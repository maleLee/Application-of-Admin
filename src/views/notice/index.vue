<template>
  <div class="app-container">
    <el-row>
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>分类</span>
        </div>
        <div style="margin-bottom:50px;">
          <el-col :span="2" class="text-center" @click.native="changeType(0)">
            <div class="pan-btn pink-btn">
              通知
            </div>
          </el-col>
          <el-col :span="2" class="text-center" @click.native="changeType(1)">
            <div class="pan-btn green-btn">
              会议
            </div>
          </el-col>
          <el-col :span="2" class="text-center" @click.native="changeType(2)">
            <div class="pan-btn yellow-btn">
              公示
            </div>
          </el-col>
        </div>
      </el-card>
    </el-row>
    <el-row :gutter="20">
      <el-col v-for="(item,index) in list" :key="index" :span="6" style="margin-top:10px;">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span class="title">{{ item.title }}</span><span class="postdate">Postde on:{{ item.postdate }}</span>
          </div>
          <div class="component-item" style="height:320px;">
            <div v-if="item.time">
              <span class="title">时间：</span>
              <span class="font-sm">{{ item.time }}</span>
            </div>
            <div v-if="item.place" class="margin-top">
              <span class="title">地点：</span>
              <span class="font-sm">{{ item.place }}</span></div>
            <div class="margin-top">{{ item.desc }}</div>
          </div>
        </el-card>
      </el-col>
    </el-row>
    <!-- <aside>
      The guide page is useful for some people who entered the project for the first time. You can briefly introduce the
      features of the project. Demo is based on
      <a href="https://github.com/kamranahmedse/driver.js" target="_blank">driver.js.</a>
    </aside>
    <el-button icon="el-icon-question" type="primary" @click.prevent.stop="guide">
      Show Guide
    </el-button> -->
  </div>
</template>

<script>
// import Driver from 'driver.js' // import driver.js
// import 'driver.js/dist/driver.min.css' // import driver.js css
// import steps from './steps'

export default {
  name: 'Notice',
  data() {
    return {
      // driver: null
      list: [
        { id: 1, title: '第一次通知', postdate: '2020-1-12 10:11:12', time: '2020-2-1 11:10:00', place: '弘德楼', desc: '请申请入党的同学注意。。。' },
        { id: 1, title: '第二次通知', postdate: '2020-1-12 10:11:12', time: '2020-2-1 11:10:00', place: '弘德楼', desc: '请申请入党的同学注意。。。' },
        { id: 1, title: '第三次通知', postdate: '2020-1-12 10:11:12', time: '2020-2-1 11:10:00', place: '弘德楼', desc: '请申请入党的同学注意。。。' }
      ]
    }
  },
  mounted() {
    // this.driver = new Driver()
  },
  methods: {
    changeType(type) {
      console.log(type)
      switch (type) {
        case 0:
          this.list = [
            { id: 1, title: '第一次通知', postdate: '2020-1-12 10:11:12', time: null, place: null, desc: '请申请入党的同学注意。。。' },
            { id: 1, title: '第二次通知', postdate: '2020-1-12 10:11:12', time: null, place: null, desc: '请申请入党的同学注意。。。' },
            { id: 1, title: '第三次通知', postdate: '2020-1-12 10:11:12', time: null, place: null, desc: '请申请入党的同学注意。。。' }
          ]
          break
        case 1:
          this.list = [
            { id: 1, title: '第一次会议', postdate: '2020-1-12 10:11:12', time: '2020-2-1 11:10:00', place: '弘德楼', desc: '请申请入党的同学注意。。。' },
            { id: 1, title: '第二次会议', postdate: '2020-1-12 10:11:12', time: '2020-2-1 11:10:00', place: '弘德楼', desc: '请申请入党的同学注意。。。' },
            { id: 1, title: '第三次会议', postdate: '2020-1-12 10:11:12', time: '2020-2-1 11:10:00', place: '弘德楼', desc: '请申请入党的同学注意。。。' }
          ]
          break
        case 2:
          this.list = [
            { id: 1, title: '第一次公示', postdate: '2020-1-12 10:11:12', time: null, place: null, desc: '请申请入党的同学注意。。。' },
            { id: 1, title: '第二次公示', postdate: '2020-1-12 10:11:12', time: null, place: null, desc: '请申请入党的同学注意。。。' },
            { id: 1, title: '第三次公示', postdate: '2020-1-12 10:11:12', time: null, place: null, desc: '请申请入党的同学注意。。。' }
          ]
          break
        default:
          break
      }
    }
    // guide() {
    //   this.driver.defineSteps(steps)
    //   this.driver.start()
    // }
  }
}
</script>
<style scoped>
  .pan-btn {
    cursor: pointer;
  }

  .title {
    font-weight: bold;
  }

  .postdate {
    color: rgb(180, 180, 180);
    margin-left: 10px;
    font-size: 12px;
  }

  .margin-top {
    margin-top: 10px;
  }

  .font-sm {
    font-size: 14px;
  }
</style>
