<script setup>
import { useRoute } from 'vue-router'
import {ref} from 'vue'

const route = useRoute()



const monster = ref([])
    
async function callApi(monsterId) {
    const url = "https://metallo.ew.r.appspot.com/monsters/"+monsterId
    const fetcher = await fetch(url)
    const json = await fetcher.json()
    monster.value = json
    console.log(json)
  
}
callApi(route.params.id)


</script>

<template>
 <!-- About Start -->
 <div class="container-fluid py-5">
        <div class="container">
            <div class="row gx-5">
                <div class="col-lg-5 mb-5 mb-lg-0" style="min-height: 500px;">
                    <div class="position-relative h-100">
                        <img class="position-absolute w-100 h-100 rounded" :src=monster.image style="object-fit: cover;">
                    </div>
                </div>
                <div class="col-lg-7">
                    <div class="border-start border-5 border-primary ps-5 mb-5">
                        <h6 class="text-primary text-uppercase">{{monster.category}}</h6>
                        <h1 class="display-5 text-uppercase mb-0">{{monster.name}}</h1>
                    </div>
                    <h4 class="text-body mb-4">{{monster.description}}</h4>
                 
                </div>
            </div>
        </div>
    </div>
    <!-- About End -->

</template>