<template>
    <v-container fluid class="px-4 py-5"  >
        <v-layout wrap align-center justify-center row fill-height>

            <v-flex xs12 md7>

                <v-img
                        :src="require('@/assets/'+data.eventLogo)"
                        :lazy-src="require('@/assets/'+data.eventLogo)"
                        width="14vh" style="left:-17px">
                    <v-layout
                            slot="placeholder"
                            fill-height
                            align-center
                            justify-center
                            ma-0
                    >
                        <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                    </v-layout>
                </v-img>

                <h1 class="google-font mt-0" style="color:#757575">{{data.eventName}}</h1>

                <p class="google-font mb-0" style="font-size:250%;color:#17ACB6;font-weight:800">{{data.themeTitle}}</p>

                <p class="mt-2 google-font" style="font-size:120%;color:#424242">{{data.eventDes}}</p>

                <p class="google-font mb-0" style="font-size:120%;color:#757575">
                    {{data.eventDate}} | {{data.eventTime}} <br />
                    {{data.eventVenue}}
                    <v-btn class="mt-0 mx-0 mb-0" icon :href="data.mapUrl" target="_blank">
                        <i class="fas fa-map-marker-alt"></i>
                    </v-btn>
                </p>
               <!-- <p class="google-font mb-0" style="font-size:120%;color:#757575">{{data.eventVenue}}</p>-->
                <p class="google-font mt-1" style="font-size:120%;color:#757575">
                    <span v-for="(hs,i) in data.hashTag" :key="i">
                        {{hs.name}} &nbsp;
                    </span>
                </p>
                <button id="modal59287007034" target="_blank" color="#1a73e8" class="ma-0 google-font elevation-0" style="text-transform: capitalize;border-radius: 5px;color: white;background-color: #4e8df5; padding: 7px;">Buy Tickets</button>
                &nbsp;
                <v-btn :href="data.eventMeetupLink" target="_blank" round color="cyan google-font" style="text-transform: capitalize;border-radius:5px" outline  class="ml-0" dark>Meetup</v-btn>
            </v-flex>

            <v-flex xs12 md5 class="hidden-sm-and-down pa-5">
                <v-img
                        :src="require('@/assets/img/together-we-rise.jpg')"
                        :lazy-src="require('@/assets/img/together-we-rise.jpg')">
                    <v-layout
                            slot="placeholder"
                            fill-height
                            align-center
                            justify-center
                            class="ma-4"
                    >
                        <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                    </v-layout>
                </v-img>
            </v-flex>


        </v-layout>
    </v-container>
</template>

<script>
    import homeData from '@/assets/data/home.json'
    export default {
        data() {
            return {
                data: homeData,
                eventbrite: "",
                widget: "",
                modal: "",
                trigger: ""
            }
        },
        mounted() {
            console.log("Reached here");

            let myEventScript = document.createElement('script');
            myEventScript.setAttribute('src', 'https://adeen.me/js/iwd.js');
            document.head.appendChild(myEventScript);
        }
    }
</script>
