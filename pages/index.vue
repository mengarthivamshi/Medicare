<template>
  <div class="flex flex-col">
    <div class="fixed top-0 left-0 right-0 z-10 bg-white">
      <NavigatorComponent></NavigatorComponent>
    </div>
    <div class="pt-[60px]"> <!-- Adjust the padding to match the height of your navbar -->
      <Header></Header>  
      <Carosol></Carosol>  
      <SocialMediaBar></SocialMediaBar>
      <HelpingPaitents></HelpingPaitents>
      <Excellence></Excellence>
      <Contact></Contact>
    </div>
  </div>
</template>

<script lang="ts" setup>

</script>

<style>

</style>