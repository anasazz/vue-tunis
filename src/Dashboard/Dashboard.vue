<template>

    <div class='p-4 grid'>
        <h1>dash</h1>
            <div class="grid grid-flow-row-dense grid-cols-3 grid-rows-3 ...">



                

<router-link v-for='car in cars' :key="car.id" :to="{ name: 'CarDetails', params: { id: car.id }}">


           <div  class="max-w-sm rounded overflow-hidden shadow-lg p-1">
            <!-- <img class="w-full" :src="car.link" alt="Sunset in the mountains"> -->
            <div class="px-6 py-4">
                <div class="font-bold text-xl mb-2">{{car.carMake}} - {{car.carYear}}</div>
                <p class="text-gray-700 text-base">
                    {{car.carModel}}
                </p>
            </div>
            <div class="px-6 pt-4 pb-2">
                <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#photography</span>
                <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#travel</span>
                <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#winter</span>
            </div>
       


   

            </div>

            </router-link>


</div>

 

        </div>



  
</template>

<script>
import axios from 'axios'
export default {
    name:'Dashboard',

    data(){
        return {

        
            cars: []
        }
    }
    ,

    mounted(){
        this.getCars()
    },

    methods:{
        getCars(){
            axios.get('/cars/')
            .then(response =>{
                this.cars = response.data
            })
            .catch(error => {
                console.log('err', error);
            })
        }
    }

}
</script>

<style>

</style>