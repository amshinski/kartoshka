<template>
    <div class="relative h-screen w-full bg-cover" :style="{ backgroundImage: `url(${backgroundImage})` }">
        <div class="absolute inset-0 bg-yellow-800 bg-opacity-40"></div>
        <div class="relative z-10 flex flex-col items-center justify-center h-full">
            <h1 class="text-white text-8xl font-bold">КАРТОШЕЧКА</h1>
        </div>
        <nav class="absolute top-0 p-6 flex justify-around z-10 w-full">
            <a href="#" class="text-white text-lg">
                <img src="@/img/logo.png" class="w-10"  alt="logo"/>
            </a>
            <div class="space-x-12">
                <a href="#" class="text-white text-lg">Цены</a>
                <a href="#" class="text-white text-lg">Видео</a>
                <a href="#" class="text-white text-lg">О нас</a>
                <a href="#" class="text-white text-lg border border-white rounded-full px-4 py-2">Оставить заявку</a>
            </div>
        </nav>
    </div>

    <div class="flex justify-center items-center relative py-20">
        <img
            @click="move('left')"
            src="@/img/left.svg"
            class="h-16 cursor-pointer select-none absolute left-0"
            style="left: 30%;"
            alt="left" />

        <div v-if="img === 0" class="flex flex-col items-center">
            <h1 class="text-6xl font-bold border-b-8 pb-5 border-amber-400 w-min mb-10">Цены</h1>
            <img src="@/img/karfcar1.png" class="h-52 mb-4 select-none" alt="Столовый картофель" />
            <div class="text-2xl mb-2">Столовый картофель</div>
            <div class="text-amber-500 text-5xl font-light tracking-wider">142 Р</div>
        </div>

        <div v-if="img === 1" class="flex flex-col items-center">
            <h1 class="text-6xl font-bold border-b-8 pb-5 border-amber-400 w-min mb-10">Цены</h1>
            <img src="@/img/karfcar2.png" class="h-52 mb-4 select-none" alt="Деревенский картофель" />
            <div class="text-2xl mb-2">Деревенский картофель</div>
            <div class="text-amber-500 text-5xl font-light tracking-wider">129 Р</div>
        </div>

        <div v-if="img === 2" class="flex flex-col items-center">
            <h1 class="text-6xl font-bold border-b-8 pb-5 border-amber-400 w-min mb-10">Цены</h1>
            <img src="@/img/karfcar3.png" class="h-52 mb-4 select-none" alt="Домашний картофель" />
            <div class="text-2xl mb-2">Домашний картофель</div>
            <div class="text-amber-500 text-5xl font-light tracking-wider">133 Р</div>
        </div>

        <img
            @click="move('right')"
            src="@/img/right.svg"
            class="h-16 cursor-pointer select-none absolute right-0"
            style="right: 30%;"
            alt="right" />
    </div>

    <div class="flex justify-center items-center py-20" style="background-color: #35312d">
        <div class="flex flex-col items-center">
            <h1 class="text-6xl font-bold border-b-8 pb-5 border-amber-400 w-min mb-10 text-white">Видео</h1>
            <video class="mb-10" style="height: 60vh" controls>
                <source src="" type="video/mp4">
                <source src="" type="video/ogg">
                Your browser does not support the video tag.
            </video>
        </div>
    </div>

    <div class="flex justify-center items-center relative mt-16">
        <img src="@/img/blurry_potat.png" alt="" class="h-64 absolute left-20 top-0" />
        <img src="@/img/fine_potat.png" alt="" class="h-96 absolute right-32 -bottom-36" />
        <div class="flex flex-col items-center z-50">
            <h1 class="text-6xl font-bold border-b-8 pb-5 border-amber-400 mb-10">О нас</h1>
            <div class="flex flex-row gap-8">
                <img src="@/img/cook.png" class="w-56" alt="cook" />
                <div class="max-w-80">
                    Если картошка, запеченная в духовке, получается не всегда такой как хочется
                    (сухая или наоборот мокрая, сыроватая внутри, недостаточно удачная по специям)
                    — дайте шанс этому рецепту.
                    <br><br>
                    Такая картошечка по-деревенски стабильно получается очень вкусная, хрустящая
                    снаружи и мягкая, как пюрешка внутри, ароматная — в общем пальчики оближешь.
                    Рецепт у меня простой, но с технологическим секретом, который и решает дело.
                </div>
            </div>
        </div>
    </div>

    <div class="flex justify-center items-center z-50">
        <div
            class="rounded-2xl flex flex-col justify-center items-center p-10 z-50"
            style="background-color: #35312d; min-width: 55vw">
            <div class="text-white text-3xl mb-10">Оставить заявку</div>
            <div class="input-container mb-6">
                <input
                    id="inp1"
                    class="input rounded border px-3 py-2 placeholder-black text-white font-light w-60"
                    style="background-color: #35312d; border-color: #5c554e"
                    placeholder="" />
                <label for="inp2" class="placeholder">Имя</label>
            </div>
            <div class="input-container mb-10">
                <input
                    type="tel"
                    id="inp2"
                    class="input rounded border px-3 py-2 placeholder-black text-white font-light w-60"
                    style="background-color: #35312d; border-color: #5c554e"
                    placeholder=""
                    value="+7 905 299 44 55"/>
                <label for="inp2" class="placeholder">Номер телефона</label>
            </div>
            <button class="bg-amber-400 py-2 px-5 rounded-full text-lg">
                Оставить заявку
            </button>
        </div>
    </div>

    <div class="text-4xl text-center mt-24 font-black mb-4" style="color: #35312d">
        КАРТОШЕЧКА
    </div>

    <div class="flex flex-row gap-4 justify-center mb-16">
        <div class="bg-gray-200 rounded-full p-4 relative">
            <img src="@/img/vk.svg" class="h-3 absolute left-0 right-0 bottom-2.5 ml-auto mr-auto" alt="vk" />
        </div>
        <div class="bg-gray-200 rounded-full p-4 relative">
            <img src="@/img/facebook.svg" class="h-5 absolute left-0 right-0 bottom-1.5 ml-auto mr-auto" alt="facebook" />
        </div>
        <div class="bg-gray-200 rounded-full p-4 relative">
            <img src="@/img/twitter.svg" class="h-4 absolute left-0 right-0 bottom-1.5 ml-auto mr-auto" alt="twitter" />
        </div>
        <div class="bg-gray-200 rounded-full p-4 relative">
            <img src="@/img/inst.svg" class="h-5 absolute left-0 right-0 bottom-1.5 ml-auto mr-auto" alt="instagram" />
        </div>
    </div>

</template>

<script setup>
import {ref} from "vue";
import backgroundImage from './img/img.png';

const img = ref(0);

const move = (direction) => {
    if (direction === 'right') {
        if (img.value === 0 || img.value === 1) {
            img.value++;
        } else {
            img.value = 0;
        }
    } else {
        if (img.value === 1 || img.value === 2) {
            img.value--;
        } else {
            img.value = 2;
        }
    }
}
</script>

<style scoped>
input::placeholder {
    color: #5c554e;
    font-size: .9rem;
}
.input-container {
    position: relative;
    display: inline-block;
}

.input {
    border: 1px solid #ccc;
    padding: 10px;
    font-size: 14px;
    outline: none;
}

.placeholder {
    position: absolute;
    top: 50%;
    left: 10px;
    transform: translateY(-50%);
    transition: all 0.2s ease;
    pointer-events: none;
    color: #5c554e;
    font-size: .9rem;
}

.input:focus + .placeholder,
.input:not(:placeholder-shown) + .placeholder {
    top: 0;
    left: 10px;
    font-size: 12px;
    color: #666;
    background-color: #35312d;
}
</style>
