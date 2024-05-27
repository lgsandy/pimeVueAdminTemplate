<script setup>
import { ref } from 'vue';

const dropdownItems = ref([
    { name: 'Option 1', code: 'Option 1' },
    { name: 'Option 2', code: 'Option 2' },
    { name: 'Option 3', code: 'Option 3' }
]);

const dropdownItem = ref(null);
const packageOption = ref('Yes');
// const type = ref('Solo');
</script>

<template>
    <h5>Create Project</h5>
    <div class="grid">
        <div class="col-12">
            <div class="card p-fluid">
                <div class="field">
                    <label for="project_name">Name</label>
                    <Textarea id="project_name" rows="4" />
                </div>
            </div>
        </div>
        <div class="col-12 md:col-7">
            <div class="card p-fluid">
                <h5>Info</h5>
                <div class="field flex flex-column md:flex-row justify-content-between">
                    <label for="code">Code</label>
                    <InputText id="code" type="text" class="w-20rem" />
                </div>
                <div class="field flex justify-content-between">
                    <label for="package">Package</label>
                    <SelectButton v-model="packageOption" :options="['Yes', 'No']" aria-labelledby="basic" id="package" />
                </div>
                <div class="field flex justify-content-between">
                    <label for="type">Type</label>
                    <SelectButton v-model="packageOption" :options="['Solo', 'JV']" aria-labelledby="basic" id="type" />
                </div>
                <div class="field flex justify-content-between">
                    <label for="start_date">Start Date</label>
                    <Calendar id="start_date" class="w-20rem"  showIcon iconDisplay="input"/>
                </div>
                <div class="field flex justify-content-between">
                    <label for="duration_date">Duration</label>
                    <div class="w-20rem flex gap-2">
                        <Dropdown id="duration_date" v-model="dropdownItem" :options="dropdownItems" optionLabel="name" placeholder="Select One"></Dropdown>
                        <InputText id="duration_date" type="text" />
                    </div>
                </div>
                <div class="field flex justify-content-between">
                    <label for="start_date">End Date</label>
                    <Calendar  id="end_date" class="w-20rem"  showIcon iconDisplay="input" />
                </div>
                <div class="field flex justify-content-between">
                    <label for="work_order">Work Order</label>
                    <InputText id="work_order" type="text" class="w-20rem" />
                </div>
                <div class="field flex justify-content-between">
                    <label for="work_date">Work Date</label>
                    <Calendar id="work_date" class="w-20rem"  showIcon iconDisplay="input"/>
                </div>
                <div class="field flex justify-content-between">
                    <label for="services">Services</label>
                    <InputText id="services" type="text" class="w-20rem" />
                </div>
            </div>
        </div>

        <div class="col-12 md:col-5">
            <div class="card p-fluid">
                <h5>Client Details</h5>
                <div class="field grid">
                    <label for="cgroup" class="col-12 mb-2 md:col-2 md:mb-0">Group</label>
                    <div class="col-12 md:col-10">
                        <InputText id="cgroup" type="text" />
                    </div>
                </div>
                <div class="field grid">
                    <label for="cname" class="col-12 mb-2 md:col-2 md:mb-0">Name</label>
                    <div class="col-12 md:col-10">
                        <InputText id="cname" type="text" />
                    </div>
                </div>
                <div class="field grid">
                    <label for="address" class="col-12 mb-2 md:col-2 md:mb-0">Address</label>
                    <div class="col-12 md:col-10">
                        <Textarea id="address" rows="4" />
                    </div>
                </div>
                <div class="field grid">
                    <label for="contact" class="col-12 mb-2 md:col-2 md:mb-0">Contact</label>
                    <div class="col-12 md:col-10">
                        <InputMask id="contact" mask="999-99-9999" placeholder="999-99-9999" />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
