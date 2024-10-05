<template>
  <div class="purchase-history-box">
    <div class="box-header">
      <h3>Purchase History</h3>

      <router-link to="/" class="close-button">
        <span class="material-symbols-outlined"> close </span>
      </router-link>
    </div>
    <div class="box-body">
      <div class="payment-list-wrapper">
        <div class="list-wrap">
          <div class="history-card">
            <button class="button-payment" type="button">
              <span class="material-symbols-outlined"> add_circle </span>
            </button>
            <div class="history-date">
              <p class="history-text">Top Up</p>
              <p class="date">12 January 2021</p>
            </div>
            <p class="amount">Rp20.000</p>
          </div>
          <div class="history-card">
            <button class="button-payment" type="button">
              <span class="material-symbols-outlined"> add_circle </span>
            </button>
            <div class="history-date">
              <p class="history-text">Top Up</p>
              <p class="date">12 January 2021</p>
            </div>
            <p class="amount">Rp20.000</p>
          </div>
          <div class="history-card">
            <button class="button-payment" type="button">
              <span class="material-symbols-outlined"> add_circle </span>
            </button>
            <div class="history-date">
              <p class="history-text">Top Up</p>
              <p class="date">12 January 2021</p>
            </div>
            <p class="amount">Rp20.000</p>
          </div>
          <div class="history-card">
            <button class="button-payment" type="button">
              <span class="material-symbols-outlined"> add_circle </span>
            </button>
            <div class="history-date">
              <p class="history-text">Top Up</p>
              <p class="date">12 January 2021</p>
            </div>
            <p class="amount">Rp20.000</p>
          </div>
          <div class="history-card">
            <button class="button-payment" type="button">
              <span class="material-symbols-outlined"> add_circle </span>
            </button>
            <div class="history-date">
              <p class="history-text">Top Up</p>
              <p class="date">12 January 2021</p>
            </div>
            <p class="amount">Rp20.000</p>
          </div>
          <div class="history-card">
            <button class="button-payment" type="button">
              <span class="material-symbols-outlined"> add_circle </span>
            </button>
            <div class="history-date">
              <p class="history-text">Top Up</p>
              <p class="date">12 January 2021</p>
            </div>
            <p class="amount">Rp20.000</p>
          </div>
          <div class="history-card">
            <button class="button-payment" type="button">
              <span class="material-symbols-outlined"> add_circle </span>
            </button>
            <div class="history-date">
              <p class="history-text">Top Up</p>
              <p class="date">12 January 2021</p>
            </div>
            <p class="amount">Rp20.000</p>
          </div>
          <div class="history-card">
            <button class="button-payment" type="button">
              <span class="material-symbols-outlined"> add_circle </span>
            </button>
            <div class="history-date">
              <p class="history-text">Top Up</p>
              <p class="date">12 January 2021</p>
            </div>
            <p class="amount">Rp20.000</p>
          </div>
          <div class="history-card">
            <button class="button-payment" type="button">
              <span class="material-symbols-outlined"> add_circle </span>
            </button>
            <div class="history-date">
              <p class="history-text">Top Up</p>
              <p class="date">12 January 2021</p>
            </div>
            <p class="amount">Rp20.000</p>
          </div>
          <div class="history-card">
            <button class="button-payment" type="button">
              <span class="material-symbols-outlined"> add_circle </span>
            </button>
            <div class="history-date">
              <p class="history-text">Top Up</p>
              <p class="date">12 January 2021</p>
            </div>
            <p class="amount">Rp20.000</p>
          </div>
          <div class="history-card">
            <button class="button-payment" type="button">
              <span class="material-symbols-outlined"> add_circle </span>
            </button>
            <div class="history-date">
              <p class="history-text">Top Up</p>
              <p class="date">12 January 2021</p>
            </div>
            <p class="amount">Rp20.000</p>
          </div>
          <div class="history-card">
            <button class="button-payment" type="button">
              <span class="material-symbols-outlined"> add_circle </span>
            </button>
            <div class="history-date">
              <p class="history-text">Top Up</p>
              <p class="date">12 January 2021</p>
            </div>
            <p class="amount">Rp20.000</p>
          </div>
          <div class="history-card">
            <button class="button-payment" type="button">
              <span class="material-symbols-outlined"> add_circle </span>
            </button>
            <div class="history-date">
              <p class="history-text">Top Up</p>
              <p class="date">12 January 2021</p>
            </div>
            <p class="amount">Rp20.000</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.purchase-history-box {
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
    padding: 19px 37px 18px 36px;

    .payment-list-wrapper {
      height: 570px;
      overflow: auto;
      .list-wrap {
        display: flex;
        flex-direction: column;
        gap: 20px;
        width: 100%;
        .history-card {
          display: flex;
          flex-direction: row;
          height: 47px;
          border: 2px solid #000000;
          box-shadow: 2px 2px 0px #000000;
          padding: 7.5px 28px 7.5px 10px;
          gap: 15px;

          .button-payment {
            display: flex;
            justify-content: center;
            width: 28px;
            height: 28px;
            padding: 0;
            border: 1px solid #000000;
            box-shadow: 2px 2px 0px #000000;
            border-radius: 2px;
            background-color: $pinkOCD;
            span {
              margin-top: 1px;
              margin-left: 1px;
            }
          }
          .history-date {
            line-height: 0px;
            margin-top: 7px;
            .history-text {
              @include font-weight(bold);
              font-size: 14px;
            }
            .date {
              font-size: 12px;
              @include font-weight(semibold);
            }
          }
          .amount {
            margin-left: auto;
          }
        }
      }
    }
  }
}
</style>
