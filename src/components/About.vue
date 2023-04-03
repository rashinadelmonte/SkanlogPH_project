<script setup lang="ts">
    import about1 from "@/assets/assets/img/about/1.jpg";
    import api from "@/services/apiService";
    import { ref, onMounted } from "vue";
 
    const getHistory = ref({
      content: ""
    });

    onMounted(async() => {
      const getData = await api.get('/AboutSkanlog');

      getHistory.value = getData.data[2];
      console.log(getHistory.value);
    });


</script>
<template>
    
   <div class="bg-light my-custom-bg rounded p-4 col-xl-10 col-lg-10 mx-auto content"
      data-aos="zoom-in" data-aos-delay="50"
   >
      <div v-html="getHistory.content"></div>
    </div>
      
</template>

<style> 
  .content {
    display: flex;
    margin-top: 5rem;
  }
  .my-custom-bg {
  background-color: #b9601c;
  border: 1px solid #38085f;
}

  
</style>