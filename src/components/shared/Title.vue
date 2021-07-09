<template>
    <div class="tengah">
          <v-row>
            <div>
        <v-col>
        <v-img
          :src="'https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/b07c5c31_b.jpg'"
          class="rounded-circle grey lighten-2 mr-10 ml-10"
          aspect-ratio="1"
          :height="200"
          :width="200"
          
          >
                      <template v-slot:placeholder>
                        <v-row
                          class="fill-height ma-0"
                          align="center"
                          justify="center"
                        >
                          <v-progress-circular
                            indeterminate
                            color="grey lighten-5"
                          ></v-progress-circular>
                        </v-row>
                      </template>
                    </v-img>
        </v-col>
        </div>
        <div>
            <v-col v-for="item in ecosystem.data"
                :key="item">
              <h3>{{item.name}}</h3>
              <v-icon  class="mr-2 mb-5 mt-5" color="yellow darken-2">mdi-star</v-icon>
              <v-icon  class="mr-2 mb-5 mt-5" color="yellow darken-2">mdi-star</v-icon>
              <v-icon  class="mr-2 mb-5 mt-5" color="yellow darken-2">mdi-star</v-icon>
              <v-icon  class="mr-2 mb-5 mt-5" color="yellow darken-2">mdi-star</v-icon>
              <v-icon  class="mr-2 mb-5 mt-5" color="yellow darken-2">mdi-star</v-icon>
              <v-btn class="mr-2 pr-1 pl-1 pb-1 pt-1">{{item.catalog.category}}</v-btn><br>
              <p>{{item.catalog.address}}</p>
              <v-progress-circular v-if="$vuetify.theme.dark" :value="item.catalog.review_rating" color="#e367f6" :rotate="-90" class="mr-4">{{item.catalog.review_rating}}</v-progress-circular>
              <v-progress-circular v-if="!$vuetify.theme.dark" :value="item.catalog.review_rating" color="purple" :rotate="-90" class="mr-4">{{item.catalog.review_rating}}</v-progress-circular>
              <span>Execellent . {{item.catalog.review_count}} reviews</span>

            </v-col>
        </div>
          </v-row>
        
        </div>
</template>
<script>
export default {
    name:"Title"
}
</script>