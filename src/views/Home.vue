<template>
    <div class="home">
        <HelloWorld msg="Welcome to Your Vue.js App"/>
        <b-container>
            <!--
                        LA VIDEO
            -->
            <b-col cols="12" md="10" class="m-auto">
                <video-player class="video-player-box"
                              ref="videoPlayer"
                              :options="playerOptions"
                              :playsinline="true"
                              customEventName="customstatechangedeventname"

                              @play="onPlayerPlay($event)"
                              @pause="onPlayerPause($event)"
                              @ended="onPlayerEnded($event)"
                              @waiting="onPlayerWaiting($event)"
                              @playing="onPlayerPlaying($event)"
                              @loadeddata="onPlayerLoadeddata($event)"
                              @timeupdate="onPlayerTimeupdate($event)"
                              @canplay="onPlayerCanplay($event)"
                              @canplaythrough="onPlayerCanplaythrough($event)"

                              @statechanged="playerStateChanged($event)"
                              @ready="playerReadied">
                </video-player>
            </b-col>
            <!--
                        CTA QUI RENVOIE VERS UN AUTRE BLOC
            -->
            <b-button variant="outline-primary"
                      class="m-3"
                      v-on:click="equipe">Notre équipe
            </b-button>

            <!--
                        BLOC TEXTE AVEC ILLUSTRATION
            -->

            <div class="mt-5">

                <b-card
                        title="Tout les chats ne sont pas gris"
                        tag="article"
                        style="max-width: 20rem;"
                        class="m-auto"
                >
                    <b-card-text>
                        Preuve que tout les chats ne sont pas gris
                    </b-card-text>

                </b-card>
                <b-row class="mt-5 mb-5">
                    <b-col cols="12" md="5" class="m-auto">
                        <img class="img-fluid" src="../assets/poisson.jpg" alt="">
                    </b-col>
                    <b-col cols="12" md="5" class="m-auto">
                        <img class="img-fluid" src="../assets/pas_poisson.jpg" alt="">
                    </b-col>
                </b-row>
            </div>
            <!--
                        LA CARTE
            -->
            <h1>Une carte</h1>
            <GmapMap
                    :center="{lat:48, lng:2}"
                    :zoom="7"
                    map-type-id="terrain"
            >
                <GmapMarker
                        :key="index"
                        v-for="(m, index) in markers"
                        :position="m.position"
                        :clickable="true"
                        :draggable="true"
                        @click="center=m.position"
                />
            </GmapMap>
        </b-container>
        <!--
        FORMULAIRE D'INSCRIPTION
        -->
        <b-container>
            <b-row>
                <b-col cols="12" md="8" class="m-auto">
                    <inscription class="mt-5"></inscription>
                    <contact>a</contact>
                </b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script>
    // @ is an alias to /src
    import HelloWorld from '@/components/HelloWorld.vue'

    import 'video.js/dist/video-js.css'
    import {videoPlayer} from 'vue-video-player'

    import inscription from "@/components/inscription";
    import contact from "@/components/contact";

    export default {
        name: 'Home',
        components: {
            HelloWorld,
            videoPlayer,
            inscription,
            contact
        },
        data() {
            return {
                playerOptions: {
                    // videojs options
                    muted: true,
                    language: 'en',
                    playbackRates: [0.7, 1.0, 1.5, 2.0],
                    sources: [{
                        type: "video/mp4",
                        src: "https://cdn.theguardian.tv/webM/2015/07/20/150716YesMen_synd_768k_vp8.webm"
                    }],
                    poster: "/static/images/author.jpg",
                },
            }

        },
        mounted() {
            console.log('this is current player instance object', this.player)
        },
        computed: {
            player() {
                return this.$refs.videoPlayer.player
            }
        },
        methods: {
            /*    // listen event
                onPlayerPlay(player) {
                  // console.log('player play!', player)
                },
                onPlayerPause(player) {
                  // console.log('player pause!', player)
                },
                // ...player event

                // or listen state event
                playerStateChanged(playerCurrentState) {
                  // console.log('player current update state', playerCurrentState)
                },*/

            // player is ready
            playerReadied(player) {
                console.log('the player is readied', player)
                // you can use it to do something...
                // player.[methods]
            },
            equipe() {
                window.open("/#/about")
            },
        }


    }
</script>

<style>
    .vue-map-container {
        /*
                width: 100vw;
        */
        height: 50vh;
    }

    .vjs_video_3-dimensions {
        width: 100% !important;
    }
</style>
