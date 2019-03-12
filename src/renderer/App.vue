<template>
  <div id="app">
    <ul class="grid">
      <li v-for="gift in gifts" :key="gift.id">
        <div v-if="gift.check" class="check">
          <img v-bind:src="gift.icon">
        </div>
        <div v-else class="uncheck">
          <img v-bind:src="gift.icon">
        </div>
      </li>
    </ul>
    <div class="start">
      <span @click="play">开始</span>
    </div>
    <el-row :gutter="20">
  
</el-row>
    <div class="action-parent">
      <div v-for="action in actions" :key="action.id" class="action">
        <el-col :span="10"><div class="grid-content bg-purple">
    <el-input v-model="action.yy" placeholder="YY号" class="gift-select"></el-input>
    </div></el-col>
  <el-col :span="5"><div class="grid-content bg-purple">
    <el-input v-model="action.multiple" placeholder="倍数" type="number" class="gift-select"></el-input>
    </div></el-col>
  <el-col :span="5"><div class="grid-content bg-purple">
    <el-select
              @change="change(action)"
              v-model="action.tips"
              placeholder="礼物"
              class="gift-select"
              popper-class='uncheck'
            >
              <el-option v-for="item in gifts" :key="item.id" :label="item.id" :value="item.icon">
                <div class="gift-item">
                  <img v-bind:src="item.icon">
                </div>
              </el-option>
            </el-select>
    </div></el-col>
  <el-col :span="4"><div class="grid-content bg-purple gift-tips">
    <img v-if="action.gift" v-bind:src="action.gift" style="width: 42px; heigh: 42px"></div></el-col>
      </div>
    </div>
    <div @click="clear" class="start">
      <span>清空</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  components: {},
  data() {
    return {
      text: "",
      times: 0,
      gifts: [
        {
          id: 0,
          icon: __static + "/assets/icon/0.png",
          check: false,
          weight:1,
        },
        {
          id: 1,
          icon: __static + "/assets/icon/1.png",
          check: false,
          weight:1,
        },
        {
          id: 2,
          icon: __static + "/assets/icon/2.png",
          check: false,
          weight:1,
        },
        {
          id: 3,
          icon: __static + "/assets/icon/3.png",
          check: false,
          weight:1,
        },
        {
          id: 4,
          icon: __static + "/assets/icon/4.png",
          check: false,
          weight:1,
        },
        {
          id: 5,
          icon: __static + "/assets/icon/5.png",
          check: false,
          weight:1,
        },
        {
          id: 6,
          icon: __static + "/assets/icon/6.png",
          check: false,
          weight:1,
        },
        {
          id: 7,
          icon: __static + "/assets/icon/7.png",
          check: false,
          weight:1,
        },
        {
          id: 8,
          icon: __static + "/assets/icon/8.png",
          check: false,
          weight:1,
        },
        {
          id: 9,
          icon: __static + "/assets/icon/9.png",
          check: false,
          weight:1,
        },
        {
          id: 10,
          icon: __static + "/assets/icon/10.png",
          check: false,
          weight:1,
        },
        {
          id: 11,
          icon: __static + "/assets/icon/11.png",
          check: false,
          weight:1,
        },
        {
          id: 12,
          icon: __static + "/assets/icon/12.png",
          check: false,
          weight:1,
        },
        {
          id: 13,
          icon: __static + "/assets/icon/13.png",
          check: false,
          weight:1,
        },
        {
          id: 14,
          icon: __static + "/assets/icon/14.png",
          check: false,
          weight:1,
        },
        {
          id: 15,
          icon: __static + "/assets/icon/15.png",
          check: false,
          weight:1,
        },
        {
          id: 16,
          icon: __static + "/assets/icon/16.png",
          check: false,
          weight:1,
        },
        {
          id: 17,
          icon: __static + "/assets/icon/17.png",
          check: false,
          weight:1,
        },
        {
          id: 18,
          icon: __static + "/assets/icon/18.png",
          check: false,
          weight:1,
        },
        {
          id: 19,
          icon: __static + "/assets/icon/19.png",
          check: false,
          weight:1,
        },
        {
          id: 20,
          icon: __static + "/assets/icon/20.png",
          check: false,
          weight:1,
        },
        {
          id: 21,
          icon: __static + "/assets/icon/21.png",
          check: false,
          weight:1,
        },
        {
          id: 22,
          icon: __static + "/assets/icon/22.png",
          check: false,
          weight:1,
        },
        {
          id: 23,
          icon: __static + "/assets/icon/23.png",
          check: false,
          weight:1,
        },
        {
          id: 24,
          icon: __static + "/assets/icon/24.png",
          check: false,
          weight:1,
        },
        {
          id: 25,
          icon: __static + "/assets/icon/25.png",
          check: false,
          weight:1,
        },
        {
          id: 26,
          icon: __static + "/assets/icon/26.png",
          check: false,
          weight:1,
        },
        {
          id: 27,
          icon: __static + "/assets/icon/27.png",
          check: false,
          weight:1,
        },
        {
          id: 28,
          icon: __static + "/assets/icon/28.png",
          check: false,
          weight:1,
        },
        {
          id: 29,
          icon: __static + "/assets/icon/29.png",
          check: false,
          weight:1,
        },
        {
          id: 30,
          icon: __static + "/assets/icon/30.png",
          check: false,
          weight:1,
        },
        {
          id: 31,
          icon: __static + "/assets/icon/31.png",
          check: false,
          weight:1,
        },
        {
          id: 32,
          icon: __static + "/assets/icon/32.png",
          check: false,
          weight:1,
        }
      ],
      actions: [
        {
          id: 0,
          yy: "",
          gift: "",
          tips: "礼物",
          multiple: ""
        },
        {
          id: 1,
          yy: "",
          gift: "",
          tips: "礼物",
          multiple: ""
        },
        {
          id: 2,
          yy: "",
          gift: "",
          tips: "礼物",
          multiple: ""
        },
        {
          id: 3,
          yy: "",
          gift: "",
          tips: "礼物",
          multiple: ""
        },
        {
          id: 4,
          yy: "",
          gift: "",
          tips: "礼物",
          multiple: ""
        },
        {
          id: 5,
          yy: "",
          gift: "",
          tips: "礼物",
          multiple: ""
        },
        {
          id: 6,
          yy: "",
          gift: "",
          tips: "礼物",
          multiple: ""
        },
        {
          id: 7,
          yy: "",
          gift: "",
          tips: "礼物",
          multiple: ""
        },
        {
          id: 8,
          yy: "",
          gift: "",
          tips: "礼物",
          multiple: ""
        },
        {
          id: 9,
          yy: "",
          gift: "",
          tips: "礼物",
          multiple: ""
        }
      ]
    };
  },
  methods: {
    play() {
      if (this.times == 0) {
        this.start();
      }
    },
    start() {
      let that = this;
      if (this.times >= 20) {
        this.times = 0;
        return;
      }
      setTimeout(() => {
        this.times++;
        this.gifts.forEach(gift => {
          gift.check = false;
        });
        this.gifts[this.getIndex() % this.gifts.length].check = true;
        this.start();
      }, 250);
    },
    change(e) {
      e.gift = e.tips;
      e.tips = "礼物";
    },
    clear() {
      this.actions.forEach(action => {
        action.yy = "";
        action.gift = "";
        action.multiple = "";
        action.tips = "礼物";
      });
    },
    getIndex() {
        let giftIndex = [];
        this.gifts.forEach(gift => {
            for(let i = 0; i < gift.weight; i++){
                giftIndex.push(gift.id);
            }
        });
        let index = Math.floor(Math.random() * giftIndex.length);
        return giftIndex[index];
    }
  }
};
</script>

<style lang="scss">
#app {
  display: flex;
  flex-direction: column;
}
.check {
  background: #f00;
}

.uncheck {
  background: #fff;
}

ul.grid {
  list-style: none;
  width: 550px;
  margin: 0 auto;
  text-align: left;
}

ul.grid li div {
  padding: 2px;
  float: left;
  cursor: pointer;
  border: 1px solid #e8e8e8;
  box-sizing: border-box;
}

ul.grid li div img {
  width: 40px;
  height: 40px;
  object-fit: cover;
  display: block;
  border: none;
  box-sizing: border-box;
}

.start {
  display: flex;
  justify-content: center;
  padding-top: 10px;
  margin-bottom: 10px;
}

.start span {
  border: 1px solid #e8e8e8;
  background: #09f;
  padding-top: 10px;
  color: #fff;
  size: 16px;
  padding-bottom: 10px;
  padding-left: 80px;
  padding-right: 80px;
  cursor: pointer;
}
.action-parent {
  flex-grow: 2;
  display: flex;
  flex-direction: column;
  border: 2px solid #09f;
  padding-bottom: 20px;
  width: 60%;
  margin-left: 20%;
  //   float: left;
  //   overflow: scroll;
}

.action {
  // flex-direction:column;
  justify-content: center;
  display: flex;
  width: 100%;
  display: flex;
  margin-top: 10px;
}

.action input {
  height: 42px;
}

.gift-tips {
  display: flex;
  justify-content: center;
  align-content: center;
  height: 100%;
  
}
.gift-select {
  display: flex;
  justify-content: center;
  align-content: center;
  width: 80%;
  margin-left: 10%;
  margin-right: 10%;
  //   overflow: hidden;
  align-self: center;
}

ul {
    list-style-type: none;
}

.gift-item {
    display: flex;
    justify-content: center;
  align-content: center;
  padding-right: 40px;
}
</style>
