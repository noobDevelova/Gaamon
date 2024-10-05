<template>
  <NavbarNav />
  <div class="page-body">
    <div class="container">
      <div class="profile-wrapper">
        <SidebarProfile class="sidebar-component">
          <template v-slot:my-profile>
            <button
              class="button-link"
              :class="{ buttonLinkActive: myProfileView }"
              type="button"
              @click="gotoProfileView"
            >
              My Profile
            </button>
          </template>
          <template v-slot:my-group>
            <button
              class="button-link"
              :class="{ buttonLinkActive: myGroupView }"
              type="button"
              @click="gotoGroupView"
            >
              My Group
            </button>
          </template>
          <template v-slot:gaamon-pay>
            <button class="button-link" type="button">Gaamon Pay</button>
          </template>
          <template v-slot:purchase-history>
            <button
              class="button-link"
              :class="{ buttonLinkActive: purchaseView }"
              type="button"
              @click="gotoPurchaseView"
            >
              Purchase History
            </button>
          </template>
          <template v-slot:payment-method>
            <button
              :class="{ buttonLinkActive: paymentView }"
              class="button-link"
              type="button"
              @click="gotoPaymentView"
            >
              Payment Method
            </button>
          </template>
          <template v-slot:saved>
            <button
              class="button-link"
              :class="{ buttonLinkActive: savedView }"
              type="button"
              @click="gotoSavedView"
            >
              Saved
            </button>
          </template>
          <template v-slot:setting>
            <button
              class="button-link"
              :class="{ buttonLinkActive: settingView }"
              type="button"
              @click="gotoSettingView"
            >
              Setting
            </button>
          </template>
        </SidebarProfile>
        <div class="view-wrapper">
          <ProfileHeader></ProfileHeader>
          <div v-if="myProfileView" class="profile-box">
            <div class="box-header">
              <button
                type="button"
                class="box-set-button"
                :class="{
                  active: myInformation,
                }"
                @click="gotoInformation"
              >
                My Information
              </button>
              <button
                type="button"
                class="box-set-button"
                :class="{ active: editProfile }"
                @click="gotoEditProfile"
              >
                Edit Profile
              </button>
              <button
                type="button"
                class="box-set-button"
                :class="{ active: changePassword }"
                @click="gotoChangePassword"
              >
                Change Password
              </button>
              <button
                type="button"
                class="box-set-button"
                :class="{ active: profileAddress }"
                @click="gotoAddress"
              >
                My Address
              </button>
              <button type="button" class="close-button">
                <router-link to="/">
                  <span class="material-symbols-outlined"> close </span>
                </router-link>
              </button>
            </div>
            <div class="box-body">
              <ProfileDisplay
                @toFollowers="gotoFollowers"
                @toFollowing="gotoFollowing"
              >
              </ProfileDisplay>
              <ProfileInformation v-if="myInformation"></ProfileInformation>
              <ProfileEdit v-if="editProfile"></ProfileEdit>
              <ProfileChangePassword
                v-if="changePassword"
              ></ProfileChangePassword>
              <ProfileAddress v-if="profileAddress"></ProfileAddress>
              <FollowersView v-if="followersList"></FollowersView>
              <FollowingView v-if="followingList"></FollowingView>
            </div>
          </div>
          <MyGroup v-if="myGroupView"></MyGroup>
          <PurchaseHistory v-if="purchaseView"></PurchaseHistory>
          <PaymentMethod v-if="paymentView"></PaymentMethod>
          <SavedView v-if="savedView"></SavedView>
          <SettingView v-if="settingView"></SettingView>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NavbarNav from "@/components/navbar/NavbarNav.vue";
import ProfileDisplay from "../../components/profile/ProfileDisplay.vue";
import ProfileInformation from "../../components/profile/ProfileInformation.vue";
import ProfileEdit from "../../components/profile/ProfileEdit.vue";
import ProfileChangePassword from "@/components/profile/ProfileChangePassword.vue";
import ProfileAddress from "@/components/profile/ProfileAddress.vue";
import FollowersView from "../../components/profile/FollowersView.vue";
import FollowingView from "@/components/profile/FollowingView.vue";
import MyGroup from "@/components/profile/MyGroup.vue";
import ProfileHeader from "@/components/profile/ProfileHeader.vue";
import SidebarProfile from "@/components/profile/SidebarProfile.vue";
import PurchaseHistory from "@/components/profile/PurchaseHistory.vue";
import PaymentMethod from "../../components/profile/PaymentMethod.vue";
import SavedView from "@/components/profile/SavedView.vue";
import SettingView from "@/components/profile/SettingView.vue";
export default {
  data() {
    return {
      myInformation: true,
      editProfile: false,
      changePassword: false,
      profileAddress: false,
      followersList: false,
      followingList: false,
      myProfileView: true,
      myGroupView: false,
      purchaseView: false,
      paymentView: false,
      savedView: false,
      settingView: false,
    };
  },
  components: {
    ProfileDisplay,
    ProfileInformation,
    ProfileEdit,
    ProfileChangePassword,
    ProfileAddress,
    FollowersView,
    FollowingView,
    MyGroup,
    ProfileHeader,
    SidebarProfile,
    PurchaseHistory,
    PaymentMethod,
    SavedView,
    SettingView,
    NavbarNav,
  },
  methods: {
    gotoInformation() {
      this.myInformation = true;
      this.editProfile = false;
      this.changePassword = false;
      this.profileAddress = false;
      this.followingList = false;
      this.followersList = false;
    },
    gotoEditProfile() {
      this.myInformation = false;
      this.editProfile = true;
      this.changePassword = false;
      this.profileAddress = false;
      this.followingList = false;
      this.followersList = false;
    },
    gotoChangePassword() {
      this.myInformation = false;
      this.editProfile = false;
      this.changePassword = true;
      this.profileAddress = false;
      this.followingList = false;
      this.followersList = false;
    },
    gotoAddress() {
      this.myInformation = false;
      this.editProfile = false;
      this.changePassword = false;
      this.profileAddress = true;
      this.followingList = false;
      this.followersList = false;
    },
    gotoFollowing() {
      this.myInformation = false;
      this.editProfile = false;
      this.changePassword = false;
      this.profileAddress = false;
      this.followingList = true;
      this.followersList = false;
    },
    gotoFollowers() {
      this.myInformation = false;
      this.editProfile = false;
      this.changePassword = false;
      this.profileAddress = false;
      this.followingList = false;
      this.followersList = true;
    },
    gotoProfileView() {
      this.myProfileView = true;
      this.myGroupView = false;
      this.purchaseView = false;
      this.paymentView = false;
      this.savedView = false;
      this.settingView = false;
    },
    gotoGroupView() {
      this.myProfileView = false;
      this.myGroupView = true;
      this.purchaseView = false;
      this.paymentView = false;
      this.savedView = false;
      this.settingView = false;
    },
    gotoPurchaseView() {
      this.myProfileView = false;
      this.myGroupView = false;
      this.purchaseView = true;
      this.paymentView = false;
      this.savedView = false;
      this.settingView = false;
    },
    gotoPaymentView() {
      this.myProfileView = false;
      this.myGroupView = false;
      this.purchaseView = false;
      this.paymentView = true;
      this.savedView = false;
      this.settingView = false;
    },
    gotoSavedView() {
      this.myProfileView = false;
      this.myGroupView = false;
      this.purchaseView = false;
      this.paymentView = false;
      this.savedView = true;
      this.settingView = false;
    },
    gotoSettingView() {
      this.myProfileView = false;
      this.myGroupView = false;
      this.purchaseView = false;
      this.paymentView = false;
      this.savedView = false;
      this.settingView = true;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables";

.page-body {
  width: min(100vw);
  height: min(100vh);
  margin-top: 67px;
  background-color: $primary20;
  padding-top: 20px;
}
.profile-wrapper {
  display: flex;
  gap: 1.8rem;

  .sidebar-component {
    .button-link {
      width: 170px;
      height: 60px;
      text-align: left;
      @include font-weight(bold);
      background-color: $primary20;
      border: 1px solid transparent;
    }
    .buttonLinkActive {
      background-color: $kuningSummer;
      border: 1px solid #000000;
      box-shadow: 2px 2px 0px #000000;
    }
  }

  .view-wrapper {
    display: flex;
    flex-direction: column;
    width: 100%;
    gap: 25px;

    .profile-box {
      width: 100%;
      height: 700px;
      background-color: $kuningEternal;
      border: 1px solid #000000;
      box-shadow: 2px 2px 0px #000000;

      .box-header {
        display: flex;
        flex-direction: row;
        gap: 20px;
        padding: 20px;
        border-bottom: 2px solid black;

        .box-set-button {
          background-color: $kuningEternal;
          border: 1px solid #000000;
          padding-inline: 8px;
          padding-top: 10px;
          padding-bottom: 10px;
        }
        .active {
          border: 2px solid #000000;
          box-shadow: 2px 2px 0px #000000;
        }
        .close-button {
          margin-left: auto;
          width: 30px;
          height: 30px;
          padding: 0;
          border: 1px solid #000000;
          box-shadow: 2px 2px 0px #000000;
          background-color: $kuningEternal;
          span {
            margin-top: 2px;
          }
        }
      }

      .box-body {
        padding-top: 13.5px;
        padding-inline: 15px;
        padding-bottom: 13.5px;
        display: flex;
        flex-direction: row;
        padding-right: 71px;
        gap: 18px;
      }
    }
  }
}
</style>
