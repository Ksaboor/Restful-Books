<template>
    <div>
    <button type="button" class="btn btn-primary">{{ msg }}</button>
    </div>
</template>

<script>
import axios from 'axios';

    export default {
        name:'Ping',
        data(){
            return{
                msg: '',
            };
        },
        methods: {
            getmessage() {
                const path = 'http://localhost:5000/ping';
                axios.get(path)
                .then((res) => {
                    this.msg = res.data;
                })
                .catch((error) => {
                    console.error(error);
                });
            },
        },
        created() {
            this.getmessage();
        },
    };
</script>

<style scoped>

</style>