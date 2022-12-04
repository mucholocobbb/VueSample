<template>
  <div class="container">
    <div class="img_block"></div>
    <div class="btn_block">
      <button id="imgDownload" class="refresh_btn" @click="getAction">
        <img
          class="refresh_btn_img"
          src="@/assets/repeat.svg"
          alt="repeatIcon"
        />
        <span class="refresh_btn_text">Обновить картинку</span>
      </button>
      <button id="listDownload" class="refresh_btn" @click="getAction">
        <img
          class="refresh_btn_img"
          src="@/assets/share.svg"
          alt="repeatIcon"
        />
        <span class="refresh_btn_text">Загрузить список</span>
      </button>
    </div>
    <div class="input_block">
      <span class="input_block_span">Загрузить файл</span>
      <div class="input_wrapper">
        <input
          class="input_wrapper_file"
          type="file"
          name="txtFile"
          id="fileDownload"
          accept=".txt"
        />
        <label class="input_wrapper_btn" for="fileDownload" @click="getAction">
          <img
            class="refresh_btn_img input_wrapper_img"
            src="@/assets/share.svg"
            alt="repeatIcon"
          />
          {{ wrapperBtnText }}
          <div class="input_wrapper_win">{{ wrapperWinText }}</div>
        </label>
      </div>
      <button class="input_btn" @click="getAction">Отобразить файл</button>
    </div>
  </div>
</template>

<script>
import sound from "@/assets/click.mp3";
export default {
  name: "LPMain",
  props: {
    msg: {
      type: String,
      default: "App - 1",
      click: {},
    },
  },
  data() {
    return {
      wrapperWinText: "Файл не выбран",
      wrapperBtnText: "Выберите файл (.txt)",
    };
  },
  methods: {
    getAction(event) {
      console.log(event);
      this.clickSound();
    },
    clickSound() {
      let click = new Audio(sound);
      click.volume = 0.05;
      click.play();
    },
  },
  mounted() {},
};
//TODO Не забыть перед публикацией сменить список без персональных данных.
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 80vw;
  min-height: calc(80vh - 256px);
  background-color: rgb(255, 255, 255);
  border: 1px solid rgb(192, 192, 192);
  margin-top: 36px;
  margin-bottom: 16px;
}
.refresh_btn {
  display: flex;
  justify-content: center;
  align-items: center;
  outline: none;
  width: 256px;
  height: 36px;
  &_img {
    width: 20px;
    margin-right: 4px;
  }
}
.img_block {
  margin-top: 16px;
  margin-bottom: 24px;
  border: 1px solid rgb(192, 192, 192);
  width: 640px;
  height: 480px;
}
.btn_block {
  width: 640px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 24px;
}
.input_block {
  display: flex;
  justify-content: space-around;
  align-items: center;
  position: relative;
  width: 640px;
  min-height: 96px;
  border: 1px solid rgb(192, 192, 192);
  margin-bottom: 16px;
  &_span {
    color: rgb(192, 192, 192);
    position: absolute;
    background-color: white;
    font-size: 14px;
    left: 16px;
    top: -10px;
    padding-left: 6px;
    padding-right: 6px;
  }
}
.input_wrapper {
  position: relative;
  margin: 15px 0;
  text-align: center;
  &_file {
    opacity: 0;
    visibility: hidden;
    position: absolute;
  }
  &_btn {
    width: 320px;
    height: 36px;
    background-color: rgb(239 239 239);
    display: flex;
    align-items: center;
    justify-content: flex-start;
    padding-left: 8px;
    padding-right: 8px;
    cursor: pointer;
    margin: 0 auto;
    border: 1px solid rgb(192, 192, 192);
    &:hover {
      background-color: rgb(229 223 223);
    }
    &:active {
      background-color: rgb(240 240 240);
    }
  }
  &_img {
    padding-right: 4 px;
  }
  &_win {
    width: 140px;
    height: 36px;
    border: 1px solid rgb(192, 192, 192);
    background-color: white;
    position: absolute;
    right: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 12px;
    color: rgb(192, 192, 192);
  }
}
.input_btn {
  width: 180px;
  height: 36px;
  outline: none;
  border: 1px solid rgb(213, 212, 212);
  &:hover {
    background-color: rgb(229 223 223);
  }
  &:active {
    background-color: rgb(240 240 240);
  }
}
</style>
