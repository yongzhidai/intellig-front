<template>
  <div class="about">
    <h1>This is an about page</h1>
    <MyDataList/>
  </div>
</template>
<script>
// @ is an alias to /src
import MyDataList from "@/components/MyDataList.vue";

export default {
  name: "home",
  components: {
    MyDataList
  }
};
</script>