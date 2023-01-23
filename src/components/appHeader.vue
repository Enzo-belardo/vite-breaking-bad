<script>
export default{
    name: 'appHeader',
}
</script>

<template>
    <header>
        <nav class="navbar bg-body-tertiary d-flex justify-content-start">
           <div class="container-fluid">
              <div class="container-image d-flex">
                 <img src="../assets/img/Yu-Gi-Oh!_(Logo).jpg" class="img-fluid w-25" alt="">
                 <h5 class="">Yu-Gi-Oh API</h5>
              </div>
           </div>
       </nav>  
    </header>
</template>

<style lang="scss" >
@use '../styles/general' as * ;
@use '../styles/partials/variables' as * ;
.container-image{
    width: 40%;
    h5{
        font-size: 3rem;
    }
}


</style>
