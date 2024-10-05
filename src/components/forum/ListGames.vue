<template>
  <div class="box-modal">
    <p class="title">All Games</p>
    <div class="list-game">
      <div v-for="game in games" :key="game.gameId" class="list-wrapper">
        <img :src="game.bgId" alt="ml_game" />
        <div class="overlay">
          <p class="overlay-text">
            {{ game.gameId }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      games: [
        {
          gameId: "Mobile Legends",
          bgId: require("@/assets/img/ml_game_list.svg"),
        },
        {
          gameId: "FreeFire MAX",
          bgId: require("@/assets/img/ff_game_list.svg"),
        },
        {
          gameId: "PUBG",
          bgId: require("@/assets/img/pubg_game_list.svg"),
        },
        {
          gameId: "CODM",
          bgId: require("@/assets/img/codm_game_list.svg"),
        },
        {
          gameId: "Valorant",
          bgId: require("@/assets/img/valo_game_list.svg"),
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/variables.scss";

.box-modal {
  position: absolute;
  margin-top: 2px;
  border: 1px solid black;
  z-index: 9393939393;
  height: 314px;
  width: 100vw;
  background-color: $primary20;
  padding: 33px;

  .title {
    @include font-weight(bold);
    margin-bottom: 25px;
    line-height: 19px;
  }

  .list-game {
    display: flex;
    flex-direction: row;
    gap: 17px;

    .list-wrapper {
      position: relative;
      img {
        width: 116px;
        height: 99px;
      }

      &:hover {
        .overlay {
          visibility: visible;
          transform: translateY(0px);
          transition: all 0.1s;
        }
      }
    }
  }
}

.overlay {
  position: absolute;
  color: #fff;
  top: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  visibility: hidden;
  background-color: rgba($color: #fff, $alpha: 0.1);
  backdrop-filter: blur(3px);
  transform: translateY(99px);

  .overlay-text {
    text-align: center;
    line-height: 12px;
    margin: 0;
    font-size: 14px;
    @include font-weight(bold);
    width: 90px;
  }
}
</style>
