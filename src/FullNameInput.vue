<template>
    <div>
        <div class="form-group">
            <label for="firstName">First Name</label>
            <input
                    type="text"
                    id="firstName"
                    class="form-control"
                    v-model="firstName">
        </div>
        <div class="form-group">
            <label for="lastName">Last Name</label>
            <input
                    type="text"
                    id="lastName"
                    class="form-control"
                    v-model="lastName">
        </div>
    </div>
</template>

<script>
    export default {
        props: ['value'],
        data() {
            return {
                firstName: '',
                lastName: ''
            }
        },
        computed: {
            fullName () {
                return this.firstName + ' ' + this.lastName;
            }
        },
        watch: {
            fullName() {
                this.$emit('input', this.fullName)
            },
            value() {
                const names = this.value.split(' ');
                this.firstName = names[0];
                this.lastName = names[names.length - 1];
            }
        }
    }
</script>

<style scoped>

</style>