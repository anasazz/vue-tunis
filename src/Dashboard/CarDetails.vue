<template>

        <div>

        <h1>cardetails</h1>


           <div  class="maxrounded overflow-hidden shadow-lg p-1">
            <!-- <img class="w-full" :src="car.link" alt="Sunset in the mountains"> -->
            <div class="p-5 m-5">
                <div class="font-bold text-xl mb-2">{{car.carMake}} - {{car.carYear}}</div>
                <p class="text-gray-700 text-base">
                  carModel :   {{car.carModel}}
                </p>

                <p class="text-gray-700 text-base">
                   carEngine :  {{car.carEngine}}
                </p>

                <p class="text-gray-700 text-base">
                    carCylinders : {{car.carCylinders}}
                </p>

                <p class="text-gray-700 text-base">
                   carTransmission :  {{car.carTransmission}}
                </p>

                <p class="text-gray-700 text-base">
                   carMileage : {{car.carMileage}}
                </p>

                 <p v-if='car.link' class="text-gray-700 text-base">
                   lien : 
                   <a target="_blank" :href="car.link">visit website</a>
                </p>

  

            </div>
            <div class="px-6 pt-4 pb-2">
                <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#photography</span>
                <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#travel</span>
                <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#winter</span>
            </div>


           </div>
           </div>
  
</template>

<script>
import axios from 'axios'
export default {
    name:'CarDetails',

    data(){
        return {

        
            car: ''
        }
    }
    ,

    mounted(){
        this.getCarDetails()
    },

    methods:{
        getCarDetails(){
         

            const id = this.$route.params.id

            // ""
            // ''
            // ``



            axios.get(`/detail/${id}/`)
            .then(response =>{
                this.car = response.data
                console.log('car deatils', response.data);
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