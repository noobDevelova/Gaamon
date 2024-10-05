<template>
  <div class="profile-content">
    <h3>Change Password</h3>
    <div class="content-wrapper">
      <div class="profile-set">
        <div class="tag"><p>Current Password</p></div>
        <div class="tag-value"><p>************</p></div>
      </div>
      <div class="profile-set">
        <div class="tag"><p>New Password</p></div>
        <div class="tag-value"><p>**************</p></div>
      </div>
      <div class="profile-set">
        <div class="tag"><p>Confirm New Password</p></div>
        <div class="tag-value">
          <p>*******************</p>
        </div>
      </div>
    </div>
    <button type="button" class="save-button">Save Changes</button>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.profile-content {
  display: flex;
  flex-direction: column;
  width: 100%;

  h3 {
    font-size: 18px;
    @include font-weight(bold);
  }
  .content-wrapper {
    display: flex;
    flex-direction: column;
    margin-top: 15px;
    gap: 25px;

    .profile-set {
      display: flex;
      flex-direction: row;
      border: 2px solid #000000;
      box-shadow: 2px 2px 0px #000000;
      height: 41px;

      p {
        @include font-weight(bold);
      }

      .tag {
        padding-left: 10px;
        padding-top: 5px;
        border-right: 2px solid black;
        width: 198px;
        background-color: $pinkOCD10;
      }
      .tag-value {
        padding-top: 7px;
        padding-left: 10px;
      }
    }
  }
  .save-button {
    @include font-weight(bold);
    margin-left: auto;
    margin-top: 14px;
    width: 250px;
    border: 2px solid #000000;
    box-shadow: 2px 2px 0px #000000;
    border-radius: 2px;
    background-color: $kuningEternal;
    padding: 5px 0px 5px 0px;
  }
}
</style>
