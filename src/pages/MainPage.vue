<template>
  <section class="main">
    <div class="main-sort">
      <span>All files</span>
      <MySelect
        :options="dropdownOptions"
        :defaultValue="defaultOption"
        :showSearchIcon="false"
      >
        <option></option>
      </MySelect>
    </div>
    <div class="grid-container">
      <Folder v-for="(folder, index) in folders" :key="index">
        {{ folder.name }}
      </Folder>
      <File v-for="(file, index) in files" :key="index">
        {{ file.name +".XLS" }}
      </File>
    </div>
    <MyButton class="main-btn__delete">
      <img class="upload__img" src="../assets/icons/delete.svg" />
      Recycle bin
    </MyButton>
  </section>
</template>

<script>
import MySelect from "@/components/UI/MySelect.vue";
import Folder from "@/components/UI/Folder.vue";
import File from "@/components/UI/File.vue";
import MyButton from "@/components/UI/MyButton.vue";

export default {
  components: {
    MySelect,
    Folder,
    File,
    MyButton,
  },
  data() {
    return {
      dropdownOptions: [
        { value: "1", label: "By type" },
        { value: "2", label: "By size" },
        { value: "3", label: "By time" },
      ],
      defaultOption: "Sort by name",
      folders: [
        { name: "Folder 1" },
        { name: "New Folder" },
        { name: "New Folder" },
        { name: "Folder 2" },
        { name: "Folder 2" },
        { name: "Folder 2" },
      ],
      files: [
        { name: "File 1" },
        { name: "File 2" },
        { name: "WORK" },
        { name: "44" },
        { name: "543" },
      ],
    };
  },
};
</script>

<style scoped>
.main{
    padding: 0 64px;
}
.main-sort{
    display:flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 10px;
}
span{
    padding: 4px 10px;
    color:#676767;
}
span:hover{
    border-radius: 36px;
    background: rgba(246, 246, 246, 0.40);
}
.grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
    grid-auto-columns: auto;
    grid-gap: 10px;
  }
.main-btn__delete:hover{
  border: 1px solid #ACADB5;
}
.main-btn__delete{
  position: fixed;
  bottom: 32px;
  right: 140px;
  display: flex;
  justify-content: center;
}

</style>