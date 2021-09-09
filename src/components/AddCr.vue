<template>
    <input v-model="crText"  class="shadow appearance-none border rounded w-2/5 py-2 px-3 mr-4 text-grey-darker" placeholder="Çizgi Roman İsmi Gir...">
        <input v-model="crImg"  class="mt-2 shadow appearance-none border rounded w-2/5 py-2 px-3 mr-4 text-grey-darker" placeholder="Çizgi Roman Fotoğraf Linki...">
      <div class="flex justify-around">
        <div class="flex items-center border-2 mt-2 p-2 mr-5">
        <span class="mr-3">Satın alındı mı? </span> <input type="checkbox" name="satis" v-model="satis" >
       </div>
        <div class="flex items-center border-2 mt-2 p-2">
        <span class="mr-3">Okundu mu? </span> <input type="checkbox" name="okuma" v-model="okuma" >
        </div>
      </div>
      <button @click="addCr(crText,crImg,okuma,satis),reset()" class="mt-2 flex-no-shrink py-2 px-5 border-2 rounded text-green-500 border-teal hover:text-white hover:bg-green-500">Ekle</button>
    
</template>

<script>
export default {
    inject:["addCr"],
     data() {
        return {
            okuma : false,
            satis: false,
            crText : null,
            crImg : ""
        }
    },
    methods:{
        reset(){
      this.crText = "";
      this.satis = false;
      this.okuma = false;
      this.crImg = "";

    },
    }
}
</script>