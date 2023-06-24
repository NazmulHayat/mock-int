<template>
  <v-container class="mx-4 px-4 d-flex flex-wrap">
    <v-sheet v-for="idx in names" :key="idx" class="ma-2 pa-2" >
      <v-btn variant="flat" @click="showData(idx)" justify="center">
        {{ idx }}
      </v-btn>
    </v-sheet>

    <v-container class="cht" v-if="selectedCategory">
      <v-row>
        <v-col v-for="card in categories[selectedCategory]" :key="card.name" cols="12" sm="6" md="4">
          <v-card class="card" flex justify="center" align="center">
            <v-img :src="card.img" cover height="250px">
              <v-card-title  class="text-white">{{ card.name }}</v-card-title>
                <v-card-text class="info text-white">
                  <p>{{ card.address }}</p>
                  <p>{{ card.detail }}</p>
                  <p>{{ card.no }}</p>
                  <p>Likes: {{ card.likes }}</p>
                </v-card-text>
              </v-img>
            </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-container>
</template>

<script>
export default {
  name: 'HelloWorld',

  data() {
    return {
      names: [
        "Arts & Entertainment", "Bars", "Breweries", "Food", "Lodging", "Nightlife", "Restaurants", "steakhouse",
        "Thai", "Vegan", "Coffee & Tea", "Doughnuts", "Canadian", "French", "Hotels",
        "Comedy Club", "Landmarks", "Nightclub", "Brunch", "Asian Fusion", "Sandwiches"
      ],
      selectedCategory: null,
      categories: {
        "Arts & Entertainment": [
          {
            "name": "Art Gallery of Ontario",
            "address": "317 Dlindas Street West",
            "detail": "Toronto Ontario MST 164",
            "no": "(416) 979-6648",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/AGO_gehry_pre-opening_night_straight_01.jpg",
            "likes": "9"
          },
          {
            "name": "Royal Ontario Museum",
            "address": "100 Queens Park",
            "detail": "Toronto Ontario MSS 2C6",
            "no": "(416) 586-8000",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/August-26-2008-portfolio-IMG-2_1140-1024x683.jpg",
            "likes": "4"
          },
          {
            "name": "Ed Mirvish Theatre",
            "address": "244 Victoria Street",
            "detail": "Toronto Ontario MB VS",
            "no": "(416) 872-1212",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/hero_emt-hero2-1024x323.jpg",
            "likes": "8"
          }
        ],
        "Canadian": [
          {
            "name": "Reposado ar & Lounge",
            "address": "136 Ossington Avenue",
            "detail": "Toronto Ontario M6J2 2Z5",
            "no": "(416) 532-6474",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/Profile-Reposado3-thumb-896xauto-5215.jpg",
            "likes": "4"
          }, {
            "name": "The Hoxton",
            "address": "69 Bathruusrt Street",
            "detail": "Toronto Ontario",
            "no": "(416) 456-7321",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/IMG_0190-45-1200x800-1024x628.jpg",
            "likes": "1"
          }, {
            "name": "Crocodile Rock",
            "address": "240 Adelaide Street West",
            "detail": "Toronto Ontario M5H 1W7",
            "no": "(416) 599-8751",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/mezz-05.jpg",
            "likes": "6"
          },{
            "name": "Parts and Labour",
            "address": "1566 Queen Street West",
            "detail": "Toronto Ontario M6R 1A6",
            "no": "(416) 588-7750",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/partsnlabour_nov2010-02.jpg",
            "likes": "2"
          }
        ],
        "Bars": [
          {
            "name": "Alo Restaurant",
            "address": "163 Spadina Avenue",
            "detail": "Toronto Ontario M5V 2A5",
            "no": "(416) 260-2222",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/toronto-restaurant-alo-optimized-1024x614.jpg",
            "likes": "3"
          }, {
            "name": "Reposado Bar & Lounge",
            "address": "136 Ossington Avenue",
            "detail": "Toronto Ontario M6J 2Z5",
            "no": "(416) 532-6474",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/Profile-Reposado3-thumb-896xauto-5215.jpg",
            "likes": "4"
          }, {
            "name": "Track and Field Bar",
            "address": "860 College Street",
            "detail": "Toronto Ontario M6H 1A2",
            "no": "(416) 555-1234",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/trackfield-53.jpg",
            "likes": "1" 
          }
        ],
        "Breweries": [
          {
            "name": "Track and Field Bar",
            "address": "860 College Street",
            "detail": "Toronto Ontario M6H 1A2",
            "no": "(416) 555-1234",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/trackfield-53.jpg",
            "likes": "1" 
          },{
            "name": "Parts and Labour",
            "address": "1566 Queen Street West",
            "detail": "Toronto Ontario M6R 1A6",
            "no": "(416) 588-7750",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/partsnlabour_nov2010-02.jpg",
            "likes": "2"
          }
        ],
        
        "Food": [
          {
            "name": "Soi Thai Street Food",
            "address": "651 College Street",
            "detail": "Toronto Ontario M6G 1B7",
            "no": "(647) 345-8838",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/Soi_mini_mini-1024x608.jpg",
            "likes": "0"
          }, {
            "name": "Parts and Labour",
            "address": "1566 Queen Street West",
            "detail": "Toronto Ontario M6R 1A6",
            "no": "(416) 588-7750",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/partsnlabour_nov2010-02.jpg",
            "likes": "2"
          }
        ],
        "Lodging": [
          {
            "name": "The Ritz-Carlton",
            "address": "181 Wellington Streett-W",
            "detail": "Toronto Ontario M5J 2H5",
            "no": "(416) 585-2500",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/RCTORON_00094_conversion-1024x683.jpg",
            "likes": "4"   
          }, {
            "name": "The Drake Hotel",
            "address": "1150 Queen Street West",
            "detail": "Toronto Ontario M6J 1J3",
            "no": "(416)-531-5042",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/Drake-Hotel-Facade-compressor.jpg",
            "likes": "3"
          }
        ],
        "Nightlife": [
          {
            "name": "Reposado ar & Lounge",
            "address": "136 Ossington Avenue",
            "detail": "Toronto Ontario M6J2 2Z5",
            "no": "(416) 532-6474",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/Profile-Reposado3-thumb-896xauto-5215.jpg",
            "likes": "4"
          }, {
            "name": "The Hoxton",
            "address": "69 Bathruusrt Street",
            "detail": "Toronto Ontario",
            "no": "(416) 456-7321",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/IMG_0190-45-1200x800-1024x628.jpg",
            "likes": "1"
          }, {
            "name": "Crocodile Rock",
            "address": "240 Adelaide Street West",
            "detail": "Toronto Ontario M5H 1W7",
            "no": "(416) 599-8751",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/mezz-05.jpg",
            "likes": "6"
          },{
            "name": "Parts and Labour",
            "address": "1566 Queen Street West",
            "detail": "Toronto Ontario M6R 1A6",
            "no": "(416) 588-7750",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/partsnlabour_nov2010-02.jpg",
            "likes": "2"
          }
        ],
        "Restaurants": [
          {
            "name": "Alo Restuarant",
            "address": "163 Spadina Avenue",
            "detail": "Toronto Ontario M5V 2A5",
            "no": "(416) 260-2222",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/toronto-restaurant-alo-optimized-1024x614.jpg",
            "likes": "3"
          }
        ],
        "steakhouse": [
          {
            "name": "Jacobs & Co. Steakhouse",
            "address": "12 Brant Street",
            "detail": "Toronto Ontario M5V 2M1",
            "no": "(416) 366-0200",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/2015-06-12-1434137658-3072349-JACOBS_4251300x867_mini-1024x683.jpg",
            "likes": "13"
          }, {
            "name": "Burdock",
            "address": "1184 Bloor Street West",
            "detail": "Toronto Ontario M6H 1N2",
            "no": "(416) 546-4033",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/burdock-brewery-2-1024x683_mini-1024x683.jpg",
            "likes": "7"
          }

        ],
        "Thai": [
          {
            "name": "Soi Thai Street Food",
            "address": "651 College Street",
            "detail": "Toronto Ontario M6G 1B7",
            "no": "(647) 345-8838",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/Soi_mini_mini-1024x608.jpg",
            "likes": "0"
          },
          {
            "name": "Burdock",
            "address": "1184 Bloor Street West",
            "detail": "Toronto Ontario M6H 1N2",
            "no": "(416) 546-4033",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/burdock-brewery-2-1024x683_mini-1024x683.jpg",
            "likes": "7"
          }
        ],
        "Vegan": [{
            "name": "The Hoxton",
            "address": "69 Bathruusrt Street",
            "detail": "Toronto Ontario",
            "no": "(416) 456-7321",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/IMG_0190-45-1200x800-1024x628.jpg",
            "likes": "1"
          },
        ],
        "Coffee & Tea": [
          {
            "name": "The Ritz-Carlton",
            "address": "181 Wellington Streett-W",
            "detail": "Toronto Ontario M5J 2H5",
            "no": "(416) 585-2500",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/RCTORON_00094_conversion-1024x683.jpg",
            "likes": "4"   
          }, {
            "name": "The Drake Hotel",
            "address": "1150 Queen Street West",
            "detail": "Toronto Ontario M6J 1J3",
            "no": "(416)-531-5042",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/Drake-Hotel-Facade-compressor.jpg",
            "likes": "3"
          }
        ],
        "Brunch": [
         {
            "name": "Track and Field Bar",
            "address": "860 College Street",
            "detail": "Toronto Ontario M6H 1A2",
            "no": "(416) 555-1234",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/trackfield-53.jpg",
            "likes": "1" 
          }
        ],
        "Sandwiches": [
          {
            "name": "The Hoxton",
            "address": "69 Bathruusrt Street",
            "detail": "Toronto Ontario",
            "no": "(416) 456-7321",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/IMG_0190-45-1200x800-1024x628.jpg",
            "likes": "1"
          }, {
            "name": "Crocodile Rock",
            "address": "240 Adelaide Street West",
            "detail": "Toronto Ontario M5H 1W7",
            "no": "(416) 599-8751",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/mezz-05.jpg",
            "likes": "6"
          }
        ] ,
        "French": [
          {
            "name": "Track and Field Bar",
            "address": "860 College Street",
            "detail": "Toronto Ontario M6H 1A2",
            "no": "(416) 555-1234",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/trackfield-53.jpg",
            "likes": "1" 
          },{
            "name": "Parts and Labour",
            "address": "1566 Queen Street West",
            "detail": "Toronto Ontario M6R 1A6",
            "no": "(416) 588-7750",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/partsnlabour_nov2010-02.jpg",
            "likes": "2"
          }
        ],
        "Hotels": [
          {
            "name": "Alo Restuarant",
            "address": "163 Spadina Avenue",
            "detail": "Toronto Ontario M5V 2A5",
            "no": "(416) 260-2222",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/toronto-restaurant-alo-optimized-1024x614.jpg",
            "likes": "3"
          }
        ],
        "Landmarks": [
          {
            "name": "Jacobs & Co. Steakhouse",
            "address": "12 Brant Street",
            "detail": "Toronto Ontario M5V 2M1",
            "no": "(416) 366-0200",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/2015-06-12-1434137658-3072349-JACOBS_4251300x867_mini-1024x683.jpg",
            "likes": "13"
          }, {
            "name": "Burdock",
            "address": "1184 Bloor Street West",
            "detail": "Toronto Ontario M6H 1N2",
            "no": "(416) 546-4033",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/burdock-brewery-2-1024x683_mini-1024x683.jpg",
            "likes": "7"
          }

        ],
        "Asian Fusion": [
          {
            "name": "Soi Thai Street Food",
            "address": "651 College Street",
            "detail": "Toronto Ontario M6G 1B7",
            "no": "(647) 345-8838",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/Soi_mini_mini-1024x608.jpg",
            "likes": "0"
          },
          {
            "name": "Burdock",
            "address": "1184 Bloor Street West",
            "detail": "Toronto Ontario M6H 1N2",
            "no": "(416) 546-4033",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/burdock-brewery-2-1024x683_mini-1024x683.jpg",
            "likes": "7"
          }
        ],
        "Doughnuts": [{
            "name": "The Hoxton",
            "address": "69 Bathruusrt Street",
            "detail": "Toronto Ontario",
            "no": "(416) 456-7321",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/IMG_0190-45-1200x800-1024x628.jpg",
            "likes": "1"
          },
        ],
        "Comedy Club": [
         {
            "name": "Track and Field Bar",
            "address": "860 College Street",
            "detail": "Toronto Ontario M6H 1A2",
            "no": "(416) 555-1234",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/trackfield-53.jpg",
            "likes": "1" 
          },{
            "name": "Parts and Labour",
            "address": "1566 Queen Street West",
            "detail": "Toronto Ontario M6R 1A6",
            "no": "(416) 588-7750",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/partsnlabour_nov2010-02.jpg",
            "likes": "2"
          },
          {
            "name": "Crocodile Rock",
            "address": "240 Adelaide Street West",
            "detail": "Toronto Ontario M5H 1W7",
            "no": "(416) 599-8751",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/mezz-05.jpg",
            "likes": "6"
          },
          {
            "name": "Parts and Labour",
            "address": "1566 Queen Street West",
            "detail": "Toronto Ontario M6R 1A6",
            "no": "(416) 588-7750",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/partsnlabour_nov2010-02.jpg",
            "likes": "2"
          }
        ],
        "Nightclub": [
          {
            "name": "The Hoxton",
            "address": "69 Bathruusrt Street",
            "detail": "Toronto Ontario",
            "no": "(416) 456-7321",
            "img": "https://listify-demos.astoundify.com/classic/wp-content/uploads/sites/2/2016/05/IMG_0190-45-1200x800-1024x628.jpg",
            "likes": "1"
          }
        ] 
      },
    };
  },

  methods: {
    showData(category) {
      this.selectedCategory = category;
    },
  },
};
</script>

<style scoped>
.v-btn {
  background-color: #ffffff !important;
  box-shadow: inset 0 0 0 1px #e5e5e5 !important;
  border: 0 !important;
}

.v-btn:hover {
  color: #0f3b88;
}

.card {
  margin-bottom: 20px;
}

.info, .v-card-title{
  text-align: left;
}

.v-container{
  max-width: 100%;
}

.cht{
  max-width: 95%;
}
*{
  margin-left: 0px !important;
}
</style>