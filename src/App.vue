<template>
  <div class="container mx-auto flex flex-col">
    <div class="header flex justify-center items-center mt-5">
      <h3 class="text-3xl">Çizgi Roman Takip</h3>
    </div>
    <div class="main flex justify-center items-center mt-5 flex-col">
 
       <AddCr  />
      
     
      <table class="w-full mt-5">
        <thead>
          <tr class="text-md font-semibold tracking-wide text-left text-gray-900 bg-gray-100 uppercase border-b border-gray-600">
            <th class="px-4 py-3">Çizgi Roman Adı</th>
            <th class="px-4 py-3">Satın Alındı mı?</th>
            <th class="px-4 py-3">Okundu mu?</th>
          </tr>
        </thead>
        <tbody class="bg-white">
         <TheList />
        </tbody>
      </table>
      
    </div>
  </div>
</template>

<script>
import TheList from "./components/TheList.vue"
import AddCr from "./components/AddCr.vue"
export default {
  components:{
    TheList,AddCr
  },
  data() {
    return {
    provideData:{  crList:[{id:1,name:"Superman Red Son",satis:true,okuma:false,img:"https://images-na.ssl-images-amazon.com/images/I/51-n8hNfSpL._SY344_BO1,204,203,200_QL70_ML2_.jpg"},
    {id:1,name:"İnfinity Gaunlet",satis:false,okuma:false,img:"https://images-na.ssl-images-amazon.com/images/I/61jeWVgiBnL._SX331_BO1,204,203,200_.jpg"},
    {id:1,name:"WOLVERINE İHTİYAR LOGAN",satis:true,okuma:false,img:"https://images-na.ssl-images-amazon.com/images/I/51cpLqWkxvL._SY344_BO1,204,203,200_QL70_ML2_.jpg"},
    {id:1,name:"Batman Beyaz Şövalye",satis:true,okuma:true,img:"https://images-na.ssl-images-amazon.com/images/I/51GjhgdgCKL._SY344_BO1,204,203,200_QL70_ML2_.jpg"}],},
      
    }
  },
  provide(){
    return{
      List : this.provideData,
      getColor : this.getColor,
      addCr : this.addCr
    }
  },
  methods:{
    addCr(item,img,okuma,satis){
      if(item=="" || img == ""){
        alert("Lütfen Bir İsim giriniz")
      }
      else{
        this.provideData.crList.push({id:new Date().getTime(),name:item,satis:satis,okuma:okuma,img:img})
      }
      
     
    },
    
    getColor(check){
      if(check == false){
        return "bg-red-700"
      }
      else{
        return "bg-green-700"
      }
    }

  }
}
</script>