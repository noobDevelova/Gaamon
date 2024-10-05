<template>
  <div class="frame-box">
    <div class="box-inner">
      <div class="inner-wrapper">
        <slot name="monpay-value">
          <div class="monpay">
            <div class="mon-header">
              <p class="card-text">MON-PAY</p>
            </div>
            <div class="mon-balance">
              <p class="card-text">Rp1.000.000</p>
            </div>
          </div>
        </slot>
        <div class="monpay-method">
          <div class="top-up">
            <button class="method-btn" type="button">
              <img
                src="../../assets/img/plus_circle_icon.svg"
                alt="plus_circle"
              />
              <!-- <span class="material-symbols-outlined"> add_circle </span> -->
            </button>
            <p>TOP UP</p>
          </div>
          <div class="pay">
            <button class="method-btn" type="button">
              <span class="material-symbols-outlined"> credit_card </span>
            </button>
            <p>PAY</p>
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

.frame-box {
  width: 380px;
  height: 160px;
  background-color: $EternalSummer30;
  border: 1px solid #000000;
  box-shadow: 2px 2px 0px #000000;
  padding-inline: 30px;
  padding-top: 39px;
  padding-bottom: 39px;

  .box-inner {
    width: 100%;
    height: 100%;
    padding-inline: 25px;
    padding-top: 10px;
    background-color: $primary20;
    border: 1px solid #000000;
    box-shadow: 2px 2px 0px #000000;
    border-radius: 2px;

    .inner-wrapper {
      display: flex;
      flex-direction: row;
      gap: 70px;

      .monpay {
        display: flex;
        flex-direction: column;
        gap: 5px;
        p {
          margin: 0;
          padding: 0;
        }
        .mon-header {
          background-color: $kuningSummer;
          border: 1px solid #000000;
          box-shadow: 2px 2px 0px #000000;
          border-radius: 2px;
          text-align: center;
          width: fit-content;
          margin-inline: auto;
          padding: 3px;

          .card-text {
            font-family: $poppins;
            @include font-weight(bold);
            font-size: 14px;
          }
        }
        .mon-balance {
          .card-text {
            font-family: $poppins;
            margin-inline: 6px;
            font-size: 14px;
            @include font-weight(medium);
            color: black;
          }
        }
      }
      .monpay-method {
        display: flex;
        flex-direction: row;
        gap: 25px;

        p {
          text-align: center;
          @include font-weight(bold);
          font-size: 12px;
          font-family: $poppins;
        }
        .top-up {
          display: flex;
          flex-direction: column;
          gap: 12px;
          justify-content: center;
          align-items: center;
        }
        .pay {
          display: flex;
          flex-direction: column;
          gap: 12px;
          justify-content: center;
          align-items: center;
        }
        .method-btn {
          position: relative;
          background-color: $kuningEternal;
          padding: 0;
          width: 22px;
          height: 22px;
          border: 1px solid #000000;
          box-shadow: 2px 2px 0px #000000;
          border-radius: 2px;

          img {
            margin-bottom: 4.8px;
          }

          span {
            font-size: 20px;
          }
        }
      }
    }
  }
}
</style>
