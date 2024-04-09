<script setup>

import { useRouter } from "vue-router";
import {ref} from 'vue'



const router = useRouter()
const monsters = ref([])
const monsterNumber = ref ("")

const currentPage  = ref(1)
const totalPages = ref(2)

async function callApi() {
    const url = `https://metallo.ew.r.appspot.com/monsters?page=${currentPage.value}`
    const fetcher = await fetch(url)
    const json = await fetcher.json()
    monsters.value = json
    monsterNumber.value = monsters.value.length;
    router.push({ query: { page: url } }); 
    console.log(monsterNumber)
  
}
callApi()

const prevPage=()=>{
    if(currentPage.value == totalPages.value)
    currentPage.value--;
    callApi()
}
const nextPage=()=>{
    if(currentPage.value < totalPages.value)
    currentPage.value++;
    callApi()
}

</script>

<template>
       <!-- Blog Start -->
       <div class="container py-5">
        <div class="row">
            <!-- Monster list Start -->
            <div class="col">
                <div class="mb-5">
                    <h3 class="text-uppercase border-start border-5 border-primary ps-3 mb-4">Every Monsters</h3>
                    <div class="d-flex overflow-hidden mb-3 bg-light" v-for="monster in monsters" :key="monster.id">
                        <img class="img-fluid" :src=monster.image style="width: 100px; height: 100px; object-fit: cover;" alt="">
                        <router-link :to="'/monsters/details/'+monster._id"><a href="" class="h5 d-flex align-items-center bg-light px-3 mb-0">{{monster.name}}
                        </a></router-link>
                    </div>
                </div>
                <div class="d-flex">
                <button type="button" @click="prevPage" class="col-5 btn btn-primary">Precedent</button>
            
                <p class="col-2 text-center btn ">{{ currentPage }}</p>      
             <button type="button" @click="nextPage" class="col-5 btn btn-primary">suivant</button>
            </div>
            </div>
                   
            <!-- Monster list End -->

          
        </div>
    </div>

</template>