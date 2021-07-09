<template>
  <v-container fill-height fluid class="container">
    <v-row >
      <v-col cols="12" style="align:center">
        
      </v-col>

      <v-col class="mb-4">
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
              <v-progress-circular v-if="!$vuetify.theme.dark" :value="item.catalog.review_rating" color="purple" :rotate="-90" class="mr-4">{{item.catalog.review_rating}}</v-progress-circular>
              <v-progress-circular v-if="$vuetify.theme.dark" :value="item.catalog.review_rating" color="#e367f6" :rotate="-90" class="mr-4">{{item.catalog.review_rating}}</v-progress-circular>
              <span>Execellent . {{item.catalog.review_count}} reviews</span>

            </v-col>
        </div>
          </v-row>
        
        </div>

      </v-col>

      <v-col
        class="mb-5"
        cols="12"
      >
   <!--     <h2 class="headline font-weight-bold mb-3">
          What's next?
        </h2>

        <v-row justify="center">
          <a
            v-for="(next, i) in xtra"
            :key="i"
            class="subheading mx-3"
            target="_blank"
          >
            {{ next }}
          </a>
        </v-row>
      </v-col>
      

      <v-col
        class="mb-5"
        cols="12"
      >
        <h2 class="headline font-weight-bold mb-3">
          Important Links
        </h2>

        <v-row justify="center">
          <a
            v-for="(link, i) in importantLinks"
            :key="i"
            :href="link.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ link.text }}
          </a>
        </v-row>
      </v-col>

      <v-col
        class="mb-5"
        cols="12"
      >
        <h2 class="headline font-weight-bold mb-3">
          Ecosystem
        </h2>-->
<v-sheet elevation="7">
  <v-tabs
      color="black"
      center-active
      centered
      v-if="!$vuetify.theme.dark"
      
    >
      <v-tab><v-icon  class="mr-2 mb-5 mt-5">mdi-apps-box</v-icon>Photos</v-tab>
    </v-tabs>
    <v-tabs
      color="white"
      center-active
      centered
      v-if="$vuetify.theme.dark"
      
    >
      <v-tab><v-icon  class="mr-2 mb-5 mt-5">mdi-apps-box</v-icon>Photos</v-tab>
    </v-tabs>
      <v-tabs
        background-color="normal"

        show-arrows
      >
        <v-tabs-slider color="blue"></v-tabs-slider>
        
        <v-tab
          v-for="i in itemTab"
          :key="i"
        >
          {{ i }}
        </v-tab>
      
    <br><br>
    <v-tab-item
          v-for="n in 20"
          :key="n"
        >
      <div v-if="n==1">
        <v-row justify="center">
          <div
            v-for="eco in ecosystem.data"
            :key="eco"
            class="subheading mx-3"
            target="_blank"
          >
          
                <v-row>
                          
                  <v-col
                    v-for="item in eco.images" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                  <v-hover
                    v-slot="{ hover }"
                  >
                  <v-card :elevation="hover ? 10 : 2"
                      :class="{ 'on-hover': hover }">
                    <v-dialog
                      v-model="dialog"
                      width="500"
                    >
                    <template v-slot:activator="{ on, attrs }">
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
                      v-bind="attrs"
                      v-on="on"
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
                    </template>
                    <v-card>
       <!-- <v-card-title class="text-h5 grey lighten-2">
          Privacy Policy
        </v-card-title>

        <v-card-text>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
        </v-card-text>-->
        <v-carousel
              cycle
              hide-delimiter-background
              hide-delimiters
              show-arrows-on-hover
            >
              <v-carousel-item
                v-for="(slide, i) in eco.images"
                :key="i"
              >
                <v-sheet
                  height="100%"
                >
                  <v-row
                    class="fill-height"
                    align="center"
                    justify="center"
                  >
                    <div class="text-h2">
                      
                    </div>
                     <v-img
                      :src="slide.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"

                    ></v-img>
                  </v-row>
                </v-sheet>
              </v-carousel-item>
            </v-carousel>

        <v-divider></v-divider>
      </v-card>
    </v-dialog>
        </v-card>
                  </v-hover>

                  </v-col>
                </v-row>

          </div>
        </v-row>
      </div>
      <div v-if="n==2">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    class="d-flex child-flex"
                    cols="4"
                  >
                  <v-hover
                    v-slot="{ hover }"
                  >
                  <v-card :elevation="hover ? 10 : 2"
                      :class="{ 'on-hover': hover }">
                    <v-dialog
                      v-model="dialog"
                      width="500"
                    >
                    <template v-slot:activator="{ on, attrs }">
                    <v-img
                      :src="'https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/b07c5c31_z.jpg'"

                      aspect-ratio="1"
                      class="grey lighten-2"
                      v-bind="attrs"
                      v-on="on"
                      
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
                    </template>
                    <v-card>
       <!-- <v-card-title class="text-h5 grey lighten-2">
          Privacy Policy
        </v-card-title>

        <v-card-text>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
        </v-card-text>-->
        <v-carousel :show-arrows="false">
    <v-carousel-item
      :src="'https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/b07c5c31_z.jpg'"
    ></v-carousel-item>
  </v-carousel>

        <v-divider></v-divider>
      </v-card>
    </v-dialog>
                  </v-card>
                  </v-hover>
                    
                  </v-col>
                </v-row>
        </v-row>
      </div>
      <div v-if="n==3">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="'https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/9c2ca042_z.jpg'"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==4">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in room" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==5">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="'https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/e427601d_z.jpg'"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==6">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="'https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/b6fa2d73_z.jpg'"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==7">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in amenity" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==8">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in bathroom" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==9">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in indoorPool" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==10">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in gym" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==11">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in spa" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==12">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in restaurant" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==13">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in breakfast" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==14">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in bar" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==15">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in meeting" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==16">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in business" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==17">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in lounge" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==18">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in extDetail" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==19">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in exterior" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
      <div v-if="n==20">
        <v-row justify="center">
                <v-row>    
                  <v-col
                    v-for="item in city" :key="item"
                    class="d-flex child-flex"
                    cols="4"
                  >
                    <v-img
                      :src="item.size_lg"

                      aspect-ratio="1"
                      class="grey lighten-2"
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
                </v-row>
        </v-row>
      </div>
    </v-tab-item>
        </v-tabs>
    </v-sheet>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import axios from 'axios'
  export default {
    name: 'HelloWorld',
    
    data () {
    return {
      overlay: false,
      zIndex: 5,
      ecosystem: null,
      itemTab: ["All","Featured Image", "Lobby", "Room", "Living Area", "Living Room","Room Amenity", "Bathroom", "Indoor Pool",
      "Gym", "Spa", "Restaurant", "Breakfast Meal", "Bar", "Meeting Facility", "Business Center", "Executive Lounge",
      "Exterior Detail", "Exterior", "City View"],
      room:[{
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/859a4e34_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/859a4e34_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/859a4e34_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/cc4f3703_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/cc4f3703_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/cc4f3703_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/622799c3_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/622799c3_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/622799c3_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/4131c416_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/4131c416_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/4131c416_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/5faff048_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/5faff048_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/5faff048_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/0097de49_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/0097de49_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/0097de49_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/01495343_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/01495343_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/01495343_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/7d1caba4_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/7d1caba4_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/7d1caba4_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/c85421fd_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/c85421fd_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/c85421fd_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/fb359ad2_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/fb359ad2_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/fb359ad2_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/8d6c18ac_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/8d6c18ac_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/8d6c18ac_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/0b7f658e_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/0b7f658e_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/0b7f658e_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/0adce361_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/0adce361_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/0adce361_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/024a6ce3_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/024a6ce3_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/024a6ce3_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/e47562d8_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/e47562d8_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/e47562d8_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/876e0cb6_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/876e0cb6_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/876e0cb6_t.jpg"
         },
         {
            "caption":"Room",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/a6d324c5_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/a6d324c5_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/a6d324c5_t.jpg"
         },],
      amenity: [{
            "caption":"Room Amenity",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d3bc2bc3_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d3bc2bc3_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d3bc2bc3_t.jpg"
         },
         {
            "caption":"Room Amenity",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/66fea4dd_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/66fea4dd_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/66fea4dd_t.jpg"
         }],
      itemFeatured : null,
      bathroom: [{
            "caption":"Bathroom",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/8fb35619_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/8fb35619_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/8fb35619_t.jpg"
         },
         {
            "caption":"Bathroom",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/97b909e9_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/97b909e9_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/97b909e9_t.jpg"
         },
         {
            "caption":"Bathroom",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/fc5c2127_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/fc5c2127_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/fc5c2127_t.jpg"
         },
         {
            "caption":"Bathroom",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/b30b18ad_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/b30b18ad_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/b30b18ad_t.jpg"
         },
         {
            "caption":"Bathroom",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/3284e5e4_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/3284e5e4_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/3284e5e4_t.jpg"
         },
         {
            "caption":"Bathroom",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/8828ebee_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/8828ebee_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/8828ebee_t.jpg"
         },
         {
            "caption":"Bathroom",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/256a5cfa_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/256a5cfa_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/256a5cfa_t.jpg"
         },
         {
            "caption":"Bathroom",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/01f59ee4_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/01f59ee4_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/01f59ee4_t.jpg"
         },
         {
            "caption":"Bathroom",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d5737751_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d5737751_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d5737751_t.jpg"
         },
         {
            "caption":"Bathroom",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/31f0ca1f_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/31f0ca1f_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/31f0ca1f_t.jpg"
         },
         {
            "caption":"Bathroom",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/23b06361_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/23b06361_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/23b06361_t.jpg"
         }],
      indoorPool: [{
            "caption":"Indoor Pool",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/39025822_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/39025822_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/39025822_t.jpg"
         },
         {
            "caption":"Indoor Pool",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/336fea1f_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/336fea1f_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/336fea1f_t.jpg"
         },
         {
            "caption":"Indoor Pool",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/1aa94019_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/1aa94019_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/1aa94019_t.jpg"
         }],
      gym:[{
            "caption":"Gym",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/c5541d68_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/c5541d68_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/c5541d68_t.jpg"
         },
         {
            "caption":"Gym",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/79eacf03_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/79eacf03_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/79eacf03_t.jpg"
         },
         {
            "caption":"Gym",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/6eb556c9_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/6eb556c9_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/6eb556c9_t.jpg"
         }],
      spa:[{
            "caption":"Spa",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/5a29e486_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/5a29e486_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/5a29e486_t.jpg"
         },
         {
            "caption":"Spa",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/562c1270_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/562c1270_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/562c1270_t.jpg"
         },
         {
            "caption":"Spa",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/f50e3b08_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/f50e3b08_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/f50e3b08_t.jpg"
         },
         {
            "caption":"Spa",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/f8241de2_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/f8241de2_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/f8241de2_t.jpg"
         }],
      restaurant:[{
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/f9673cb2_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/f9673cb2_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/f9673cb2_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/115cee20_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/115cee20_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/115cee20_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/63d99120_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/63d99120_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/63d99120_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d3bf562d_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d3bf562d_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d3bf562d_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/9a8d1aba_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/9a8d1aba_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/9a8d1aba_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/2ca5ca5b_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/2ca5ca5b_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/2ca5ca5b_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/1382a869_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/1382a869_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/1382a869_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d522a174_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d522a174_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d522a174_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/c59ba85f_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/c59ba85f_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/c59ba85f_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/bf64f1eb_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/bf64f1eb_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/bf64f1eb_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/056266b8_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/056266b8_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/056266b8_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/06f2a70b_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/06f2a70b_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/06f2a70b_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/0eb53a20_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/0eb53a20_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/0eb53a20_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/ef67f16d_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/ef67f16d_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/ef67f16d_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/2bd7425d_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/2bd7425d_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/2bd7425d_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/87ff09a1_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/87ff09a1_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/87ff09a1_t.jpg"
         },
         {
            "caption":"Restaurant",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/5e8a05c5_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/5e8a05c5_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/5e8a05c5_t.jpg"
         }],
      breakfast:[{
            "caption":"Breakfast Meal",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/1ccf8ae1_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/1ccf8ae1_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/1ccf8ae1_t.jpg"
         }],
      bar:[ {
            "caption":"Bar",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/80b8a4be_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/80b8a4be_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/80b8a4be_t.jpg"
         }],
      meeting:[{
            "caption":"Meeting Facility",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/946856f6_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/946856f6_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/946856f6_t.jpg"
         },
         {
            "caption":"Meeting Facility",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/bdd60585_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/bdd60585_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/bdd60585_t.jpg"
         },
         {
            "caption":"Meeting Facility",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/3ef31479_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/3ef31479_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/3ef31479_t.jpg"
         },
         {
            "caption":"Meeting Facility",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/bbe129a1_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/bbe129a1_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/bbe129a1_t.jpg"
         },
         {
            "caption":"Meeting Facility",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/b0435d94_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/b0435d94_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/b0435d94_t.jpg"
         },
         {
            "caption":"Meeting Facility",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/139823cf_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/139823cf_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/139823cf_t.jpg"
         },
         {
            "caption":"Meeting Facility",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/dd7a879e_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/dd7a879e_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/dd7a879e_t.jpg"
         },
         {
            "caption":"Meeting Facility",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d2dfd039_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d2dfd039_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/d2dfd039_t.jpg"
         },
         {
            "caption":"Meeting Facility",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/5bb3debf_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/5bb3debf_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/5bb3debf_t.jpg"
         },
         {
            "caption":"Meeting Facility",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/1bd26a74_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/1bd26a74_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/1bd26a74_t.jpg"
         },
         {
            "caption":"Meeting Facility",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/a49223ab_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/a49223ab_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/a49223ab_t.jpg"
         }],
      business:[{
            "caption":"Business Center",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/6c34d9ca_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/6c34d9ca_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/6c34d9ca_t.jpg"
         },
         {
            "caption":"Business Center",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/46a23860_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/46a23860_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/46a23860_t.jpg"
         }],
      lounge:[{
            "caption":"Executive Lounge",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/528d4479_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/528d4479_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/528d4479_t.jpg"
         }],
      extDetail:[{
            "caption":"Exterior detail",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/4e4756bd_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/4e4756bd_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/4e4756bd_t.jpg"
         }],
      exterior:[{
            "caption":"Exterior",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/10cc74fb_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/10cc74fb_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/10cc74fb_t.jpg"
         },
         {
            "caption":"Exterior",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/42b58855_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/42b58855_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/42b58855_t.jpg"
         }],
      city:[{
            "caption":"City View",
            "size_lg":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/eb6c3abb_z.jpg",
            "size_sm":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/eb6c3abb_b.jpg",
            "size_xs":"https://i.travelapi.com/hotels/16000000/15670000/15663900/15663894/eb6c3abb_t.jpg"
         }],

    }
  },
  
  mounted () {
    axios
      .get('./file.json')
      .then(response => (this.ecosystem = response))

    axios
      .get('./fileFeatured.json')
      .then(response => (this.itemFeatured = response))
  },
  
  
  }
  
</script>
<style scoped>
.v-card {
  transition: opacity .2s ease-in-out;
}

.v-card.on-hover {
  opacity: 0.8;
 }

.show-btns {
  color: rgba(255, 255, 255, 1) !important;
}

.v-application .elevation-7 {
    box-shadow: none !important;
}
</style>