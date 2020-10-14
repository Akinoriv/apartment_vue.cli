<template>
  <div id="app">

    <header class="header">

      <div class="header__links">
        <img class="logo" src="/logo.png"> 
        <nav class="menu">
          <ul class="menu__list">
            <li class="menu__list-item"> home </li>
            <li class="menu__list-item"> about us </li>
            <li class="menu__list-item"> contact </li>
            <li class="menu__list-item"> your likes </li>
          </ul>
        </nav>
      </div>

      <div class="search">
        <input class="search__input" placeholder="Поиск самой красивой квартиры">
        <button class="search__button"> Найти </button>
      </div>

    </header>

    <catalog/>

    <footer class="footer">
      <div class="footer__links">
        <!-- <img class="logo" src="https://github.com/Akinoriv/Redsoft-test/blob/master/my-project/src/assets/logo-museum%202.png?raw=true">  -->
        <nav class="menu">
          <ul class="menu__list">
            <li class="menu__list-item"> Contacts </li>
          </ul>
        </nav>
      </div>
    </footer>

  </div>
  
</template>

<script>
import catalog from './components/catalog.vue'

export default {
  name: 'App',
  components: {
    catalog
  }
}



</script>

<style lang="scss">

.header {
  padding: 12px;
  /* padding-top: 24px;
  padding-bottom: 24px; */
  background: #222222;
  border-bottom: 1px solid #E1E1E1;
  display: flex;

  width: auto;
  /* max-width: 1400px; */
  justify-content: space-around;
  position: fixed;
  top: 0px;
  right: 0px;
  left: 0px;
  .header__links {
    display: flex;
    justify-content: space-between;
    padding-left: 8px;
  }
}
.search__button {
  /* padding-left: 24px; */
  border: none;
  height: 48px;
  width: 122px;
  background-color:#4F4F4F;
  color: #F4F6F9;
  Font-Family: Merriweather;
  Font-Style: Bold;
  Font-Size: 14px;
  Line-Height: 21px;
  Line-Height: 150%;
  /* justify-content: space-evenly; */
  justify-content:right;
}

.search__input {
  padding-left: 16px;
  border: 1px solid #E1E1E1;
  box-sizing: border-box;
  height: 48px;
  width: 294px;
  background-color: rgb(246, 243, 243);
  color: #9F9F9F;
  align-self : Inside;
  Font-Family: Merriweather;
  Font-Style: normal;
  Font-Size: 14px;
  Line-Height: 21px;
  Line-Height: 150%;
}

.logo {
  height: 58px;
  border: none;
  align-self: center;
}

.menu__list {
  text-transform: uppercase; 
  padding-left: 24px;
  display: flex;
  list-style-type: none;
}

.menu__list-item{
  margin-left: 24px;
  margin-right: 24px;
  align-self: center;
  justify-content:start;  
}


.footer {
  /* height: 96px; */
  // padding: 24px;
  background:#222222;
  display: flex;

  // position: fixed;
	left: 0;
  right: 0;
	bottom: 0;
	width: auto;
  justify-content: space-around;
}

.footer__links {
  display: flex;
  justify-content: space-between;
  padding-left: 27px;
}

.foter__contacts{
  /* justify-content: space-between; */
  display: flex;
}

.foter__contacts-img {
  border: none;
  align-self: center;
  width: auto;
  height: 14px;
}

.foter__contacts-name {
  text-decoration: none;
  margin-left: 24px;
  margin-right: 24px;
  align-self: center;
  justify-content: start;  
  color: #555555;
}

h1 {
  font-weight: bold;
  font-size: 24px;
  /* line-height: 1.7; */
 }

h2 {
  font-weight: normal;
  font-size: 18px;  
 }

h3 {
  font-weight: bold;
  font-size: 16px;
 }

h4 {
  font-weight: bold;
  font-size: 14px;
 }

h5 {
  font-weight: normal;
  font-size: 14px;  
 }

h6 {
  font-weight: 300;
  font-size: 14px;
 }

#app {
  font-family: 'Merriweather', serif;
  color: #F3F3F3;
  font-style: normal;
  Font-Size: 14px;
  Line-Height: 21px;
  Line-Height: 150%;
  
  background: #F3F3F3;

  width: 100%;
  padding-right: 15px;
  padding-left: 15px;
  margin-right: auto;
  margin-left: auto;
  max-width: 1258px;

  height: 100%;

  
  /* padding: 0 calc(50% - 610px); */
}
</style>
