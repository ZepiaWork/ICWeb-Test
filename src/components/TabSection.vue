<script setup>
import { ref, computed } from 'vue'
const dataList = ref([
    {
        imageUrl: '/tab-image/tab1.jpg',
        key: 'photo',
        name: 'img1'
    },
    {
        imageUrl: '/tab-image/tab2.jpg',
        key: 'photo',
        name: 'img2'
    },
    {
        imageUrl: '/tab-image/tab3.jpg',
        key: 'branding',
        name: 'img3'
    },
    {
        imageUrl: '/tab-image/tab4.jpg',
        key: 'branding',
        name: 'img4'
    },
    {
        imageUrl: '/tab-image/tab5.jpg',
        key: 'design',
        name: 'img5'
    },
    {
        imageUrl: '/tab-image/tab6.jpg',
        key: 'design',
        name: 'img6'
    },
    {
        imageUrl: '/tab-image/tab7.jpg',
        key: 'coffee',
        name: 'img7'
    },
    {
        imageUrl: '/tab-image/tab8.jpg',
        key: 'coffee',
        name: 'img8'
    }
])
const filterText = ref('')

const filteredData = computed(() => {
    let out = []
    if (filterText.value == '') return dataList.value
    for (let index = 0; index < dataList.value.length; index++) {
        const element = dataList.value[index]
        if (element.key == filterText.value) out.push(element)
    }
    return out
})

function clickTab(val) {
    filterText.value = val
}
</script>

<template>
    <div class="text-center" id="great-work">
        <h4 class="section-title">Great work<span class="text-warning">.</span></h4>
        <div class="d-flex gap-3 gap-md-4 justify-content-center mb-4">
            <div class="tab-title" :class="{ active: filterText == '' }" @click="clickTab('')">All</div>
            <div class="tab-title" :class="{ active: filterText == 'branding' }" @click="clickTab('branding')">Branding</div>
            <div class="tab-title" :class="{ active: filterText == 'design' }" @click="clickTab('design')">Design</div>
            <div class="tab-title" :class="{ active: filterText == 'photo' }" @click="clickTab('photo')">Photo</div>
            <div class="tab-title" :class="{ active: filterText == 'coffee' }" @click="clickTab('coffee')">Coffee</div>
        </div>
        <div class="grid-layout">
            <TransitionGroup name="fade">
                <div v-for="element in filteredData" :key="element.name" class="tab-element">
                    <img class="tab-image" :src="element.imageUrl" />
                </div>
            </TransitionGroup>
        </div>
    </div>
</template>

<style scoped lang="scss">
.section-title {
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-bottom: 32px;
    margin-top: 64px;
}
.tab-title {
    cursor: pointer;
    font-weight: 500;
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 1px;
    transition: color 0.4s;
    &.active {
        color: #dbac3b;
    }
    @media screen and (min-width: 768px) {
        font-size: 14px;
        letter-spacing: 4px;
    }
}
.grid-layout {
    display: flex;
    // grid-template-columns: 1fr 1fr 1fr 1fr;
    flex-flow: wrap;
    position: relative;
    .tab-element {
        aspect-ratio: 16/9;
        width: 100%;
        @media screen and (min-width: 768px) {
            width: 50%;
        }
        @media screen and (min-width: 992px) {
            width: 25%;
        }
        .tab-image {
            object-fit: cover;
            width: 100%;
            height: 100%;
        }
    }
}
.fade-move,
.fade-enter-active,
.fade-leave-active {
    transition: all 0.5s ease;
}
.fade-enter-from,
.fade-leave-to {
    opacity: 0;
    transform: scale(0);
}
.fade-leave-active {
    position: absolute;
}
</style>
