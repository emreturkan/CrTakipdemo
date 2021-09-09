<template>
     <tr class="text-gray-700 " v-for="item in List.crList" :key="item.id">
            <td class="px-4 py-3 border">
              <div class="flex items-center text-sm">
                <div class="relative w-18 h-24 mr-3 rounded md:block">
                  <img class="object-cover w-full h-24 rounded" :src="item.img" alt="" loading="lazy" />
                  <div class="absolute inset-0 rounded-full shadow-inner" aria-hidden="true"></div>
                </div>
                <div>
                  <p class="font-semibold text-black">{{item.name}}</p>
                </div>
              </div>
            </td>
            <td class="px-4 py-3 text-ms font-semibold border" >
              <span @click="item.satis = !item.satis" class="px-2 py-1 font-semibold leading-tight cursor-pointer text-white  rounded-sm" :class="getColor(item.satis)">{{item.satis===false ? "Alınmadı!" : "Alındı!"}}</span>
            </td>
            <td class="px-4 py-3 text-xs border">
              <span @click="item.okuma = !item.okuma" title="Değiştirebilirsin" class="px-2 py-1 font-semibold leading-tight cursor-pointer text-white  rounded-sm" :class="getColor(item.okuma)"> {{item.okuma===false ? "Okunmadı!" : "Okundu!"}} </span>
            </td>
            
          </tr>
</template>

<script>
export default {
    inject:["List","getColor"]
}
</script>