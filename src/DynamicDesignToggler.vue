<template>
    <div>
        <link href="https://fonts.googleapis.com/css?family=Fira+Code&display=swap" rel="stylesheet">

        <div class="fixed w-full z-50">
        <div class="bg-gray-800 hover:bg-indigo-800 lg:p-4 md:p-2 sm:p-1 flex justify-between items-center transition-colors duration-300 ease-in-out">

            <button @click="toggleDesignPrev"
                class="bg-blue-500 hover:bg-blue-600 text-white font-mono font-semibold md:px-4 md:py-2 px-2 py-1  rounded-full transition-colors duration-300 ease-in-out">
                <transition name="fade" mode="out-in">
                    <span :key="buttonTextprev">{{ buttonTextprev }}</span>
                </transition>
            </button>

            <div class="text-white text-xl font-mono">{{ topicText }}</div>


            <button @click="toggleDesignNext"
                class="bg-blue-500 hover:bg-blue-600 text-white font-mono font-semibold md:px-4 md:py-2 px-2 py-1 rounded-full transition-colors duration-300 ease-in-out">
                <transition name="fade" mode="out-in">
                    <span :key="buttonTextnext">{{ buttonTextnext }}</span>
                </transition>
            </button>
        </div>
        <div class="">
            <div class="flex">
                <div class="w-1/4 h-1 bg-blue-500 duration-500 rounded-full" :style="{ width: part1Width + '%' }"></div>
                <div class="w-1/4 h-1 bg-blue-500 duration-500 rounded-full" :style="{ width: part2Width + '%' }"></div>
                <div class="w-1/4 h-1 bg-blue-500 duration-500 rounded-full" :style="{ width: part3Width + '%' }"></div>
                <div class="w-1/4 h-1 bg-blue-500 duration-500 rounded-full" :style="{ width: part4Width + '%' }"></div>
            </div>
        </div>
    </div>





        <transition name="slide-fade" mode="out-in">
            <component :is="currentComponent" />
        </transition>





    </div>
</template>
  
<script>

import Design1 from './introduction.vue';
import Design2 from './Qualifications.vue';
import Design3 from './Projects.vue';
import Design4 from './Certificates.vue';

export default {
    data() {
        return {
            showDesign1: true,
            showDesign2: false,
            showDesign3: false,
            buttonTextprev: "Achievement & Certificates",
            buttonTextnext: "Education & Experience",
            part1Width: 25,
            part2Width: 0,
            part3Width: 0,
            part4Width: 0,
            currentComponent: Design1,
            topicText: "Rishabh Gupta",
            slideDirection: 100,
        };
    },
    methods: {
        toggleDesignNext() {
            if (this.showDesign1) {
                this.showDesign1 = false;
                this.showDesign2 = true;
                this.buttonTextnext = "Projects";
                this.buttonTextprev = "Introduction";
                this.part2Width = 25;
                this.topicText = "Education & Experience";
                this.currentComponent = Design2;
            } else if (this.showDesign2) {
                this.showDesign2 = false;
                this.showDesign3 = true;
                this.buttonTextnext = "Achievement & Certificates";
                this.buttonTextprev = "Education & Experience";
                this.part3Width = 25;
                this.topicText = "Projects";
                this.currentComponent = Design3;
            } else if (this.showDesign3) {
                this.showDesign3 = false;
                this.buttonTextnext = "Introduction";
                this.buttonTextprev = "Projects";
                this.part4Width = 25;
                this.topicText = "Achievement & Certificates";
                this.currentComponent = Design4;
            } else {
                this.showDesign1 = true;
                this.buttonTextnext = "Introduction";
                this.buttonTextprev = "Achievement & Certificates";
                this.topicText = "Rishabh Gupta";
                this.currentComponent = Design1;
                this.part2Width = 0;
                this.part3Width = 0;
                this.part4Width = 0;
            }
            slideDirection: 100;
        },
        toggleDesignPrev() {
            if (this.showDesign1) {
                this.showDesign1 = false;
                this.showDesign4 = true;
                this.buttonTextnext = "Introduction";
                this.buttonTextprev = "Projects";
                this.topicText = "Achievement & Certificates";
                this.part2Width = 25;
                this.part3Width = 25;
                this.part4Width = 25;
                this.currentComponent = Design4;
            } else if (this.showDesign2) {
                this.showDesign2 = false;
                this.showDesign1 = true;
                this.buttonTextnext = "Introduction";
                this.buttonTextprev = "Achievement & Certificates";
                this.topicText = "Rishabh Gupta";
                this.part2Width = 0;
                this.part3Width = 0;
                this.currentComponent = Design1;
                this.part4Width = 0;
            } else if (this.showDesign3) {
                this.showDesign3 = false;
                this.showDesign2 = true;
                this.buttonTextnext = "Projects";
                this.buttonTextprev = "Introduction";
                this.part2Width = 25;
                this.part3Width = 0;
                this.part4Width = 0;
                this.topicText = "Education & Experience";
                this.currentComponent = Design2;
            } else {
                this.showDesign3 = true;
                this.buttonTextnext = "Achievement & Certificates";
                this.buttonTextprev = "Education & Experience";
                this.topicText = "Projects";
                this.part2Width = 25;
                this.part3Width = 25;
                this.part4Width = 0;
                this.currentComponent = Design3;
            }
            slideDirection: -100;
        },
    },
};
</script>
  
<style>
.fade-enter-active,
.fade-leave-active {
    transition: opacity 1s;
}

.fade-enter,
.fade-leave-to {
    opacity: 0;
}


.font-mono {
    font-family: 'Fira Code', monospace;
}

.link-underline {
    border-bottom-width: 0;
    background-image: linear-gradient(transparent, transparent), linear-gradient(#fff, #fff);
    background-size: 0 3px;
    background-position: 0 100%;
    background-repeat: no-repeat;
    transition: background-size .5s ease-in-out;
}

.link-underline-black {
    background-image: linear-gradient(transparent, transparent), linear-gradient(#F2C, #F2C)
}

.link-underline:hover {
    background-size: 100% 3px;
    background-position: 0 100%
}

.slide-fade-enter-active, .slide-fade-leave-active {
  transition: transform 0.5s;
}
.slide-fade-enter, .slide-fade-leave-to /* .slide-fade-leave-active in <2.1.8 */ {
  transform: translateX(v-bind(slideDirection));
}

</style>
  