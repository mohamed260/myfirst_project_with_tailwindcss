<template>
  <div id="app" class=" min-h-screen bg-gray-200 antialiased xl:flex xl:flex-col xl:h-screen">
    <sideHeader class="xl:flex-shrink-0" />
    <div class="xl:flex-1 xl:flex xl:overflow-y-hidden">
      <searchFilters/>

      <main class="py-6 xl:flex-1 xl:overflow-x-hidden">
        <div class="px-4">
          <h3 class="text-gray-900 text-xl">Los Angeles</h3>
          <p class="text-gray-600">live like the stars in these luxurious Southern California estates.</p>
        </div>
        <div class="mt-6 sm:-ml-2 sm:overflow-x-auto">
          <div class="px-4 sm:flex sm:px-4 sm:pb-8">
            <div v-bind:key=i v-for="(property, i) in properties" :class="{'mt-10': i > 0}" class="sm:mt-0 sm:w-80 sm:flex-shrink-0" >
              <searchCard :property="property" />
            </div>
          </div>
        </div>

        <div class="px-4 mt-8">
          <h3 class="text-gray-900 text-xl">New York</h3>
          <p class="text-gray-600">live like the stars in these luxurious New York estates.</p>
        </div>
        <div class="mt-6 sm:-ml-2 sm:overflow-x-auto">
          <div class="px-4 sm:flex sm:px-4 sm:pb-8">
            <div v-bind:key=i v-for="(property, i) in properties" :class="{'mt-10': i > 0}" class="sm:mt-0 sm:w-80 sm:flex-shrink-0" >
              <searchCard :property="property" />
            </div>
          </div>
        </div>
      </main>

    </div>
    
  </div>
</template>

<script>

import HelloWorld from './components/HelloWorld'
import sideHeader from './components/SideHeader.vue'
import SearchFilters from './components/SearchFilters.vue'
import SearchCard from './components/SearchCard.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    sideHeader,
    SearchFilters,
    SearchCard,
  },
  data() {
    return {
      properties:[
        {
          imageUrl: "https://images.unsplash.com/photo-1512917774080-9991f1c4c750?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=400&q=60",
          beds: 3,
          baths: 10,
          title: "modern Home In City Center",
          price: 10000,
          reviewCount: 34,
          reting: 2,
        },
        {
          imageUrl: 'https://images.unsplash.com/photo-1564013799919-ab600027ffc6?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=400&q=60',
          beds: 4,
          baths: 5,
          title: "modern Home In City Center",
          price: 140000,
          reviewCount: 34,
          reting: 5,
        },
        {
          imageUrl: 'https://images.unsplash.com/photo-1531971589569-0d9370cbe1e5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=400&q=60',
          beds: 2,
          baths: 1,
          title: "modern Home In City Center",
          price: 140000,
          reviewCount: 34,
          reting: 1,
        },
        {
          imageUrl: 'https://images.unsplash.com/photo-1542314831-068cd1dbfeeb?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=400&q=60',
          beds: 8,
          baths: 6,
          title: "modern Home In City Center",
          price: 140000,
          reviewCount: 34,
          reting: 3,
        },
      ]
    }
  }

}
  
</script>

<style src="./assets/css/tailwind.css"></style>
