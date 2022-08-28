<script setup></script>
<template>
    <div class="center">
        <div class="lds-dual-ring"></div>
        <p>Loading</p>
    </div>
    

</template>
<style scoped lang="scss">
.center {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 2rem;
    & p{
        overflow: hidden;
        text-align: center;
        font-size: 2rem;
        
        font-family:Verdana, Geneva, Tahoma, sans-serif;
    }
}
.lds-dual-ring {
  display: inline-block;
  width: 80px;
  height: 80px;
}
.lds-dual-ring:after {
  content: " ";
  display: block;
  width: 64px;
  height: 64px;
  margin: 8px;
  border-radius: 50%;
  border: 6px solid rgb(0, 0, 0);
  border-color: rgb(0, 0, 0) transparent rgb(0, 0, 0) transparent;
  animation: lds-dual-ring 1.2s linear infinite;
}
@keyframes lds-dual-ring {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

</style>