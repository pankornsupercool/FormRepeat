<template>
<div class="">
    <label>Data Model</label>
    <br/>
      <label>Name : {{name}}</label>
      <br/>
      <label>Lastname : {{lastname}}</label>
      <br/>
      <label>Favorite Thing : {{fav}}</label>
    <br/>
      <label>Asia : {{asia}}</label>
          <br/>
      <label>Europe : {{europe}}</label>
                <br/>
      <label>Gender : {{gender}}</label>
</div>
</template>

<script>
export default {
    name : 'BaseDisplay',
    props:{
        name :{
            type : [String, Number],
            default: ''
        },
        lastname :{
            type : [String, Number],
            default: ''
        },
        fav:{
            type :[String, Number],
            default: ''
        },
        asia: {
            type : Boolean
        },
        europe:{
            type : Boolean
        },
        gender :{
            type : [String,Number],
        }
    }
}
</script>

<style scoped>
.bord{
    border: 1px solid black;
}
</style>
