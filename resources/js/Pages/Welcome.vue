<template>
    <BreezeGuestLayout>
        <Head title="Register" />
        <h1 class="text-3xl text-center">Impii Connected Protection</h1>

        <BreezeValidationErrors class="mb-4" />

        <br>
        <div>

            <div class="flex items-center ">
                <BreezeButton class="ml-2" :class="{ 'opacity-25': form.processing }" :disabled="form.processing">
                    Log in
                </BreezeButton>
                <BreezeButton class="ml-2" :class="{ 'opacity-25': form.processing }" :disabled="form.processing">
                    Register
                </BreezeButton>
                <ButtonSOS class="ml-2" :class="{ 'opacity-25': form.processing }" :disabled="form.processing">
                    S.O.S
                </ButtonSOS>
            </div>

        </div>

    </BreezeGuestLayout>
</template>

<script setup>
import BreezeButton from '@/Components/Button.vue';
import ButtonSOS  from '@/Components/ButtonSOS.vue';
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

</script>
