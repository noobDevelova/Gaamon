<template>
  <div class="payment-method-box">
    <div class="box-header">
      <h3>Payment Method</h3>
      <router-link to="/" class="close-button">
        <span class="material-symbols-outlined"> close </span>
      </router-link>
    </div>
    <div class="box-body">
      <div class="dropdown">
        <button class="dropdown-button" type="button" @click="toggleMenuBank">
          Bank
          <span class="text-end">
            Choose Bank
            <span class="material-symbols-outlined"> expand_more </span>
          </span>
        </button>
        <ul class="menu-down" :class="{ hide: isExpandedBank }">
          <li v-for="bank in banks" :key="bank">
            <img :src="bank.img" alt="" />
            <a class="menu-item" href="#">{{ bank.name }}</a>
          </li>
        </ul>
      </div>
      <div class="dropdown">
        <button class="dropdown-button" type="button" @click="toggleMenuWallet">
          E-Wallet
          <span class="text-end">
            Choose E-Wallet
            <span class="material-symbols-outlined"> expand_more </span>
          </span>
        </button>
        <ul class="menu-down" :class="{ hide: isExpandedWallet }">
          <li v-for="wallet in wallets" :key="wallet">
            <img :src="wallet.img" alt="" />
            <a class="menu-item" href="#">{{ wallet.name }}</a>
          </li>
        </ul>
      </div>
      <div class="add-button">
        <p>Add Payment</p>
        <button class="button-payment" type="button">
          <span class="material-symbols-outlined"> add_circle </span>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isExpandedBank: true,
      isExpandedWallet: true,
      banks: [
        {
          name: "BCA",
          img: require("@/assets/img/bca_logo.svg"),
        },
        {
          name: "BNI",
          img: require("@/assets/img/bni_logo.svg"),
        },
        {
          name: "CIMB",
          img: require("@/assets/img/cimb_logo.svg"),
        },
        {
          name: "Mandiri",
          img: require("@/assets/img/mandiri_logo.svg"),
        },
        {
          name: "BRI",
          img: require("@/assets/img/bri_logo.svg"),
        },
        {
          name: "Permata",
          img: require("@/assets/img/permata_logo.svg"),
        },
        {
          name: "Danamon",
          img: require("@/assets/img/danamon_logo.svg"),
        },
        {
          name: "BJB",
          img: require("@/assets/img/bjb_logo.svg"),
        },
      ],
      wallets: [
        {
          name: "Gopay",
          img: require("@/assets/img/gopay_logo.svg"),
        },
        {
          name: "OVO",
          img: require("@/assets/img/ovo_logo.svg"),
        },
        {
          name: "Dana",
          img: require("@/assets/img/dana_logo.svg"),
        },
        {
          name: "LinkAja",
          img: require("@/assets/img/linkaja_logo.svg"),
        },
        {
          name: "ShopeePay",
          img: require("@/assets/img/shopeepay_logo.svg"),
        },
      ],
    };
  },
  methods: {
    toggleMenuBank() {
      if (this.isExpandedWallet == false) {
        this.isExpandedWallet = true;
      }
      this.isExpandedBank = !this.isExpandedBank;
    },
    toggleMenuWallet() {
      this.isExpandedWallet = !this.isExpandedWallet;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.payment-method-box {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 700px;
  background-color: $kuningEternal;
  border: 1px solid #000000;
  box-shadow: 2px 2px 0px #000000;

  .box-header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    border-bottom: 2px solid black;
    padding: 30px 20px 30px 25px;

    h3 {
      @include font-weight(bold);
      font-size: 18px;
      line-height: 19.6px;
    }

    .close-button {
      width: 30px;
      height: 30px;
      border: 1px solid #000000;
      box-shadow: 2px 2px 0px #000000;
      padding: 2px;
      span {
        margin: 0;
        color: black;
      }
    }
  }

  .box-body {
    display: flex;
    flex-direction: column;
    gap: 30px;
    padding: 19px 37px 18px 36px;

    .dropdown {
      position: relative;
      width: 100%;
      .hide {
        display: none;
      }
      .dropdown-button {
        height: 41px;
        padding: 10.5px 10px 10.5px 15px;
        line-height: 20px;
        color: black;
        @include font-weight(bold);
        font-size: 18px;
        border: 1px solid #000000;
        box-shadow: 2px 2px 0px #000000;
        border-radius: 0px;
        background-color: $kuningEternal;
        width: 100%;
        text-align: left;
        display: flex;
        justify-content: space-between;
        .text-end {
          display: flex;
          gap: 16px;
          color: rgba(0, 0, 0, 0.5);

          .material-symbols-outlined {
            color: black;
          }
        }
      }
      .dropdown-menu {
        width: 100%;
        border-radius: 0px;
        .dropdown-item {
          margin-bottom: 3px;
        }
      }
      .menu-down {
        position: absolute;
        width: 100%;
        z-index: 99999;
        margin-top: 3px;
        padding: 0;
        li {
          padding: 3px 11px 0px 11px;
          list-style: none;
          height: 41px;
          background-color: $pinkOCD;
          margin-bottom: 3px;
          border: 1px solid #000000;
          box-shadow: 2px 2px 0px #000000;
        }
        .menu-item {
          text-decoration: none;
          color: black;
          margin-left: 14px;
          @include font-weight(bold);
        }
      }
    }

    .add-button {
      display: flex;
      flex-direction: row;
      border: 1px solid #000000;
      padding: 7px 16px 7px 15px;
      box-shadow: 2px 2px 0px #000000;
      height: 51px;
      justify-content: space-between;

      p {
        line-height: 23px;
        margin: 5px 0px 5px 0px;
        @include font-weight(bold);
      }

      .button-payment {
        display: flex;
        justify-content: center;
        width: 35px;
        height: 35px;
        margin: 0;
        padding: 0;
        border: 1px solid #000000;
        box-shadow: 2px 2px 0px #000000;
        border-radius: 2px;
        background-color: $kuningEternal;
        span {
          margin-top: 2px;
          font-size: 30px;
        }
      }
    }
  }
}
</style>
