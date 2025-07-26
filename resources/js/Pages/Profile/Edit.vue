<script setup lang="ts">
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import DeleteUserForm from './Partials/DeleteUserForm.vue';
import UpdatePasswordForm from './Partials/UpdatePasswordForm.vue';
import UpdateProfileInformationForm from './Partials/UpdateProfileInformationForm.vue';
import { Head } from '@inertiajs/vue3';

defineProps<{
    mustVerifyEmail?: boolean;
    status?: string;
}>();
</script>

<template>

    <Head title="Profile" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="h5 fw-semibold text-dark mb-0">Profile</h2>
        </template>

        <div class="py-2">
            <div class="container">
                <div class="row gy-4">

                    <!-- Update Profile Information -->
                    <div class="col-12">
                        <div class="card shadow-sm">
                            <div class="card-body">
                                <UpdateProfileInformationForm :must-verify-email="mustVerifyEmail" :status="status"
                                    class="w-100" />
                            </div>
                        </div>
                    </div>

                    <!-- Update Password -->
                    <div class="col-12">
                        <div class="card shadow-sm">
                            <div class="card-body">
                                <UpdatePasswordForm class="w-100" />
                            </div>
                        </div>
                    </div>

                    <!-- Delete User -->
                    <div class="col-12">
                        <div class="card shadow-sm">
                            <div class="card-body">
                                <DeleteUserForm class="w-100" />
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
