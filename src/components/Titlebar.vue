<template>
  <div data-tauri-drag-region class="titlebar">
    <div
      data-tauri-drag-region
      style="justify-content: space-between"
      class="titlebar-icons"
    >
      <div class="titlebar-options">
        <img
          class="titlebar-settings"
          src="../assets/svg/settings.svg"
          id="settings-btn"
        />
        <img
          class="titlebar-account"
          src="../assets/svg/account.svg"
          id="account-btn"
        />

        <img class="titlebar-rpc" src="../assets/svg/discord.svg" id="rpcbtn" />
        <span id="rpc"></span>
      </div>
      <div style="margin-top: 0px" class="titlebar-icons">
        <div @click="min_window" class="titlebar-min mx-1"></div>
        <div @click="max_window" class="titlebar-max mx-1"></div>
        <div @click="close_window" class="titlebar-exit mx-1"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "titlebar-comp",
  methods: {
    min_window() {
      window.__TAURI__.window.appWindow.minimize();
    },
    max_window() {
      window.__TAURI__.window.appWindow.toggleMaximize();
    },
    close_window() {
      window.__TAURI__.window.appWindow.close();
    },
  },
};
</script>

<style>
.titlebar {
  position: relative;
  overflow: hidden;
  border-radius: 10px;
  background-color: #1c1d22;
  height: 35px;
  width: 100%;
  flex: auto;
}

.titlebar-icons {
  margin-right: 6px !important;
  margin-top: 9px;

  display: flex !important;
  justify-content: space-between;
}

.titlebar-options {
  margin-left: 14px;
  display: flex;
  justify-content: space-between;
}

.titlebar-exit {
  border-radius: 50px;
  transition: all 0.2s cubic-bezier(0.165, 0.84, 0.44, 1);
  height: 18px;
  width: 18px;
  background-color: rgb(70, 70, 70);
  display: block;
}

.titlebar-exit:hover {
  background: #ff0000;
  background-size: cover;
}

.titlebar-max {
  border-radius: 50px;
  transition: all 0.2s cubic-bezier(0.165, 0.84, 0.44, 1);
  height: 18px;
  width: 18px;
  background-color: rgb(70, 70, 70);
  display: block;
}

.titlebar-max:hover {
  background: #ffc400;
}

.titlebar-min {
  border-radius: 50px;
  transition: all 0.2s cubic-bezier(0.165, 0.84, 0.44, 1);
  height: 18px;
  width: 18px;
  background-color: rgb(70, 70, 70);
  display: block;
}

.titlebar-min:hover {
  background: #22ff00;
}

.titlebar-settings {
  display: block;
  height: 18px;
  width: 18px;
  align-items: flex-start;
}

.titlebar-settings:hover {
  cursor: pointer;
  animation-delay: 200ms;
  animation: settings-spin 1.5s linear;
  filter: invert(17%) sepia(86%) saturate(3285%) hue-rotate(239deg)
    brightness(85%) contrast(101%);
}

.titlebar-account {
  display: none;
  height: 18px;
  width: 18px;
  margin-left: 14px;
  align-items: flex-start;
  border-radius: 50px/50px;
}

.titlebar-account:hover {
  cursor: pointer;
  filter: invert(36%) sepia(89%) saturate(4522%) hue-rotate(225deg)
    brightness(99%) contrast(99%);
}

.titlebar-update {
  -webkit-app-region: no-drag;
  display: none;
  height: 18px;
  width: 18px;
  margin-top: 1px;
  margin-left: 13px;
  align-items: flex-start;
}

.titlebar-update:hover {
  cursor: pointer;
  filter: invert(65%) sepia(56%) saturate(4278%) hue-rotate(79deg)
    brightness(118%) contrast(130%);
}

.titlebar-loading {
  -webkit-app-region: no-drag;
  display: flex;
  opacity: 0;
  height: 24px;
  width: 24px;
  margin-top: -2px;
  margin-left: 8px;
  align-items: flex-start;
}

.titlebar-rpc {
  display: block;
  height: 19px;
  width: 19px;
  margin-left: 14px;
  align-items: flex-start;
  filter: invert(50%);
}

#rpc {
  display: flex;
  color: darkgray;
  font-family: Nunito-Bold;
  justify-content: center;
  align-items: center;
  font-size: 14px;
  margin-left: 10px;
  cursor: default;
}
</style>