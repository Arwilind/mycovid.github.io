<template>
    <div class="container">
        <h2 class="text-font">{{ text }}</h2>
        <div class="time">
            {{ timestamp }}
        </div>
    </div>
</template>

<script>
import moment from 'moment'

export default {
    name: 'DataTitle',
    props: ['text', 'dataDate'],
    computed:{
        timestamp: function() {
            return moment(this.dataDate).format('MMMM Do YYYY, h:mm:ss a')
        }
    }
  
};
</script>


<style scoped>
.container{
    width: 100%;
    text-align: center;
    padding: 10px 20px 50px 20px;
    background-color: #ffffff73;


}
.text-font{
    font-size: 2.5rem;
    font-weight: bold;
    color: #000;

}
.time{
    font-size: 25px;
    font-weight: bold;
    color: #000;

}
</style>