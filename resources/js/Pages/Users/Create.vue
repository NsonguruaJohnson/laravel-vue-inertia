<template>
    <Head title="Create User" />

    <h1 class="text-3xl">Create New User</h1>

    <form @submit.prevent="submit" class="max-w-md mx-auto mt-8">
        <div class="mb-6">
            <label
                for="name"
                class="block mb-2 uppercase font-bold text-xs text-gray-700"
            >
                NAME
            </label>
            <input
                v-model="form.name"
                class="border border-gray-400 p-2 w-full"
                type="text"
                id="name"
            >
            <div
                v-if="form.errors.name"
                v-html="form.errors.name"
                class="text-red-500 text-xs mt-1"
            >
            </div>
        </div>

        <div class="mb-6">
            <label
                for="email"
                class="block mb-2 uppercase font-bold text-xs text-gray-700"
            >
                EMAIL
            </label>
            <input
                v-model="form.email"
                class="border border-gray-400 p-2 w-full"
                type="email"
                id="name"
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
                class="border border-gray-400 p-2 w-full"
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
                Submit
            </button>
        </div>

    </form>
</template>

<script setup>
    import { useForm } from '@inertiajs/inertia-vue3';

    {
        // $this.inertia.form({
            // name: ''
        // });
        // the above is for vue 2 or option API(maybe)
    }

    let form = useForm({
        name: '',
        email: '',
        password: '',
    });

    let submit = () => {
        form.post('/users');
    };

</script>

<style>

</style>
