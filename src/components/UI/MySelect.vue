<template>
    <div class="custom-dropdown">
      <div class="dropdown-header" @click="toggleDropdown">
        <div class="dropdown-iconAs"><img v-if="showSearchIcon" src="../../assets/icons/logos.svg" alt="" class="navigate-btn__search" />
        <span>{{ selectedOption }}</span></div>
        <img src="../../assets/icons/stroke.svg" alt=""/>
      </div>
      <div v-if="isDropdownOpen" class="dropdown-options">
        <div v-for="option in options" :key="option.value" @click="selectOption(option)">
          <img v-if="option.icon" :src="option.icon" alt="" />
          {{ option.label }}
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      options: {
        type: Array,
        required: true,
      },
      defaultValue: {
        type: String,
        default: "",
      },
      showSearchIcon: {
        type: Boolean,
        default: true,
      },
    },
    data() {
      return {
        isDropdownOpen: false,
        selectedOption: this.defaultValue,
      };
    },
    methods: {
      toggleDropdown() {
        this.isDropdownOpen = !this.isDropdownOpen;
      },
      selectOption(option) {
        this.selectedOption = option.label;
        this.isDropdownOpen = false;
      },
    },
  };
  </script>
  
  <style scoped>
  .custom-dropdown {
    position: relative;
    min-width: 200px;
    max-height: 38px;
    color: #676767;
  }
  .dropdown-header:hover{
    background: rgba(246, 246, 246, 0.40);
  }
  .dropdown-iconAs{
    align-items: center;
    display: flex;
}
  .dropdown-header {
    cursor: pointer;
    padding: 5px;
    border: 1px solid #ccc;
    display: flex;
    align-items: center;
    padding: 8px 16px;
    flex-direction: column;
    gap: 10px;
    display: flex;
    flex-direction: row;
    align-items: center;
    border-radius: 10px;
    justify-content: space-between;
  }
  
  .dropdown-options {
    width: 136px;
    position: absolute;
    top: 130%;
    left: 0;
    overflow-y: auto;
    background-color: #fff;
    z-index: 1;
    border-radius: 10px;
    display: flex;
    padding: 19px 49px 19px 16px;
    flex-direction: column;
    align-items: flex-start;
    gap: 18px;
    box-shadow: 6px 12px 36px 0px rgba(35, 35, 35, 0.10);
    backdrop-filter: blur(10.5px);
  }
  .dropdown-options div {
    cursor: pointer;
    display: flex;
}
  .dropdown-options img {
    margin-right: 5px;
  }
  </style>