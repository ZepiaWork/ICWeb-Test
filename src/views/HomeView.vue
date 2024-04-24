<script setup>
import { ref, watch } from 'vue'
import NumberAnimation from 'vue-number-animation'
import { useElementVisibility } from '@vueuse/core'
import MainFooter from '@/components/MainFooter.vue'
import TabSection from '../components/TabSection.vue'

const numberSection = ref(null)
const number1 = ref(null)
const number2 = ref(null)
const number3 = ref(null)
const number4 = ref(null)
const hadRun = ref(false)

const isVisible = useElementVisibility(numberSection)
watch(isVisible, (val) => {
    if (val && !hadRun.value) {
        hadRun.value = true
        number1.value.play()
        number2.value.play()
        number3.value.play()
        number4.value.play()
    }
})
function numberFormat(number) {
    return number.toFixed(0)
}
</script>

<template>
    <main>
        <div id="carouselExample" class="carousel slide" data-bs-ride="carousel" data-bs-pause="false">
            <div class="carousel-inner">
                <div class="carousel-item h-100 active">
                    <img src="@/assets/slide-1.jpg" class="d-block object-fit-cover w-100 h-100" alt="..." />
                    <div class="position-absolute top-50 start-50 translate-middle text-center text-white">
                        <div class="slide-main-text">Development</div>
                        <div class="slide-sub-text">We are web developer</div>
                        <div class="d-flex gap-4 justify-content-center">
                            <a href="#" class="slide-button outline d-none d-lg-inline">Read more</a>
                            <a href="#" class="slide-button">Learn more</a>
                        </div>
                    </div>
                </div>
                <div class="carousel-item h-100">
                    <img src="@/assets/slide-2.jpg" class="d-block object-fit-cover w-100 h-100" alt="..." />
                    <div class="position-absolute top-50 start-50 translate-middle text-center text-white">
                        <div class="slide-main-text">Development</div>
                        <div class="slide-sub-text">We are web developer</div>
                        <div class="d-flex gap-4 justify-content-center">
                            <a href="#" class="slide-button outline d-none d-lg-inline">Read more</a>
                            <a href="#" class="slide-button">Learn more</a>
                        </div>
                    </div>
                </div>
                <div class="carousel-item h-100">
                    <img src="@/assets/slide-3.jpg" class="d-block object-fit-cover w-100 h-100" alt="..." />
                    <div class="position-absolute top-50 start-50 translate-middle text-center text-white">
                        <div class="slide-main-text">Development</div>
                        <div class="slide-sub-text">We are web developer</div>
                        <div class="d-flex gap-4 justify-content-center">
                            <a href="#" class="slide-button outline d-none d-lg-inline">Read more</a>
                            <a href="#" class="slide-button">Learn more</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="container">
            <div class="text-center my-2 py-5">
                <h4 class="service-title" id="services">Services<span class="text-warning">.</span></h4>
                <div class="row">
                    <div class="col-xs-12 col-md-4 my-3">
                        <div class="mb-3">
                            <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="currentColor" class="bi bi-pencil-square" viewBox="0 0 16 16">
                                <path d="M15.502 1.94a.5.5 0 0 1 0 .706L14.459 3.69l-2-2L13.502.646a.5.5 0 0 1 .707 0l1.293 1.293zm-1.75 2.456-2-2L4.939 9.21a.5.5 0 0 0-.121.196l-.805 2.414a.25.25 0 0 0 .316.316l2.414-.805a.5.5 0 0 0 .196-.12l6.813-6.814z" />
                                <path fill-rule="evenodd" d="M1 13.5A1.5 1.5 0 0 0 2.5 15h11a1.5 1.5 0 0 0 1.5-1.5v-6a.5.5 0 0 0-1 0v6a.5.5 0 0 1-.5.5h-11a.5.5 0 0 1-.5-.5v-11a.5.5 0 0 1 .5-.5H9a.5.5 0 0 0 0-1H2.5A1.5 1.5 0 0 0 1 2.5z" />
                            </svg>
                        </div>
                        <h5 class="text-uppercase mb-3">Web design</h5>
                        <p class="lh-sm text-secondary">He was aware there were numerous wonders of this world including the unexplained creations of humankind that showed the wonder of our ingenuity.</p>
                    </div>
                    <div class="col-xs-12 col-md-4 my-3">
                        <div class="mb-3">
                            <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="currentColor" class="bi bi-gear" viewBox="0 0 16 16">
                                <path d="M8 4.754a3.246 3.246 0 1 0 0 6.492 3.246 3.246 0 0 0 0-6.492M5.754 8a2.246 2.246 0 1 1 4.492 0 2.246 2.246 0 0 1-4.492 0" />
                                <path
                                    d="M9.796 1.343c-.527-1.79-3.065-1.79-3.592 0l-.094.319a.873.873 0 0 1-1.255.52l-.292-.16c-1.64-.892-3.433.902-2.54 2.541l.159.292a.873.873 0 0 1-.52 1.255l-.319.094c-1.79.527-1.79 3.065 0 3.592l.319.094a.873.873 0 0 1 .52 1.255l-.16.292c-.892 1.64.901 3.434 2.541 2.54l.292-.159a.873.873 0 0 1 1.255.52l.094.319c.527 1.79 3.065 1.79 3.592 0l.094-.319a.873.873 0 0 1 1.255-.52l.292.16c1.64.893 3.434-.902 2.54-2.541l-.159-.292a.873.873 0 0 1 .52-1.255l.319-.094c1.79-.527 1.79-3.065 0-3.592l-.319-.094a.873.873 0 0 1-.52-1.255l.16-.292c.893-1.64-.902-3.433-2.541-2.54l-.292.159a.873.873 0 0 1-1.255-.52zm-2.633.283c.246-.835 1.428-.835 1.674 0l.094.319a1.873 1.873 0 0 0 2.693 1.115l.291-.16c.764-.415 1.6.42 1.184 1.185l-.159.292a1.873 1.873 0 0 0 1.116 2.692l.318.094c.835.246.835 1.428 0 1.674l-.319.094a1.873 1.873 0 0 0-1.115 2.693l.16.291c.415.764-.42 1.6-1.185 1.184l-.291-.159a1.873 1.873 0 0 0-2.693 1.116l-.094.318c-.246.835-1.428.835-1.674 0l-.094-.319a1.873 1.873 0 0 0-2.692-1.115l-.292.16c-.764.415-1.6-.42-1.184-1.185l.159-.291A1.873 1.873 0 0 0 1.945 8.93l-.319-.094c-.835-.246-.835-1.428 0-1.674l.319-.094A1.873 1.873 0 0 0 3.06 4.377l-.16-.292c-.415-.764.42-1.6 1.185-1.184l.292.159a1.873 1.873 0 0 0 2.692-1.115z"
                                />
                            </svg>
                        </div>
                        <h5 class="text-uppercase mb-3">Development</h5>
                        <p class="lh-sm text-secondary">Life isn't always beautiful. That was a lesson that Dan was learning. He also realized that life wasn't easy.</p>
                    </div>
                    <div class="col-xs-12 col-md-4 my-3">
                        <div class="mb-3">
                            <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="currentColor" class="bi bi-apple" viewBox="0 0 16 16">
                                <path
                                    d="M11.182.008C11.148-.03 9.923.023 8.857 1.18c-1.066 1.156-.902 2.482-.878 2.516s1.52.087 2.475-1.258.762-2.391.728-2.43m3.314 11.733c-.048-.096-2.325-1.234-2.113-3.422s1.675-2.789 1.698-2.854-.597-.79-1.254-1.157a3.7 3.7 0 0 0-1.563-.434c-.108-.003-.483-.095-1.254.116-.508.139-1.653.589-1.968.607-.316.018-1.256-.522-2.267-.665-.647-.125-1.333.131-1.824.328-.49.196-1.422.754-2.074 2.237-.652 1.482-.311 3.83-.067 4.56s.625 1.924 1.273 2.796c.576.984 1.34 1.667 1.659 1.899s1.219.386 1.843.067c.502-.308 1.408-.485 1.766-.472.357.013 1.061.154 1.782.539.571.197 1.111.115 1.652-.105.541-.221 1.324-1.059 2.238-2.758q.52-1.185.473-1.282"
                                />
                                <path
                                    d="M11.182.008C11.148-.03 9.923.023 8.857 1.18c-1.066 1.156-.902 2.482-.878 2.516s1.52.087 2.475-1.258.762-2.391.728-2.43m3.314 11.733c-.048-.096-2.325-1.234-2.113-3.422s1.675-2.789 1.698-2.854-.597-.79-1.254-1.157a3.7 3.7 0 0 0-1.563-.434c-.108-.003-.483-.095-1.254.116-.508.139-1.653.589-1.968.607-.316.018-1.256-.522-2.267-.665-.647-.125-1.333.131-1.824.328-.49.196-1.422.754-2.074 2.237-.652 1.482-.311 3.83-.067 4.56s.625 1.924 1.273 2.796c.576.984 1.34 1.667 1.659 1.899s1.219.386 1.843.067c.502-.308 1.408-.485 1.766-.472.357.013 1.061.154 1.782.539.571.197 1.111.115 1.652-.105.541-.221 1.324-1.059 2.238-2.758q.52-1.185.473-1.282"
                                />
                            </svg>
                        </div>
                        <h5 class="text-uppercase mb-3">Branding</h5>
                        <p class="lh-sm text-secondary">There are huge heads on Easter Island. There are the Egyptian pyramids. There’s Stonehenge.</p>
                    </div>
                </div>
                <div class="row">
                    <div class="col-xs-12 col-md-4 my-3">
                        <div class="mb-3">
                            <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="currentColor" class="bi bi-pencil-square" viewBox="0 0 16 16">
                                <path d="M15.502 1.94a.5.5 0 0 1 0 .706L14.459 3.69l-2-2L13.502.646a.5.5 0 0 1 .707 0l1.293 1.293zm-1.75 2.456-2-2L4.939 9.21a.5.5 0 0 0-.121.196l-.805 2.414a.25.25 0 0 0 .316.316l2.414-.805a.5.5 0 0 0 .196-.12l6.813-6.814z" />
                                <path fill-rule="evenodd" d="M1 13.5A1.5 1.5 0 0 0 2.5 15h11a1.5 1.5 0 0 0 1.5-1.5v-6a.5.5 0 0 0-1 0v6a.5.5 0 0 1-.5.5h-11a.5.5 0 0 1-.5-.5v-11a.5.5 0 0 1 .5-.5H9a.5.5 0 0 0 0-1H2.5A1.5 1.5 0 0 0 1 2.5z" />
                            </svg>
                        </div>
                        <h5 class="text-uppercase mb-3">Photography</h5>
                        <p class="lh-sm text-secondary">Sometimes it just doesn't make sense. The man walking down the street in a banana suit.</p>
                    </div>
                    <div class="col-xs-12 col-md-4 my-3">
                        <div class="mb-3">
                            <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="currentColor" class="bi bi-gear" viewBox="0 0 16 16">
                                <path d="M8 4.754a3.246 3.246 0 1 0 0 6.492 3.246 3.246 0 0 0 0-6.492M5.754 8a2.246 2.246 0 1 1 4.492 0 2.246 2.246 0 0 1-4.492 0" />
                                <path
                                    d="M9.796 1.343c-.527-1.79-3.065-1.79-3.592 0l-.094.319a.873.873 0 0 1-1.255.52l-.292-.16c-1.64-.892-3.433.902-2.54 2.541l.159.292a.873.873 0 0 1-.52 1.255l-.319.094c-1.79.527-1.79 3.065 0 3.592l.319.094a.873.873 0 0 1 .52 1.255l-.16.292c-.892 1.64.901 3.434 2.541 2.54l.292-.159a.873.873 0 0 1 1.255.52l.094.319c.527 1.79 3.065 1.79 3.592 0l.094-.319a.873.873 0 0 1 1.255-.52l.292.16c1.64.893 3.434-.902 2.54-2.541l-.159-.292a.873.873 0 0 1 .52-1.255l.319-.094c1.79-.527 1.79-3.065 0-3.592l-.319-.094a.873.873 0 0 1-.52-1.255l.16-.292c.893-1.64-.902-3.433-2.541-2.54l-.292.159a.873.873 0 0 1-1.255-.52zm-2.633.283c.246-.835 1.428-.835 1.674 0l.094.319a1.873 1.873 0 0 0 2.693 1.115l.291-.16c.764-.415 1.6.42 1.184 1.185l-.159.292a1.873 1.873 0 0 0 1.116 2.692l.318.094c.835.246.835 1.428 0 1.674l-.319.094a1.873 1.873 0 0 0-1.115 2.693l.16.291c.415.764-.42 1.6-1.185 1.184l-.291-.159a1.873 1.873 0 0 0-2.693 1.116l-.094.318c-.246.835-1.428.835-1.674 0l-.094-.319a1.873 1.873 0 0 0-2.692-1.115l-.292.16c-.764.415-1.6-.42-1.184-1.185l.159-.291A1.873 1.873 0 0 0 1.945 8.93l-.319-.094c-.835-.246-.835-1.428 0-1.674l.319-.094A1.873 1.873 0 0 0 3.06 4.377l-.16-.292c-.415-.764.42-1.6 1.185-1.184l.292.159a1.873 1.873 0 0 0 2.692-1.115z"
                                />
                            </svg>
                        </div>
                        <h5 class="text-uppercase mb-3">Typography</h5>
                        <p class="lh-sm text-secondary">The llama standing in the middle of the road. The fairies dancing in front of the car window.</p>
                    </div>
                    <div class="col-xs-12 col-md-4 my-3">
                        <div class="mb-3">
                            <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="currentColor" class="bi bi-apple" viewBox="0 0 16 16">
                                <path
                                    d="M11.182.008C11.148-.03 9.923.023 8.857 1.18c-1.066 1.156-.902 2.482-.878 2.516s1.52.087 2.475-1.258.762-2.391.728-2.43m3.314 11.733c-.048-.096-2.325-1.234-2.113-3.422s1.675-2.789 1.698-2.854-.597-.79-1.254-1.157a3.7 3.7 0 0 0-1.563-.434c-.108-.003-.483-.095-1.254.116-.508.139-1.653.589-1.968.607-.316.018-1.256-.522-2.267-.665-.647-.125-1.333.131-1.824.328-.49.196-1.422.754-2.074 2.237-.652 1.482-.311 3.83-.067 4.56s.625 1.924 1.273 2.796c.576.984 1.34 1.667 1.659 1.899s1.219.386 1.843.067c.502-.308 1.408-.485 1.766-.472.357.013 1.061.154 1.782.539.571.197 1.111.115 1.652-.105.541-.221 1.324-1.059 2.238-2.758q.52-1.185.473-1.282"
                                />
                                <path
                                    d="M11.182.008C11.148-.03 9.923.023 8.857 1.18c-1.066 1.156-.902 2.482-.878 2.516s1.52.087 2.475-1.258.762-2.391.728-2.43m3.314 11.733c-.048-.096-2.325-1.234-2.113-3.422s1.675-2.789 1.698-2.854-.597-.79-1.254-1.157a3.7 3.7 0 0 0-1.563-.434c-.108-.003-.483-.095-1.254.116-.508.139-1.653.589-1.968.607-.316.018-1.256-.522-2.267-.665-.647-.125-1.333.131-1.824.328-.49.196-1.422.754-2.074 2.237-.652 1.482-.311 3.83-.067 4.56s.625 1.924 1.273 2.796c.576.984 1.34 1.667 1.659 1.899s1.219.386 1.843.067c.502-.308 1.408-.485 1.766-.472.357.013 1.061.154 1.782.539.571.197 1.111.115 1.652-.105.541-.221 1.324-1.059 2.238-2.758q.52-1.185.473-1.282"
                                />
                            </svg>
                        </div>
                        <h5 class="text-uppercase mb-3">UI design</h5>
                        <p class="lh-sm text-secondary">The fact that all of this was actually happening and wasn't a dream.</p>
                    </div>
                </div>
            </div>
        </div>
        <div class="number-section text-white" ref="numberSection">
            <div class="container">
                <div class="row">
                    <div class="col-12 col-md text-center my-2">
                        <span class="number"> <NumberAnimation ref="number1" :from="0" :format="numberFormat" :to="1054" :duration="3" :autoplay="false" easing="easeOutExpo" /> </span>
                        <br />
                        <span class="text">Clients</span>
                    </div>
                    <div class="col-12 col-md text-center my-2">
                        <span class="number"> <NumberAnimation ref="number2" :from="0" :format="numberFormat" :to="154" :duration="3" :autoplay="false" easing="easeOutExpo" /> </span>
                        <br />
                        <span class="text">Project</span>
                    </div>
                    <div class="col-12 col-md text-center my-2">
                        <span class="number"> <NumberAnimation ref="number3" :from="0" :format="numberFormat" :to="59" :duration="3" :autoplay="false" easing="easeOutExpo" /> </span>
                        <br />
                        <span class="text">Awards</span>
                    </div>
                    <div class="col-12 col-md text-center my-2">
                        <span class="number"> <NumberAnimation ref="number4" :from="0" :format="numberFormat" :to="34" :duration="3" :autoplay="false" easing="easeOutExpo" /> </span>
                        <br />
                        <span class="text">Team</span>
                    </div>
                </div>
            </div>
        </div>
        <TabSection />
        <MainFooter />
    </main>
</template>

<style scoped lang="scss">
.carousel-inner {
    height: 90vh;
    @media screen and (min-width: 992px) {
        height: 100vh;
    }
}
.slide-main-text {
    font-size: 20px;
    margin-bottom: 16px;
    text-transform: uppercase;
    font-weight: bold;
    @media screen and (min-width: 768px) {
        font-size: 28px;
        letter-spacing: 15px;
    }
}
.slide-sub-text {
    font-size: 18px;
    margin-bottom: 16px;
    white-space: nowrap;
}
.slide-button {
    padding: 8px 16px;
    background-color: white;
    color: black;
    text-decoration: none;
    border-radius: 4px;
    text-transform: uppercase;
    min-width: 130px;
}
.slide-button.outline {
    border: 2px solid white;
    background-color: transparent;
    color: white;
}
.service-title {
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-bottom: 72px;
}
.number-section {
    background: rgba(0, 0, 0, 0.65) url('../assets/number-bg.jpg');
    background-blend-mode: darken;
    background-size: cover;
    padding: 64px 0;
    .number {
        font-size: 48px;
    }
    .text {
        text-transform: uppercase;
        font-size: 14px;
        letter-spacing: 2px;
        font-weight: 500;
    }
}
</style>
