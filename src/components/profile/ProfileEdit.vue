<template>
  <div class="profile-content">
    <h3>Change your bio</h3>
    <div class="content-wrapper top-content">
      <div class="profile-set">
        <div class="tag"><p>Name</p></div>
        <div class="tag-value"><p>Randi Risdiansyah</p></div>
      </div>
      <div class="profile-set">
        <div class="tag"><p>Username</p></div>
        <div class="tag-value"><p>@bocilganggu12</p></div>
      </div>
      <div class="profile-set">
        <div class="tag"><p>Bio</p></div>
        <div class="tag-value">
          <p>Lebih Sering Ketemu error daripada ketemu kamu</p>
        </div>
      </div>
      <div class="profile-set">
        <div class="tag"><p>Born</p></div>
        <div class="tag-value"><p>32 - Feb - 1400</p></div>
      </div>
      <div class="profile-set">
        <div class="tag"><p>Gender</p></div>
        <div class="tag-value"><p>Male</p></div>
      </div>
    </div>
    <h3>Change Contact</h3>
    <div class="content-wrapper bottom-content">
      <div class="profile-set">
        <div class="tag"><p>Email</p></div>
        <div class="tag-value"><p>randyrisdiansyah@gmail.com</p></div>
      </div>
      <div class="profile-set">
        <div class="tag"><p>Phone</p></div>
        <div class="tag-value"><p>+62 878 3783 2789</p></div>
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
        width: 100px;
        background-color: $pinkOCD10;
      }
      .tag-value {
        padding-top: 7px;
        padding-left: 10px;
      }
    }
  }
  .top-content {
    margin-bottom: 20px;
  }
  .bottom-content {
    margin-top: 15px;
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
