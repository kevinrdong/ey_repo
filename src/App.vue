<template>
  <div id="app">
    <div class="inn">
      <h1 class="p1">There is no one</h1>
      <h2 class="p2">who loves pain</h2>
      <!-- <img src="./assets/白色海浪.png" alt="" class="back" /> -->
      <a href="#anchor" class="btn_form"
        ><img src="./assets/form.png" alt=""
      /></a>
      <div class="info">
        <div class="sup supB">
          <img src="./assets/sup.png" alt="" class="supB1" />
          <img src="./assets/船槳.png" alt="" class="supB2" />
          <img src="./assets/泡泡.png" alt="" class="supB3" />
          <img src="./assets/泡泡-1.png" alt="" class="supB4" />
        </div>
        <div class="sup supF">
          <img src="./assets/sup煙火.png" alt="" class="supF1" />
          <img src="./assets/煙火.png" alt="" class="supF2" />
        </div>
        <div class="title">
          <img src="./assets/cactus.png" alt="" />
          <p class="pt1p">paragraph</p>
          <img src="./assets/cactus.png" alt="" />
        </div>
        <ol>
          <li>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</li>
        </ol>
        <div class="title">
          <img src="./assets/cactus.png" alt="" />
          <p class="pt1p">paragraph</p>
          <img src="./assets/cactus.png" alt="" />
        </div>
        <ol>
          <li>
            Quisque sodales leo vitae <u><b>vulputate auctor.</b></u>
          </li>
          <li>
            Proin ac justo ut nisl tincidunt imperdiet.Maecenas viverra libero a
            pellentesque blandit.
          </li>
          <li>
            Cras tristique tellus id leo bibendum, eu dapibus nisl accumsan.
          </li>
          <li>Donec ultrices sapien <b>vitae leo venenatis ullamcorper.</b></li>
        </ol>
      </div>
    </div>
    <div class="waves">
      <img src="./assets/海浪.png" alt="" class="wave" />
      <img src="./assets/海浪.png" alt="" class="wave" />
      <img src="./assets/海浪.png" alt="" class="wave" />
    </div>
    <div class="part2">
      <div class="inn2">
        <img src="./assets/Frame18.png" alt="" class="Frame18" id="anchor" />
        <div class="form">
          <img src="./assets/turtle.png" alt="" class="turtle" />
          <div class="sub">
            <label name="store">store</label>
            <div class="warn">*</div>
          </div>
          <input
            id="store"
            type="text"
            list="typelist"
            placeholder="placeholder text"
            class="search"
            v-model="storeVal"
            v-bind:class="{ err: !storeValid }"
          />
          <div class="error" v-if="!storeValid && storeVal !== ''">
            wrongformat
          </div>
          <div class="error" v-if="!storeValid && storeVal == ''">required</div>
          <datalist id="typelist">
            <option value="store1">store1</option>
            <option value="store2">store2</option>
            <option value="store3">store3</option>
          </datalist>
          <div class="sub">
            <label name="name">name</label>
            <div class="warn">*</div>
          </div>
          <input
            class="search"
            type="text"
            placeholder="placeholder text"
            v-model="nameVal"
            v-bind:class="{ err: !nameValid }"
          />
          <div class="error" v-if="!nameValid && nameVal !== ''">
            wrongformat
          </div>
          <div class="error" v-if="!nameValid && nameVal == ''">required</div>
          <div class="sub">
            <label name="phone">phone</label>
            <div class="warn">*</div>
          </div>
          <input
            class="search phonesearch"
            type="number"
            placeholder="placeholder text"
            pattern="[0-9]{4}-[0-9]{3}-[0-9]{3}"
            v-model="phoneVal"
            v-bind:class="{ err: !phoneValid }"
          />
          <div class="error" v-if="!phoneValid && phoneVal !== ''">
            wrongformat
          </div>
          <div class="error" v-if="!phoneValid && phoneVal == ''">required</div>
          <div class="sub">
            <label name="Amount">Amount of consumption</label>
            <div class="warn">*</div>
          </div>
          <input
            class="search"
            type="text"
            placeholder="placeholder text"
            v-model="amountVal"
            v-bind:class="{ err: !amountValid }"
          />
          <div class="error" v-if="!amountValid && amountVal !== ''">
            wrongformat
          </div>
          <div class="error" v-if="!amountValid && amountVal == ''">
            required
          </div>
          <div class="sub">
            <label name="payment">payment</label>
            <div class="warn">*</div>
          </div>
          <input
            class="search"
            type="text"
            list="typelist2"
            placeholder="placeholder text"
            v-model="paymentVal"
            v-bind:class="{ err: !paymentValid }"
          />
          <div class="error" v-if="!paymentValid && paymentVal !== ''">
            wrongformat
          </div>
          <div class="error" v-if="!paymentValid && paymentVal == ''">
            required
          </div>
          <datalist id="typelist2">
            <option value="digital payment">digital payment</option>
            <option value="ATM">ATM</option>
          </datalist>
        </div>
        <div class="submit" @click="submitted">
          <div class="submit-img">
            <img src="./assets/submit.png" v-if="!ifSubmit" />
            <img src="./assets/Text.png" v-if="susses" />
            <img src="./assets/TextF.png" v-if="showF" />
          </div>
        </div>
        <div class="container">
          <div
            v-for="(con, index) in cons"
            :key="index"
            :class="`containers ${con.className}`"
          >
            <div class="conlet">{{ con.conLetter }}</div>
            <img :src="con.conImg" alt="" class="conin" />
            <img :src="con.conCer" alt="" class="concer" />
            <div class="connum">{{ con.conNum }}</div>
            <div class="conpa">{{ con.conPa }}</div>
          </div>
        </div>
        <div class="word">
          <div class="line line1"></div>
          <div class="pag">
            <p class="pagp pagp1"><b>13.32</b></p>
            <p class="pagp pagp2">who seeks after it and</p>
            <p class="pagp pagp2">wants to have it</p>
          </div>
          <div class="line line2"></div>
        </div>
        <div class="light">
          <img src="./assets/lighthouse.png" alt="" class="lighthouse" />
        </div>
      </div>
    </div>

    <div class="inn3">
      <div class="wod"><br />Neque porro quisquam<br />est qui dolorem!</div>
      <img src="./assets/market.png" alt="" class="market" />
    </div>
  </div>
</template>

<script>
import Rectangle from "./assets/Rectangle412.png";
import certificateA from "./assets/certificateA.png";
import certificateD from "./assets/certificateD.png";

export default {
  name: "App",
  data() {
    return {
      cons: [
        {
          conPa: "dehumidifier",
          conImg: Rectangle,
          conNum: "ONE",
          conLetter: "A",
          conCer: certificateA,
          className: "asd",
        },
        {
          conPa: "range hood",
          conImg: Rectangle,
          conNum: "ONE",
          conLetter: "B",
          conCer: certificateA,
          className: "asd",
        },
        {
          conPa: "vacuum cleaner",
          conImg: Rectangle,
          conNum: "ONE",
          conLetter: "C",
          conCer: certificateA,
          className: "asd",
        },
        {
          conPa: "toaster",
          conImg: Rectangle,
          conNum: "ONE",
          conLetter: "D",
          conCer: certificateD,
          className: "zxc",
        },
        {
          conPa: "scale",
          conImg: Rectangle,
          conNum: "ONE",
          conLetter: "E",
          conCer: certificateD,
          className: "zxc",
        },
        {
          conPa: "straightening iron",
          conImg: Rectangle,
          conNum: "ONE",
          conLetter: "F",
          conCer: certificateD,
          className: "zxc",
        },
        {
          conPa: "vacuum cleaner",
          conImg: Rectangle,
          conNum: "FIVE",
          conLetter: "G",
          conCer: certificateD,
          className: "zxc",
        },
        {
          conPa: "rice cooker",
          conImg: Rectangle,
          conNum: "TEN",
          conLetter: "H",
          conCer: certificateD,
          className: "zxc",
        },
      ],
      storeVal: "",
      storeValid: true,
      nameVal: "",
      nameValid: true,
      phoneVal: "",
      phoneValid: true,
      amountVal: "",
      amountValid: true,
      paymentVal: "",
      paymentValid: true,
      ifSubmit: false,
      susses: false,
      showF: false,
    };
  },
  watch: {
    storeVal: "storeCheck",
    nameVal: "nameCheck",
    phoneVal: "phoneCheck",
    amountVal: "amountCheck",
    paymentVal: "paymentCheck",
    ifSubmit: "submittedCheck",
  },
  methods: {
    storeCheck() {
      if (
        this.storeVal == "store1" ||
        this.storeVal == "store2" ||
        this.storeVal == "store3"
      ) {
        this.storeValid = true;
      } else {
        this.storeValid = false;
      }
    },
    nameCheck() {
      if (isNaN(parseInt(this.nameVal))) {
        this.nameValid = true;
      } else {
        this.nameValid = false;
      }
    },
    phoneCheck() {
      console.log(this.phoneValid);
      const phoneNumber = parseFloat(this.phoneVal);
      if (
        !isNaN(phoneNumber) &&
        this.phoneVal.length == 10 &&
        phoneNumber >= 0 &&
        Number.isInteger(phoneNumber)
      ) {
        this.phoneValid = true;
      } else {
        this.phoneValid = false;
      }
    },
    amountCheck() {
      if (!isNaN(this.amountVal) && this.amountVal > 0) {
        this.amountValid = true;
      } else {
        this.amountValid = false;
      }
    },
    paymentCheck() {
      if (this.paymentVal == "digital payment" || this.paymentVal == "ATM") {
        this.paymentValid = true;
      } else {
        this.paymentValid = false;
      }
    },
    submitted() {
      if (
        this.storeVal == "" ||
        this.nameVal == "" ||
        this.phoneVal == "" ||
        this.amountVal == "" ||
        this.paymentVal == ""
      ) {
        this.ifSubmit = false;
        this.storeValid = false;
        this.nameValid = false;
        this.phoneValid = false;
        this.amountValid = false;
        this.paymentValid = false;
      } else {
        this.ifSubmit = true;
      }
    },
    submittedCheck() {
      if (
        this.storeValid == true &&
        this.nameValid == true &&
        this.phoneValid == true &&
        this.amountValid == true &&
        this.paymentValid == true
      ) {
        this.susses = true;
      } else {
        this.susses = false;
        this.showF = true;
      }
    },
  },
};
</script>

<style lang="scss">
@import url(//fonts.googleapis.com/earlyaccess/notosanstc.css);

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
}

input[type="number"] {
  -moz-appearance: textfield;
}

html {
  background-image: url("./assets/底色.png");
  position: relative;
  display: flex;
  scroll-behavior: smooth;
}

body {
  /* 先套用 Noto Sans TC 這個 思源黑體 */
  font-family: "Noto Sans TC", "微軟正黑體", sans-serif;
  width: 100%;
  height: 100%;
}

#app {
  background-image: url("./assets/白色海浪.png");
  position: relative;
  width: 100%;
  height: 100vh;
  background-repeat: no-repeat;
  background-position: 20% 200%;
  background-size: 100%, 120%;
  // background-attachment: fixed;
  .inn {
    position: relative;
    display: flex;
    max-width: 1024px;
    margin: 0 auto;
    // border: 1px solid;
    flex-direction: column;

    .back {
      position: relative;
      width: 100%;
      height: 100%;
      top: 10%;
      left: 50%;
      transform: translate(-50%, -74%);
      z-index: -1;
    }

    .btn_form {
      position: relative;
      margin: 0 auto;
    }

    .p1 {
      position: relative;
      // width: 400px;
      height: 40px;
      font-weight: 700;
      font-size: 32px;
      line-height: 125%;
      color: #ffffff;
      font-family: "Noto Sans TC";
      font-style: normal;
      letter-spacing: 0.2em;
      margin: 0 auto;
      // transform: translate(-50%, -50%);
    }

    .p2 {
      position: relative;
      // width: 278px;
      height: 35px;
      font-family: "Noto Sans TC";
      font-style: normal;
      font-weight: 700;
      font-size: 28px;
      line-height: 125%;
      // text-align: center;
      letter-spacing: 0.2em;
      color: #ffffff;
      margin: 0 auto;
    }

    .info {
      border: 2px solid;
      border-radius: 20px;
      border-color: #b57556;
      margin: 0 auto;
      margin-top: 32px;
      width: 808px;
      height: 322px;
      background-color: #dae4f1;

      .sup {
        position: absolute;
      }
      .supB {
        right: 11%;
        top: 33%;
        .supB2 {
          position: absolute;
          right: 0px;
          top: 13px;
        }
        .supB3 {
          position: absolute;
          right: 40%;
          top: -28%;
        }
        .supB4 {
          position: absolute;
          right: 26%;
          top: -65%;
        }
      }
      .supF {
        left: 15%;
        bottom: -11%;

        .supF1 {
          width: 105%;
          height: 105%;
        }
        .supF2 {
          position: absolute;
          bottom: 9%;
          left: -27%;
        }
      }
      .title {
        position: relative;
        display: flex;
        flex-direction: row;
        left: 50%;
        transform: translate(-10%, 0%);
        color: #204379;
        font-family: "Noto Sans TC";
        font-style: normal;
        font-weight: 700;
        font-size: 18px;
        line-height: 125%;

        img {
          width: 30px;
          height: 40px;
          margin-right: 5px;
          margin-top: 5px;
        }
      }

      ol {
        color: #204379;
        width: 776px;
        height: 22px;
        font-family: "Noto Sans TC";
        font-style: normal;
        font-weight: 400;
        font-size: 16px;
        line-height: 140%;
      }
    }
  }

  .waves {
    display: flex;
    overflow: hidden;
    .wave {
      margin-top: 52px;
      margin-left: 0px;
    }
  }

  .part2 {
    position: relative;
    display: flex;
    top: -1px;
    width: 100%;
    height: 220%;
    background-color: #e2d9d3;
    margin-bottom: 0px;

    .inn2 {
      position: relative;
      display: flex;
      width: 1024px;
      max-width: 1024px;
      margin: 0 auto;
      // border: 1px solid;
      flex-direction: column;
      margin-top: 60px;

      .Frame18 {
        width: 123px;
        height: 55px;
        position: relative;
        margin: 0 auto;
        top: 1.5%;
      }
      .form {
        background-color: #ffffff;
        margin: 0 auto;
        border: #b57556 2px solid;
        border-radius: 16px;
        padding: 5%;

        .turtle {
          position: absolute;
          right: 41%;
          top: 1.2%;
        }

        input {
          width: 100%;
          padding: 12px 20px;
          margin: 8px 0;
          box-sizing: border-box;
          border: 3px solid #204379;
          -webkit-transition: 0.5s;
          transition: 0.5s;
          outline: none;
        }

        input:focus {
          border: solid 3px #93bbf9;
        }

        .err {
          border: 3px solid #e06d6d;
        }

        label {
          // width: 38px;
          height: 22px;
          color: #204379;
          margin-bottom: 3px;
        }
        .error {
          color: #e06d6d;
          font-family: "Noto Sans TC";
          font-style: normal;
          font-weight: 400;
          font-size: 12px;
          line-height: 140%;
        }
        .sub {
          display: flex;
        }
        .warn {
          width: 8px;
          height: 20px;
          color: #b57556;
        }
        .search {
          width: 768px;
          height: 57px;
          border-radius: 20px;
        }
        .phonesearch {
          -moz-appearance: textfield;
        }
      }
      .submit {
        display: flex;
        .submit-img {
          margin: 0 auto;
          cursor: pointer;

          :active {
            opacity: 0.5;
          }
        }
      }
      .container {
        position: relative;
        display: flex;
        max-width: 830px;
        max-height: 600px;
        flex-wrap: wrap;
        left: 4%;
        margin: 0 auto;
        top: 4%;

        .asd {
          .concer {
            position: relative;
            top: -81px;
          }
        }
        .containers {
          justify-content: center;
          position: relative;
          margin-bottom: 0px;
          left: 30px;
          .conim {
            position: relative;
            width: 178px;
            height: 122px;
          }
          .concer {
            position: relative;
            right: 50%;
            bottom: 48%;
          }
          .connum {
            position: relative;
            font-size: 12px;
            color: #b3b960;
            border: #b3b960 1px solid;
            border-radius: 50px;
            width: 34px;
            height: 22px;
            text-align: center;
            left: 53%;
            bottom: 60%;
          }
          .conlet {
            position: relative;
            color: #ffffff;
            font-family: "Noto Sans TC";
            font-style: normal;
            font-weight: 700;
            font-size: 18px;
            left: 33%;
            bottom: -4%;
            padding: 2px;
            z-index: 2;
          }
          .conpa {
            position: relative;
            font-family: "Noto Sans TC";
            font-style: normal;
            font-weight: 700;
            font-size: 18px;
            line-height: 125%;
            color: #b3b960;
            bottom: 50%;
            right: 14%;
            text-align: center;
          }
        }
        .zxc {
          .connum {
            color: #a0bcc8;
            border: #a0bcc8 1px solid;
          }
          .conpa {
            color: #a0bcc8;
            right: 14%;
          }
        }
      }
      .word {
        position: relative;
        margin: 0 auto;
        display: flex;
        top: 5%;
        .pag {
          position: relative;
          margin: 0 auto;
          text-align: center;
          top: 8%;

          .pagp {
            font-family: "Noto Sans TC";
            font-style: normal;
            font-weight: 700;
            font-size: 20px;
            line-height: 140%;
            text-align: center;
          }
          .pagp1 {
            color: #b57556;
          }
          .pagp2 {
            color: #204379;
          }
        }
        .line {
          position: relative;
          width: 0px;
          height: 100px;
          border: #204379 solid 1px;
          top: 30%;
          margin: 13px;
        }
        .line1 {
          transform: rotate(-15deg);
        }
        .line2 {
          transform: rotate(15deg);
        }
      }
      .light {
        position: relative;
        margin: 0 auto;
        top: 6%;
      }
    }
  }
  .inn3 {
    position: relative;
    margin: 0 auto;
    height: 75vh;

    .wod {
      background-image: url("./assets/底色.png");
      border-radius: 60px;
      position: relative;
      text-align: center;
      font-family: "Noto Sans TC";
      font-style: normal;
      font-weight: 700;
      font-size: 20px;
      line-height: 200%;
      color: #ffffff;
      bottom: 7%;
    }
    .market {
      position: relative;
      left: 50%;
      transform: translate(-50%, -3%);
    }
  }
}

@media screen and (min-width: 415px) and (max-width: 769px) {
  body {
    position: relative;
    left: -8px;
  }
  #app {
    max-width: 768px;
    position: relative;
    width: 100%;
    height: 100vh;
    overflow-x: hidden;
    
    .inn {
      max-width: 768px;
      justify-content: center;
      .info {
        width: 720px;
        ol {
          width: 660px;
        }
        .title {
          transform: translate(-23%, 0%);
          margin-top: 15px;
          width: 300px;
          margin-right: 0px;
        }
        .supB {
          position: absolute;
          right: 6%;
        }
        .supF {
          left: 7%;
        }
      }
    }

    .waves {
      position: relative;
      top: 1px;
    }
    .part2 {
      max-width: 768px;
      height: 230%;
      .inn2 {
        max-width: 768px;
        justify-content: center;
        .Frame18 {
          top: -3.6%;
          position: relative;
          z-index: 2;
        }
        .submit {
          position: relative;
          top:-3%
        }
        .container {
          position: relative;
          top:-1%;
        }
        .form {
          max-width: 720px;
          bottom: 5%;
          position: relative;
          padding: 15px;
          .turtle {
            position: absolute;
            z-index: 2;
            top: -6%;
            right: 37%;
          }
          .search {
            width: 680px;
          }
        }
        .word {
          position: relative;
          top: -1%
        }
        .light {
          position: relative;
          top:0%;
        }
      }
    }
    .inn3 {
      position: relative;
      top: -11px;
    }
  }
}

@media screen and (max-width: 414px) {
  body {
    overflow-x: hidden;
    margin: 0px;
  }
  #app {
    max-width: 414px;

    .inn {
      max-width: 414px;
      .info {
        width: 366px;
        height: 489px;

        ol {
          width: 305px;
        }
        .title {
          transform: translate(-20%, 0%);
          margin-top: 25px;
        }
        .supB {
          position: absolute;
          right: 1%;
          top: 26%;
        }
        .supF {
          left: 7%;
          bottom: -7%;
        }
      }
    }
    .waves {
      position: relative;
      top: 1px;
    }
    .part2 {
      max-width: 414px;
      height: 230%;
      .inn2 {
        max-width: 414px;
        .form {
          width: 366px;
          position: relative;
          padding: 15px;
          .turtle {
          z-index: 3;
          position: absolute;
          right: 26%;
          top: -6%;
        }
          .search {
            width: 326px;
          }
        }
        .Frame18 {
          z-index: 2;
        }
        .container {
          width: 365px;
          margin: 0px;
          padding: 0px;
          .containers {
            margin-left: -62px;
            left: 68px;
          }
          .containers.asd.zxc {
            width: 178px;
            margin: 0px; 
          }
        }

        .word {
          position: relative;
          top: 12%;
        }
        .light {
          position: relative;
          top: 13%;
        }
      }
    }
    .inn3 {
        .wod {
          position: relative;
          letter-spacing: 0.2em;

        }
      }
  }
}
</style>
