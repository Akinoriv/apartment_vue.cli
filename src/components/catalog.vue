<template>

  <div class="page">
    <div class="page__title">
      <h1> Apartamets </h1>
    </div>

    <div class="wrap">
      <div class="flats" v-for="item in info.response" :key="item.id">
   
        <div class="flat__item">
          <img class="flat__item-img" :src="`${item.img}`">
          <h2 class="flat__item-name"> {{ item.attributes.title }} - {{ item.attributes.rooms }}х  комнатная {{ item.type }} в Москве </h2>
          <h3> {{ item.attributes.area }} квм</h3>
          <h3>  </h3>
          <h4> Владелец: {{ item.relationships.attributes.first_name }} {{ item.relationships.attributes.last_name }} </h4>
          <div class="flat__item-block">
            
            <div class="flat__button-box">
              <button  v-if="item.like" class="flat__button"  v-on:click="putInBacskets0"> like </button>
              <button  v-else id="hide-seen" class="flat__button flat__button--basket" v-on:click="putInBacskets0"> 
                <img class="foter__contacts-img" 
                src="https://raw.githubusercontent.com/Akinoriv/Redsoft-test/216b544ec28482b1801ed7ef5c97ec9a1b2ceb7f/my-project/src/assets/Vector.svg"> 
                {{ picture[0].state }} 
              </button>
            </div>
          </div>
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
      // console.log ('./entities.json')
  },

  methods: {  
  
    // changes the state of the button on clicked
    putInBacskets0: function () {
      this.picture[0].status = !this.picture[0].status;
      // this.picture[0].state = this.picture[0].status ? 'Like' : 'Like';
    },

  
    ajaxRequest: function() {
      this.putInBacskets2();
      var then = this;
      let XMLH = new XMLHttpRequest();

      XMLH.open('GET', "https://jsonplaceholder.typicode.com/posts/1");
      
      XMLH.onreadystatechange = function() {
        if (XMLH.readyState === 4 && XMLH.status === 200) {
          test(XMLH.responseText);
          putInBacsketsOk(XMLH.responseText);
        }
        else {
          putInBacsketsEror()
        }
      }
      function putInBacsketsOk() {
        then.picture[2].status = !then.picture[2].status;
        then.picture[2].state = then.picture[2].status ? 'Купить' : 'В корзине';
      }
      function putInBacsketsEror() {
        then.picture[2].status = !then.picture[2].status;
        then.picture[2].state = then.picture[2].status ? 'Купить' : 'Eror';
      // then.picture[2].state =  'обработка' ;
    }
      function test(data) {
        console.log(data) 
      }

      XMLH.send();
    
    },
  },

    
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">

.page {
  color: #222222;
  /* min-height: calc(100vh - 80px); */
  padding-top: 102px;
  padding-bottom: 96px;
  // box-sizing: border-box;
	// min-height: 100%; 
  .page__title {

    /* max-width: 1400px; */
    /* padding-left: 7%; */
    justify-content: start;
    padding: 24px;
    padding-bottom: 14px;
    /* position: fixed; */
  }
}
.wrap {
   display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    grid-gap: 1rem;
  /* padding:24px; */
  margin: 0 auto;
  width: 100%;
  max-width: 1400px;


  /* justify-content: space-between; */
}

/* .flats {
} */

.flat__item {
  // height: 328px;
  // width: 282px;
  float:left; 
  text-align:center;
  margin: 14px;
  /* position: absolute; */
  /* left: 0%;
  right: 0%;
  top: 0%;
  bottom: 0%; */
  border: 1px solid #E1E1E1;
  box-sizing: border-box;
}

.flat__item-name {
  padding-left: 24px;
  text-align: left;
  line-height: 1.5;
}

.flat__item-img  {
  height: 258px;
  width: 380px;
}

.flat__item-block {
  margin:  24px;
  /* padding-top: ; */
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
}

.flat__button {
   /* padding-left: 24px; */
  border: none;
  height: 48px;
  width: 120px;
  background-color: #382E2B;
  color: #F4F6F9;
  Font-Family: Merriweather;
  Font-Style: Bold;
  Font-Size: 14px;
  Line-Height: 21px;
  Line-Height: 150%;
  /* justify-content: space-evenly; */
  justify-content:right;
}

.flat__button--basket {
  background-color: #5B3A32
  
}


</style>
