<template>
  <tabla 
  :key="skill"
  :index="index"
  :names-array="skills"
  />
</template>

<script>
  import Tabla from "./components/Tabla.vue";

  export default{
    components: {
      Tabla,
    },
    data () {
      
    return {
     
      skills: [
        {
          name: 'Servicios',
          amount:'200',
          paid:false,
          required: 1,
          vMode1: ''
        },
        {
          name: 'Hosting',
          amount:'90',
          paid:true,
          required: 3,
          vMode1: ''
        }
      ],
      
    }
  }
  };
</script>