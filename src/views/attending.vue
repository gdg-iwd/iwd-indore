<template>
    <v-slide-y-reverse-transition>
        <div>
        <v-container fluid v-show="show" class="mt-3 grey lighten-5" style="border-bottom-right-radius:60%">
            <v-layout wrap align-center justify-center row>
                <v-flex xs12 md10 lg10>
                    <attnedingHome/>
                </v-flex>
            </v-layout>
        </v-container>

        <v-container fluid v-show="show" class="mt-3" style="border-bottom-right-radius:70%">
            <v-layout wrap align-center justify-center row>
                <v-flex xs12 md10 lg10>
                    <attnedingExplore/>
                    <faq/>  
                </v-flex>
            </v-layout>
        </v-container>
        </div>
    </v-slide-y-reverse-transition>
</template>

<script>

import faq from '@/components/faq'
import attnedingHome from '@/components/attending/attendingHome'
import attnedingExplore from '@/components/attending/attendingExplore'

export default {
    components:{
        faq,
        attnedingHome,
        attnedingExplore,
    },
    data() {
        return {
            show:false,
            imgPath:{
                src: require('@/assets/img/bg.jpg')
            }
        }
    },
    created(){
        this.show = true
    }
}
</script>
