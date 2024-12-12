<template>
    <section id="about" class="relative py-20 border-b-2 border-black">
        <div class="mx-auto px-4 ml-56 mr-56">
            <h2 class="text-4xl font-bold text-gray-800 mb-8 text-center">ABOUT ME</h2>
            <span class="bg-black h-1 w-10 block mx-auto mb-32"></span>

            <!-- 创意卡片 -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-32">
                <div v-for="(card, index) in cards" :key="index" class="text-center">
                    <div class="relative group z-10">
                        <!-- 装饰背景：将z-index调低 -->
                        <div
                            class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2 w-[190px] h-[380px] -skew-x-[20deg] transition-colors duration-300 group-hover:bg-[#fffab3] -z-10">
                        </div>

                        <!-- 图标容器 -->
                        <div class="relative w-[140px] h-[150px] mx-auto flex items-center justify-center">
                            <div
                                class="absolute inset-0 border border-[#ffee02] bg-white -skew-x-[20deg] transition-colors duration-300 group-hover:bg-[#ffee02]">
                            </div>
                            <component :is="card.icon" class="relative w-[70px] h-[70px] stroke-[1.5]" />
                        </div>

                        <!-- 内容：增加相对定位和z-index确保在装饰背景之上 -->
                        <div class="relative z-10">
                            <h3 class="mt-12 mb-4 text-2xl font-bold">
                                <span class="text-black">{{ card.title }}</span>
                            </h3>
                            <p class="text-base leading-[30px] text-[#444] mb-8 px-4">{{ card.description }}</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- 技能条部分 -->
            <div class="flex">
                <!-- 图片部分 -->
                <div class="w-1/2 justify-center items-start">
                    <img src="../assets/images/Youz_.png" alt="">
                </div>
                <div class="space-y-4 w-1/2" >
                    <div v-for="skill in skills" :key="skill.name" class="skill-bar">
                        <div class="flex h-7">
                            <div class="w-32 bg-amber-400 flex items-center justify-center">
                                <span class="text-white font-bold">{{ skill.name }}</span>
                            </div>
                            <div class="flex-grow bg-gray-200">
                                <div class="h-full bg-amber-500" :style="{ width: `${skill.level}%` }"></div>
                            </div>
                        </div>
                        <!-- 添加技能描述 -->
                        <p class="text-sm text-gray-600 mt-1 ml-32">{{ skill.description }}</p>
                    </div>
                </div>
            </div>

        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'
import { Rocket, Smartphone, Lightbulb, Sparkles } from 'lucide-vue-next'

const skills = ref([
    {
        name: 'CSS',
        level: 70,
        description: 'Modern CSS3, Flexbox, Grid, Animations'
    },
    {
        name: 'HTML',
        level: 85,
        description: 'Semantic HTML5, Accessibility, SEO'
    },
    {
        name: 'JavaScript',
        level: 80,
        description: 'ES6+, Async/Await, DOM Manipulation'
    },
    {
        name: 'Vue3',
        level: 80,
        description: 'Composition API, Vuex, Vue Router'
    },
    {
        name: 'Node.js',
        level: 70,
        description: 'Express, RESTful APIs, MongoDB'
    }
])

const cards = ref([
    {
        icon: Rocket,
        title: 'Fast',
        description: 'Lightning-fast performance and quick loading times for optimal user experience.',
    },
    {
        icon: Smartphone,
        title: 'Responsive',
        description: 'Fully adaptive designs that work seamlessly across all devices and screen sizes.',
    },
    {
        icon: Lightbulb,
        title: 'Intuitive',
        description: 'User-friendly interfaces with natural, easy-to-understand navigation and controls.',
    },
    {
        icon: Sparkles,
        title: 'Dynamic',
        description: 'Engaging animations and interactive elements that bring your website to life.',
    }
])
</script>

<style scoped>
.skill-bar {
    animation: slideIn 1s ease-out forwards;
}

@keyframes slideIn {
    from {
        transform: translateX(-100%);
        opacity: 0;
    }

    to {
        transform: translateX(0);
        opacity: 1;
    }
}
</style>