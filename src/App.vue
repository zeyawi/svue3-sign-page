<template>
  <div class="full-screen">
    <sign-in/>
  </div>
</template>

<script>

import SignIn from "@/components/SignIn";
export default {
  name: "App",
  components: {SignIn},
};
</script>

<style lang="less" scoped>
.full-screen{
  width: 100vw;
  height: 100vh;
  background:radial-gradient(#e2e4ed, #1827b9);
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
