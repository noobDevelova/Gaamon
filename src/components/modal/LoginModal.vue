<template>
  <div v-if="showLoginModal" class="modal-wrapper">
    <ModalFrame @close="closeModal">
      <h1 class="header-title text-center">Log In</h1>
      <template v-slot:input>
        <form class="input-form">
          <label for="email">Email or Phone</label>
          <input
            type="text"
            class="input-email"
            placeholder="Enter your email or phone number"
            required
          />
          <label for="password">Password</label>
          <div class="passField">
            <input
              v-if="peekPassword"
              type="text"
              class="inputPass"
              :class="{ invalid: isPasswordInvalid }"
              placeholder="Minimum 8 Characters"
              v-model="password"
            />
            <input
              v-else
              type="password"
              class="inputPass"
              :class="{ invalid: isPasswordInvalid }"
              placeholder="Minimum 8 Characters"
              v-model="password"
            />
            <a class="forgot-pass">Forgot Password?</a>
            <span class="eye material-symbols-outlined" @click="togglePeek()">
              {{ peekPassword ? "visibility_off" : "visibility" }}
            </span>
          </div>
          <button type="submit" class="submit-btn">Log In</button>
        </form>
      </template>
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
        <p class="sign-up-link">
          Don't Have an account?
          <a href="">Sign Up</a>
        </p>
      </div>
    </ModalFrame>
  </div>
</template>

<script>
import ModalFrame from "./ModalFrame.vue";
export default {
  props: {
    showLoginModal: Boolean,
  },
  data() {
    return {
      peekPassword: false,
    };
  },

  components: {
    ModalFrame,
  },
  methods: {
    closeModal() {
      this.$emit("modalClose");
    },
    togglePeek() {
      this.peekPassword = !this.peekPassword;
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
  .input-form {
    position: relative;
    margin-top: 70px;
    margin-inline: 25px;

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
      .forgot-pass {
        font-size: 0.9rem;
        top: 60px;
        text-decoration: none;
        @include font-weight(semibold);
        color: black;
      }
    }
  }
  .forgot-pass {
    font-size: 0.9rem;
    top: 60px;
    text-decoration: none;
    @include font-weight(semibold);
    color: black;
  }
  .submit-btn {
    @extend .btn-master;
    margin-top: 1rem;
    font-size: 1rem;
    width: 100%;
    height: 40px;
  }
  .footer-section {
    position: absolute;
    margin-inline: auto;
    left: 0;
    right: 0;
    bottom: 5.5rem;
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
    .sign-up-link {
      @include font-weight(bold);
      color: black;
      margin-top: 2rem;

      a {
        text-decoration: none;
        color: black;
      }
    }
  }
}
</style>
