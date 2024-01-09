<script>
  import MyButton from "@/components/UI/MyButton.vue";
  import MySelect from "@/components/UI/MySelect.vue";
  export default {
    components: {
      MyButton,
      MySelect,
    },
    data() {
    return {
      dropdownOptions: [
        { value: "polygon", label: "Nepolygon", icon: "../../assets/icons/logos.svg" },
      ],
      defaultOption: "Polygon",
    };
  }
  }
</script>

<template>
   <header>
    <div class="navigate">
      <a href="#"><img src="../assets/logo.svg"/></a>
      <MyButton class="navigate-btn__upload">
       <img class="upload__img" src="../assets/icons/active.svg"/>
        Upload
      </MyButton>
      <MyButton class="navigate-btn__add">
        <img src="../assets/icons/add.svg"/>
        New folder</MyButton>
      <MyButton class="navigate-btn__delete"><img src="../assets/icons/delete.svg"/>Resycle bin</MyButton>
    </div>
    <div class="navigate">
      <div class="navigate-btn__search"><a href="#"><img src="../assets/icons/search.svg"></a></div>
      <MySelect  :options="dropdownOptions" :defaultValue="defaultOption" :showSearchIcon="true"><option>Polygon</option></MySelect>
      <div class="navigate-balance"><p><span>Used:</span> 0.4 GB</p><div class="navigate-balance__line"></div><p><span>Balance:</span> 0.6 TBY</p><img src="../assets/icons/plusY.svg"/></div>
      <div class="navigate-profile"><a href="#"><img src="../assets/icons/ava.svg"/></a></div>
    </div>
  </header>
</template>

<style scoped>
header{
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 32px 64px;
}
span{
  color:#676767;
}
.navigate, .navigate-balance{
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
}
.navigate-btn__delete{
  display: flex;
  align-items: center;
  box-shadow: none
}
.navigate-btn__upload:hover{
  background: #FFD600;
}
.navigate-btn__upload:hover img{
  opacity: 0;
}
.navigate-btn__add:hover{
  border: 1px solid #ACADB5;
}
.navigate-btn__search{
  width: 40px;
  height: 40px;
  border-radius: 50%;
  border: none;
  background-color: #F6F6F666;
  display: flex;
  justify-content: center;
  align-items: center;
}
.navigate-balance{
  border: 1px solid #EBEBEB;
  border-radius: 10px;
  padding: 10px 16px;
  gap: 12px;
  cursor: pointer;
}
.navigate-balance__line{
  border:  1px solid #EBEBEB;
  height: 20px;
}
.navigate-profile{
  width: 40px;
  height: 40px;
  border-radius: 50px;
  background-color: #EBEBEB;
}
</style>
