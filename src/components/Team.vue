<template>
    <section class="team-area pt-100 section-padding fix" id="team">
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <div class="section-title text-center">
                        <div class="title-icon"></div>
                        <h2 class="title">Team </h2>
                        <!--<p class="paragraph">Das Team hinter dem Forum Offene Stadt.</p>-->
                    </div>
                </div>
            </div>
        </div>

        <div class="team-member-inner" :style="bgImg">
            <div class="container">
                <div class="row">
                    <div class="col-12">
                        <div class="team-content text-center">
                           <!-- <p>Claritas est etiam processus dynamicus, qui sequitur mutationem consuetudium lectorum. Mirum est notare quam littera gothica, quam nunc putamus parum claram, anteposuerit litterarum formas humanitatis per seacula quarta decima et quinta decima.</p>-->
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="team-member-slider">
            <div class="container">
                <div class="row">
                    <div class="col-12">
                        <carousel class="team-carousel"
                            :item = "6"
                            :nav = "false"
                            :dots = "false"
                            :autoplay = "true"
                            :smartSpeed = "1000"
                            :responsive="{0:{items:1},576:{items:2},768:{items:3}}"
                        >
                            <div v-for="(team, teams) in teams" :key="teams" class="team-member">
                                <div class="member-thumb">
                                    <img :src="team.thumb" alt="team thumb" style="filter: grayscale(100%)" >
                                    <div class="member-content">
                                        <h6 class="title">{{ team.title }}</h6>
                                        <p class="designation">{{ team.designation }}</p>
                                    </div>
                                </div>
                            </div>
                        </carousel>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import carousel from 'vue-owl-carousel'

export default {
    name: 'Team',
    components: {
        carousel 
    },
    data (){
        return {
            teams:[
                {title: "Claudia Jach", designation: "Open Knowledge Foundation DE e.V.", thumb: require("../assets/img/team/claudia.jpg")},
                {title: "Timo Lundelius", designation: "Code for Hamburg e.V.", thumb: require("../assets/img/team/timo.jpg")},
                {title: "Adriana Groh", designation: "Open Knowledge Foundation DE e.V.", thumb: require("../assets/img/team/adriana.jpg")},
                //{title: "Sven Tetzlaff", designation: "Körber-Stiftung", thumb: require("../assets/img/team/sven.jpg")},
                //{title: "Michael Peters", designation: "Open Knowledge Foundation DE e.V.", thumb: require("../assets/img/team/michael.jpg")},
                //{title: "Julia Thomaschki", designation: "Code for Hamburg e.V.", thumb: require("../assets/img/team/julia.jpg")},
                {title: "Hannes Hasenpatt", designation: "Körber-Stiftung", thumb: require("../assets/img/team/hannes2.jpg")},
                {title: "Feena Fensky", designation: "Code for Hamburg e.V.", thumb: require("../assets/img/team/feena.jpg")},
                {title: "Natalia Brühl", designation: "Körber-Stiftung", thumb: require("../assets/img/team/natalia.jpg")},
                //{title: "Christian Wittig", designation: "Code for Hamburg e.V.", thumb: require("../assets/img/team/christian.jpg")},
                {title: "Sina Droste", designation: "Körber-Stiftung", thumb: require("../assets/img/team/sina.jpg")}
            ],
            bgImg: {
                backgroundImage: `url(${require('../assets/img/slider/2.jpg')})`
            }
        }
    }
}
</script>

<style lang="scss">
    @import '../assets/scss/variables.scss';
    @import '../assets/scss/components/team.scss';
</style>
