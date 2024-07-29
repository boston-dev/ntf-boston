<template>
  <div class="font12">
    <van-sticky>
      <ul class="nav justify-between align-center">
        <li class="logo center-center">
          <img class="d-img" src="@/assets/img/ntf/home/logo.png" alt="" />
        </li>
        <li class="flex-1 text-center txt">logo.com</li>
        <li class="align-center lef-icon">
          <p class="m-r-16">
            <img class="d-img" src="@/assets/img/ntf/home/nav1.png" alt="" />
          </p>
          <p class="m-r-16">
            <img class="d-img" src="@/assets/img/ntf/home/nav2.png" alt="" />
          </p>
        </li>
      </ul>
    </van-sticky>
    <ul class="p-l-16 p-r-16 center-center els m-t-8 m-b-12">
      <li class="live">
        <img src="@/assets/img/ntf/home/ligth.png" alt="" />
      </li>
      <li class="m-r-8 m-l-8 center-center flex-1 money-list">
        <div class="p-x-4">
          <p class="els">{{ $t(`user.money.available`) }}</p>
          <p class="m-t-4 els">{{ divide(user.balance) }}</p>
        </div>
        <div class="p-x-4">
          <p class="els">{{ $t(`user.money.purchased`) }}</p>
          <p class="m-t-4 els">{{ divide(user.frozenBet) }}</p>
        </div>
      </li>
      <li class="serve">
        <img class="d-img" src="@/assets/img/ntf/home/serve.png" alt="" />
      </li>
    </ul>
    <div class="shop m-l-16 m-r-16 m-b-24">
      <ul class="text-center user-info">
        <li class="username blod">{{ user.username }}</li>
        <li class="vipLevel m-t-4" v-if="user.vipLevel">
          LV.{{ user.vipLevel }}
        </li>
      </ul>
      <ul class="enter justify-between p-l-16 p-r-16">
        <li
          class="flex-column center-center"
          @click="$router.push({ path: '/pages/home/gameTools' })"
        >
          <div class="els desc">
            <p class="m-b-8 els">{{ $t(`user.Item.shop`) }}</p>
          </div>

          <p><img src="@/assets/img/ntf/home/shop1.png" alt="" /></p>
        </li>
        <li
          class="flex-column center-center"
          @click="$router.push({ path: '/pages/function/rebate_center' })"
        >
          <div class="els desc">
            <p class="m-b-8 els">{{ $t(`fuc.rebate.center`) }}</p>
          </div>
          <p><img src="@/assets/img/ntf/home/shop2.png" alt="" /></p>
        </li>
      </ul>
      <ul class="nav-enter-list justify-between els">
        <li
          class="els"
          @click="$router.push({ path: '/pages/wallet/onlineRecharge' })"
        >
          {{ $t(`deal_deposit`) }}
        </li>
        <li class="els" @click="$router.push({ path: '/wallet/withdraw' })">
          {{ $t(`dropdown.billing.income.withdraw.text`) }}
        </li>
        <li class="els" @click="$router.push({ path: '/pages/wallet/index' })">
          {{ $t("fuc.safe.text") }}
        </li>
      </ul>
    </div>
    <div
      class="game-hot"
      @click="$router.push({ path: '/pages/information/information' })"
    >
      <div class="center-center hot-title p-t-8 text-center">
        <p>
          <img src="@/assets/img/ntf/home/rit.png" alt="" />
        </p>
        <ul class="trading m-l-8 m-r-8">
          <li class="els">{{ $t(`user.platform.trading`) }}</li>
          <li class="els">{{ $t(`user.platform.trading.desc`) }}</li>
        </ul>
        <p>
          <img src="@/assets/img/ntf/home/left.png" alt="" />
        </p>
      </div>
      <p class="center-center more color-active">
        {{ $t(`user.platform.more`) }}
        <van-icon class="m-l-4" name="arrow" />
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeView",
  data() {
    return {};
  },
  computed: {
    user() {
      return this.$store.state.user;
    },
  },
  methods: {
    informationDealSold() {},
  },
  created() {
    this.$store.commit("setPdTop", false);
  },
};
</script>
<style lang="less" scoped>
.nav {
  height: 46px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  background-color: var(--bg-body);
  .logo {
    width: 77px;
    position: relative;
    img {
      width: 34px;
      height: 34px;
    }
    &::before {
      content: "";
      position: absolute;
      top: 50%;
      height: 18px;
      transform: translateY(-50%);
      right: 0;
      border: 1px solid transparent;
      border-image: linear-gradient(
          to bottom,
          rgba(255, 255, 255, 0),
          #888 52%,
          rgba(128, 128, 128, 0)
        )
        1;
    }
  }
  .lef-icon {
    img {
      height: 32px;
      width: 32px;
    }
  }
  .txt {
    font-size: 16px;
    font-weight: bold;
  }
}
.money-list {
  //width: 220.5px;
  text-align: center;
  height: 38.2px;
  border-radius: 9.5px;
  border: solid 1px #2c2c2c;
  background-image: linear-gradient(to bottom, #000, #373334);
  font-size: 10px;
  & > div {
    width: 50%;
  }
  & > div:nth-child(1) {
    background-image: linear-gradient(
      to bottom,
      rgba(255, 153, 123, 0) 0%,
      rgba(255, 58, 0, 0.33) 100%
    );
    border-radius: 9px;
  }
}
.live {
  img {
    height: 26px;
  }
}
.serve {
  width: 31px;
  height: 31px;
}
.shop {
  background: url("@/assets/img/ntf/home/shop.png") no-repeat;
  background-size: 100% 100%;
  height: 236px;
  position: relative;
  .vipLevel {
    color: #858585;
  }
  .user-info {
    height: 48px;
  }
  .enter {
    .desc {
      max-width: 97px;
    }
    img {
      height: 67px;
      width: 67px;
    }
  }
  .nav-enter-list {
    position: absolute;
    left: 0;
    right: 0;
    bottom: -16px;
    & > li {
      width: 97px;
      height: 45px;
      line-height: 45px;
      text-align: center;
      background: url("@/assets/img/ntf/home/desc1.png") no-repeat;
      background-size: 100% 100%;
    }
    & > li:nth-child(2) {
      background-image: url("@/assets/img/ntf/home/desc2.webp");
    }
    & > li:nth-child(3) {
      background-image: url("@/assets/img/ntf/home/desc3.webp");
    }
  }
}
.game-hot {
  height: 225px;
  background: url("@/assets/img/ntf/home/gamehot.png") no-repeat;
  background-size: 100% 100%;
  position: relative;
  .hot-title {
    img {
      height: 24px;
      width: 24px;
    }
  }
  .trading {
    width: 158px;
  }
  .more {
    position: absolute;
    line-height: 1;
    right: 16px;
    top: 16px;
  }
}
</style>
