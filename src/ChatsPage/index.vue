<template>
    <div style="height: 100vh">
      <PrettyChatWindow
        :projectId="projectId"
        :username="username"
        :secret="secret"
        :fontFamily='Roboto', sans-serif;
        :fontSize="14"
      />
    </div>
  </template>
  
  <style>
  .ce-new-chat-button {
    width: 32px;
    position: relative;
    bottom: 22px;
  }
  </style>
  
  <script>
  import { PrettyChatWindow } from "react-chat-engine-pretty";
  import { applyReactInVue } from "veaury";
  
  export default {
    data() {
      return {
        projectId: import.meta.env.VITE_CHAT_ENGINE_PROJECT_ID,
      };
    },
    components: {
      PrettyChatWindow: applyReactInVue(PrettyChatWindow),
    },
    props: {
      username: {
        type: String,
        required: true,
      },
      secret: {
        type: String,
        required: true,
      },
    },
  };
  </script>
  