<template>
    <BreezeGuestLayout>
        <Head title="Landing" />
        <h1 class="text-3xl text-center">Impii Connected Protection</h1>
        <BreezeValidationErrors class="mb-4" />
        <br>
        <div>
            <div >
                <button class="w-full h-12 px-6 text-indigo-100 mt-2 transition-colors duration-150 bg-black rounded-lg focus:shadow-outline hover:bg-indigo-800">Log in</button>
                <br>
                <button class="w-full h-12 px-6 text-indigo-100 mt-2 transition-colors duration-150 bg-impii rounded-lg focus:shadow-outline hover:bg-indigo-800">Register</button>
                <br>
                <button class="w-full h-12 px-6 text-indigo-100 mt-2 transition-colors duration-150 bg-red-500 rounded-lg focus:shadow-outline hover:bg-indigo-800">S.O.S</button>
            </div>

        </div>

    </BreezeGuestLayout>
</template>

<script setup>

import BreezeGuestLayout from '@/Layouts/Guest.vue';
import BreezeValidationErrors from '@/Components/ValidationErrors.vue';
import { Head, useForm } from '@inertiajs/inertia-vue3';

const form = useForm({
    name: '',
    email: '',
    password: '',
    password_confirmation: '',
    terms: false,
});

const submit = () => {
    form.post(route('register'), {
        onFinish: () => form.reset('password', 'password_confirmation'),
    });
};

const image = "impii_logo_black.png" ;

</script>
