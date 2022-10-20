<template>
    <Head  title="Login Page"/>
    <main class="grid place-items-center min-h-screen">

        <section class="bg-white p-8 rounded-xl max-w-md mx-auto border">

            <h1 class="text-3xl mb-6">Login</h1>
            <form @submit.prevent="submit">
                <div class="mb-6">
                    <label
                        for="email"
                        class="block mb-2 uppercase font-bold text-xs text-gray-700"
                    >
                        EMAIL
                    </label>
                    <input
                        v-model="form.email"
                        class="border p-2 w-full rounded-xl"
                        type="email"
                        id="email"
                    >
                    <div
                        v-if="form.errors.email"
                        v-html="form.errors.email"
                        class="text-red-500 text-xs mt-1"
                    >
                    </div>
                </div>

                <div class="mb-6">
                    <label
                        for="password"
                        class="block mb-2 uppercase font-bold text-xs text-gray-700"
                    >
                        PASSWORD
                    </label>
                    <input
                        v-model="form.password"
                        class="border p-2 w-full rounded-xl"
                        type="password"
                        id="name"
                    >
                    <div
                        v-if="form.errors.password"
                        v-html="form.errors.password"
                        class="text-red-500 text-xs mt-1"
                    >
                    </div>
                </div>

                <div class="mb-6">
                    <button
                        type="submit"
                        class="bg-blue-400 text-white rounded py-2 px-4 hover:bg-blue-500"
                        :disabled="form.processing"
                    >
                        Log In
                    </button>
                </div>
            </form>

        </section>
    </main>


</template>

<script>
    export default {
        layout: null
    };
</script>

<script setup>
import { useForm } from '@inertiajs/inertia-vue3'

    let form = useForm({
        email: '',
        password: ''
    });
    let submit = () => {
        form.post('/login');
    };
</script>

