<script setup>
import {faker} from '@faker-js/faker'

const firstName = faker.name.firstName()
const lastName = faker.name.lastName()
const fullName = `${firstName} ${lastName}`

const selectCard = () => {
    console.log(`${fullName} selected`)
}
</script>

<template>
    <div class="card" @click="selectCard">
        <div class="card-image">
    <img :src="faker.internet.avatar()" alt="" srcset="" />
        </div>
        <div class="card-details"> 
    <p class="card-details-name">{{ fullName }}</p>
    <p class="card-details-job">{{  faker.name.jobTitle() }}, {{ faker.name.jobArea() }}</p>
    <p class="card-details=email">{{ faker.internet.exampleEmail(firstName, lastName) }}</p>
    <p class="card-details-quote">"{{  faker.lorem.paragraph() }}"</p>
        </div>
    </div>
</template>

<style scoped lang="postcss">
    .card {
        @apply cursor-pointer overflow-hidden rounded-md bg-white p-8 shadow-md hover:scale-110 transition-transform duration-300 hover:shadow-blue-500;
        &-image {
            img {
            @apply mx-auto rounded-full object-contain; 
            }
        }
        &-details {
            @apply flex flex-col gap-4 pt-6 text-center;
            &-name {
                @apply text-2xl font-bold text-teal-600;
            }
            &-job {
                @apply text-slate-700;
            }
            &-email {
                @apply text-slate-700;
            }
            &-quote {
                @apply text-slate-700 italic font-semibold;
            }
        }
    }
</style>