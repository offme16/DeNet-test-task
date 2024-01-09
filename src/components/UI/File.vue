<template>
    <button @contextmenu.prevent="showContextMenu">
      <img src="../../assets/icons/file.svg" alt="File icon">
      <slot></slot>
      <div v-if="contextMenuVisible" class="context-menu">
        <div class="context-menu__item" @click="handleContextMenuAction('active')"><img src="../../assets/icons/active.svg"/>Upload</div>
        <div class="context-menu__item" @click="handleContextMenuAction('active')"><img src="../../assets/icons/newf.svg"/>New folder</div>
        <div class="context-menu__item" @click="handleContextMenuAction('active')"><img src="../../assets/icons/delete.svg"/>Deleted</div>
        <div class="context-menu__item" @click="handleContextMenuAction('active')"><img src="../../assets/icons/info.svg"/>Info</div>
      </div>
    </button>
  </template>
  
  <script>
  export default {
    props: {
      fileName: {
        type: String,
        required: true,
      },
    },
    data() {
      return {
        contextMenuVisible: false,
      };
    },
    methods: {
      showContextMenu() {
        this.contextMenuVisible = true;
        const hideContextMenu = () => {
          this.contextMenuVisible = false;
          document.removeEventListener('click', hideContextMenu);
        };
        document.addEventListener('click', hideContextMenu);
      },
      handleContextMenuAction(action) {
        if (action === 'active') {
          console.log('Edit action');
        }
        this.contextMenuVisible = false;
      },
    },
  };
  </script>
  
  <style scoped>
  button {
    position: relative;
    display: flex;
  flex-direction: column;
  border-radius: 10px;
  border: none;
  transition: all, 0.5s;
  cursor: pointer;
  background: transparent;
  justify-content: center;
  align-items: center;
  gap: 15px;
  width: 150px;
  height: 176px;
  }
  .context-menu__item{
      padding: 10px 45px 10px 12px;
      align-items: center;
      gap: 6px;
      display: flex;
      border-bottom: 1px solid  #EBEBEB;
      color: #676767;
  }
  .context-menu__item:hover{
    background-color: #EBEBEB;
  }
  .context-menu {
    position: absolute;
    background-color: #fff;
    border: none;
    z-index: 1000;
    top: 53px;
    right: -84px;
    border-radius: 6px;
    box-shadow: 7px 9px 27px 0px rgba(0, 0, 0, 0.12);
  }
  button:hover {
  background-color: #F6F6F6;
}
  </style>

