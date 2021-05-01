<template>
  <div class="home">
    <img alt="Vue logo" src="../images/letter.png" width="120" />
    <BaseInput
      msg="Registration Form"
      v-model="event.name"
      label="Name"
      type="text"
    />
        <BaseInput
      msg="Registration Form"
      v-model="event.lastname"
      label="Lastname"
      type="text"
    />
    <br/>
    <BaseCombobox label="Favorite Thing " :options="fav" v-model="event.fav"/>
    <br/>
    <BaseCheckbox v-model="event.regions.asia" label="Asia" />
    <br/>
    <BaseCheckbox v-model="event.regions.europe" label="Europe" @update:modelValue="checkUpdate" />
    <br/>
    <!-- <BaseRadio v-model="event.gender" label="Male " :value="1" name="gender"/>
    <BaseRadio v-model="event.gender" label="Female " :value="2" name="gender"/> -->
    <div>
    <BaseRadioGroup
    v-model="event.gender"
    name="gender"
    :options="genderOption"
    />
    </div>
    
    <BaseDisplay
      :name="event.name"
      :lastname="event.lastname"
      :fav="event.fav"
      :asia="event.regions.asia"
      :europe="event.regions.europe"
      :gender="event.gender"
      class="pre-card"
    />
  </div>
</template>

<script>
// @ is an alias to /src
import BaseInput from "@/components/BaseInput.vue";
import BaseDisplay from "@/components/BaseDisplay.vue";
import BaseCombobox from "@/components/BaseCombobox.vue";
import BaseCheckbox from "@/components/BaseCheckbox.vue";
import BaseRadioGroup from "@/components/BaseRadioGroup.vue";
export default {
  name: "Home",
  components: {
    BaseInput,
    BaseDisplay,
    BaseCombobox,
    BaseCheckbox,
    BaseRadioGroup,
  },
  data() {
    return {
      fav :[
        'Book',
        'Music',
        'Beauty',
        'Sport',
        'Game',
      ],
      event: {
        name: "",
        lastname: "",
        age: "",
        gender: 0,
        fav: "",
        regions: {
          asia: false,
          europe: false,
        },
      },
      genderOption:[
        {label: 'Male', value : 1},
        {label: 'Female', value : 2}
      ]
    };
  },
  methods: {
    checkUpdate(value){
      console.log(value);
    }
  }
};
</script>




<style >
.home{
  display: inline-block;
}
a {
  color: #42b983;
}
input {
  margin-left: 10px;
  border: 1px solid rgba(0, 0, 0, 0.2);
  outline: none;
  height: 23px;
}
.pre-card {
  margin-top: 15px;
  border: 1px solid black;
  width:300px;
}
</style>
