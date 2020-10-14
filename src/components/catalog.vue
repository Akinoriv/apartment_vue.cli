<template>

  <div class="flats">
      <div class="flat" v-for="item in info.response" :key="item.id">
        <img class="flat__img" :src="`${item.img}`">
        <h2 class="flat__name"> {{ item.attributes.title }} - {{ item.attributes.rooms }}х  комнатная {{ item.type }} в Москве </h2>
        <div class="flat-box">
          <div class="flat__description">
            <h3 class="flat__description-kvm"> Метраж: {{ item.attributes.area }} квм </h3>
            <h3 class="flat__description-owner"> Владелец: {{ item.relationships.attributes.first_name }} {{ item.relationships.attributes.last_name }} </h3>
          </div>
          <div class="flat__button-box">
            <button class="flat__button" v-if="item.like" v-on:click="item.like = !item.like"> 
              <svg class="flat__button-vector" fill="currentColor" width="1em" height="1em">
                <path fill-rule="evenodd" d="M13.854 3.646a.5.5 0 0 1 0 .708l-7 7a.5.5 0 0 1-.708 0l-3.5-3.5a.5.5 0 1 1 .708-.708L6.5 10.293l6.646-6.647a.5.5 0 0 1 .708 0z"/>
              </svg> 
              like 
            </button>
            <button class="flat__button flat__button--basket" v-else v-on:click="item.like = !item.like"> 
              like 
            </button>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      info: []
    }
  },
   mounted() {
    axios
      .get('/entities.json')
      .then(response => (this.info = response.data));
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">

.flats {
  color: #222222;
  padding-top: 102px;
  padding-bottom: 96px;

  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  grid-gap: 70px;
  max-width: 1400px;
}

.flat {
  height: 460px;
  width: 382px;
  float:left; 
  margin: 14px;
  border: 1px solid #E1E1E1;
  box-sizing: border-box;
  justify-self: center;
  display: grid;
  align-content: space-between;
  .flat__name {
    margin: 0;
    padding: 16px;
    text-align: left;
    line-height: 1.5;
  }
  .flat__img  {
    height: 258px;
    width: 380px;
  }
}

.flat-box {
  display: flex;
  justify-content: space-between;
}

.flat__description {
  padding-left: 16px;
  justify-self: start;
  .flat__description-kvm{
    margin-top: 24px;
    margin-bottom: 6px;
  }
  .flat__description-owner {
    margin: 0;
  }
}

.flat__button-vector {
  
  color: #F4F6F9;
  fill:"currentColor";
}
.flat__button-box {
    margin:  24px;
    
  .flat__button {
    border: none;
    height: 48px;
    width: 120px;
    background-color: #222222;
    color: #F4F6F9;

    font-Family: Merriweather;
    font-Size: 14px;
    line-Height: 150%;
    justify-content:right;
  }
  .flat__button--basket {
    background-color: #4F4F4F;
  }

}

</style>
