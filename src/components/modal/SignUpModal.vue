<template>
  <div v-if="showRegisModal" class="modal-wrapper">
    <ModalFrame @close="closeModal">
      <h1 class="header-title text-center">Sign Up</h1>
      <template v-slot:button-method>
        <div class="btn-wrapper">
          <button
            type="button"
            class="btn-sign-up-method"
            data-bs-target="#signUpEmailModal"
            data-bs-toggle="modal"
            @click="closeModal"
          >
            <img src="../../assets/img/email_icon.svg" alt="" /> With Email
          </button>
          <button type="button" class="btn-sign-up-method">
            <img src="../../assets/img/phone_icon.svg" alt="" />With Phone
            Number
          </button>
          <button type="button" class="btn-sign-up-method">
            <img src="../../assets/img/google_icon.svg" alt="" /> With Google
          </button>
          <button type="button" class="btn-sign-up-method">
            <img src="../../assets/img/apple_icon.svg" alt="" /> With Apple
          </button>
        </div>
      </template>
    </ModalFrame>
  </div>
  <!-- Sign Up With Email Start -->
  <div
    class="modal fade"
    id="signUpEmailModal"
    tabindex="-1"
    aria-labelledby="signUpEmailModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-centered">
      <div class="modal-content">
        <div class="modal-header">
          <h1 class="header-title text-center">Sign Up</h1>
          <button
            type="button"
            class="btn-close-modal float-end"
            data-bs-dismiss="modal"
            aria-label="Close"
          >
            <img src="../../assets/img/close.svg" alt="" />
          </button>
        </div>
        <div class="modal-body">
          <form class="input-form" @submit.prevent="register">
            <label for="email">Email</label>
            <input
              type="text"
              class="input-email"
              :class="{ invalid: isEmailInvalid }"
              placeholder="example@gmail.com"
              required
              v-model="email"
            />
            <p v-if="isEmailInvalid" class="invalid-email">{{ message }}</p>
            <label for="password">New Password</label>
            <div class="passField">
              <input
                v-if="showPassword"
                type="text"
                class="inputPass"
                :class="{ invalid: isPasswordInvalid }"
                id="password"
                placeholder="Minimum 8 Characters"
                v-model="passwordFirst"
              />
              <input
                v-else
                type="password"
                class="inputPass"
                :class="{ invalid: isPasswordInvalid }"
                id="password"
                placeholder="Minimum 8 Characters"
                v-model="passwordFirst"
              />
              <p v-if="isPasswordInvalid" class="invalid-password">
                {{ pw_message }}
              </p>
              <span class="eye material-symbols-outlined" @click="toggleShow">
                {{ showPassword ? "visibility_off" : "visibility" }}
              </span>
            </div>

            <label for="confirm_password">Confirm Password</label>
            <div class="passFieldConfirm">
              <input
                v-if="showPasswordConfirm"
                type="text"
                class="inputPassConfirm"
                :class="{ invalid: isPasswordNotMatch }"
                id="confirm_password"
                placeholder="Minimum 8 Characters"
                v-model="password"
              />
              <input
                v-else
                type="password"
                class="inputPassConfirm"
                :class="{ invalid: isPasswordNotMatch }"
                id="confirm_password"
                placeholder="Minimum 8 Characters"
                v-model="password"
              />
              <p v-if="isPasswordNotMatch" class="invalid-password">
                {{ pw_message_confirm }}
              </p>
              <span
                class="eye material-symbols-outlined"
                @click="toggleShowConfirm()"
              >
                {{
                  showPasswordConfirm ? "visibility_off" : "visibility"
                }}</span
              >
            </div>
            <input type="submit" @click="submit" class="submit-btn" />
            <!-- Create Account -->
            <!-- data-bs-target="#otpVerificationlModal" data-bs-toggle="modal" -->
          </form>
          <!-- data-bs-toggle="modal" data-bs-target="#verificationAccountModal" -->
          <div class="footer-section">
            <p>Or Continue With</p>
            <div class="btn-wrapper">
              <a href="" class="btn-sign-method"
                ><img src="../../assets/img/apple_icon.svg" alt=""
              /></a>
              <a href="" class="btn-sign-method"
                ><img src="../../assets/img/google_icon.svg" alt=""
              /></a>
              <a href="" class="btn-sign-method"
                ><img src="../../assets/img/phone_icon.svg" alt=""
              /></a>
            </div>
            <p class="login-method">
              Already have an account? <a href="">Log In</a>
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- Sign Up With Email Modal End -->
</template>

<script>
import ModalFrame from "./ModalFrame.vue";

export default {
  props: {
    showRegisModal: Boolean,
  },
  data() {
    return {
      email: "",
      message: "",
      reg: /^(([^<>()\]\\.,;:\s@"]+(\.[^<>()\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,24}))$/,
      showPassword: false,
      showPasswordConfirm: false,
      passwordFirst: "",
      password: "",
      pw_message: "",
      pw_message_confirm: "",
      isEmailInvalid: false,
      isPasswordInvalid: false,
      isPasswordConfirmInvalid: false,
      isPasswordNotMatch: false,
    };
  },
  components: { ModalFrame },
  emits: ["modalClose"],
  methods: {
    closeModal() {
      this.$emit("modalClose");
    },
    toggleShow() {
      this.showPassword = !this.showPassword;
    },
    toggleShowConfirm() {
      this.showPasswordConfirm = !this.showPasswordConfirm;
    },
    submit() {
      if (this.email == null || this.email == "") {
        this.isEmailInvalid = !this.isEmailInvalid;
        this.message = "Your email invalid";
      } else if (!this.reg.test(this.email)) {
        this.isEmailInvalid = !this.isEmailInvalid;
        this.message = "Your email invalid";
      }

      if (this.passwordFirst.length < 8) {
        this.isPasswordInvalid = !this.isPasswordInvalid;
        this.pw_message = "Your password insufficient";
        return false;
      }

      if (this.password != this.passwordFirst || this.passwordFirst == "") {
        this.isPasswordNotMatch = !this.isPasswordNotMatch;
        this.pw_message_confirm = "Your password doesn't match";
        return false;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";

.modal-wrapper {
  .header-title {
    margin-inline: auto;
    margin-top: 25px;
    @include font-weight(black);
    font-size: 1.5rem;
    z-index: 3;
  }
  .btn-wrapper {
    display: flex;
    flex-direction: column;
    gap: 20px;
    margin-top: 5rem;

    .btn-sign-up-method {
      @extend .btn-master;
      height: 45px;
      border: 2px solid black;
      font-size: 1rem;
      margin-inline: 25px;
      img {
        margin-right: 5px;
      }
    }
  }
}

.modal {
  .modal-dialog {
    max-width: 550px;
    .modal-content {
      height: 700px;
      border: 4px solid black;
      border-radius: 0px;
      box-shadow: 4px 4px 0px #000000;
      background: $primary20;
      .modal-header {
        position: relative;
        border-bottom: none;
        .btn-close-modal {
          width: 30px;
          height: 30px;
          position: relative;
          background: $kuningSummer;
          border-radius: 0px;
          border: 2px solid black;
          box-shadow: 2px 2px 0px #000000;
          margin-left: auto;
          img {
            position: absolute;
            top: 8px;
            left: 8px;
            width: 10px;
          }
        }
        .header-title {
          position: absolute;
          top: 50px;
          left: 0;
          right: 0;
          text-align: center;
          margin-left: auto;
          margin-right: auto;
          @include font-weight(black);
          font-size: 1.5rem;
          z-index: 3;
        }
      }
      .modal-body {
        .btn-wrapper-method {
          display: flex;
          flex-direction: column;
          gap: 20px;
          margin-top: 5rem;

          .btn-sign-up-method {
            @extend .btn-master;
            height: 45px;
            border: 2px solid black;
            font-size: 1rem;
            margin-inline: 25px;
            img {
              margin-right: 5px;
            }
          }
        }
        .input-form {
          position: relative;
          margin-top: 40px;
          margin-left: 25px;
          margin-right: 25px;

          label {
            display: block;
            @include font-weight(bold);
            margin-bottom: 0.2rem;
            margin-top: 0.9rem;
            font-size: 1.1rem;
          }
          input:placeholder-shown {
            width: 100%;
            height: 40px;
            padding-left: 10px;
            border: 1px solid black;
            box-shadow: none;
          }
          input[type="text"] {
            font-family: $archivo;
            @include font-weight(medium);
          }
          input:focus {
            outline: none;
            border: 2px solid black;
            box-shadow: 2px 2px 0px #000000;
          }
          input:not(:placeholder-shown) {
            width: 100%;
            height: 40px;
            padding-left: 10px;
            outline: none;
            border: 2px solid black;
            box-shadow: 2px 2px 0px #000000;
          }
          .passField {
            position: relative;
            .inputPass {
              width: 100%;
              height: 40px;
              padding-left: 10px;
            }

            .eye {
              cursor: pointer;
              position: absolute;
              right: 8px;
              top: 8px;
            }
          }
          .passFieldConfirm {
            position: relative;

            .inputPassConfirm {
              width: 100%;
              height: 40px;
              padding-left: 10px;
            }
            .eye {
              cursor: pointer;
              position: absolute;
              right: 8px;
              top: 8px;
            }
          }
          // Input Wrong or inufficient password

          input.invalid:not(:placeholder-shown) {
            color: red;
            border: 2px solid red;
            box-shadow: 2px 2px 0px red;
          }
          input.invalid:placeholder-shown {
            color: red;
            border: 2px solid red;
            box-shadow: 2px 2px 0px red;
          }
          .invalid-email {
            position: absolute;
            @include font-weight(medium);
            font-size: 0.7rem;
            color: red;
            margin-top: 0.2rem;
            right: 0;
            text-align: right;
          }

          .invalid-password {
            position: absolute;
            @include font-weight(medium);
            font-size: 0.7rem;
            color: red;
            margin-top: 0.2rem;
            right: 0;
            text-align: right;
          }

          // End

          .submit-btn {
            @extend .btn-master;
            font-size: 1rem;
            width: 100%;
            height: 40px;
            margin-top: 30px;
          }
        }
        .footer-section {
          position: absolute;
          margin-inline: auto;
          left: 0;
          right: 0;
          bottom: 3rem;
          text-align: center;
          p {
            @include font-weight(semibold);
            font-size: 1rem;
            color: $pinkOCD;
          }
          .btn-wrapper {
            position: relative;
            z-index: 10;
            display: flex;
            gap: 15px;
            justify-content: center;

            .btn-sign-method::before {
              content: "";
              width: 44px;
              height: 44px;
              border: 1px solid black;
              border-radius: 2px;
              background: transparent;
              position: absolute;
              top: 1px;
              left: 2px;
              z-index: -1;
            }
            .btn-sign-method {
              position: relative;
              width: 44px;
              height: 44px;
              border-radius: 2px;
              border: 1px solid black;
              background-color: $primary20;
              padding-top: 8px;
            }
          }

          .login-method {
            margin-top: 40px;
            color: black;
            a {
              text-decoration: none;
              color: $pinkOCD;
            }
          }
        }
      }
    }
  }
}
</style>
