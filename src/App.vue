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
      <h2 class="footer__name"> Contacts </h2>
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
  background: #222222;
  border-bottom: 1px solid #E1E1E1;
  display: flex;
  width: auto;
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


.logo {
  height: 58px;
  border: none;
  align-self: center;
}
@media only screen and (max-width:1066px) {
  .logo{
    display:none;
  }
}

@media only screen and (max-width:901px) {
  .menu{
    display:none;
  }
}

.menu__list {
  text-transform: uppercase; 
  padding-left: 24px;
  display: flex;
  list-style-type: none;
  .menu__list-item{
    margin-left: 24px;
    margin-right: 24px;
    align-self: center;
    justify-content:start;  
  }
}

.search__button {
  border: none;
  height: 48px;
  width: 122px;
  background-color:#4F4F4F;
  color: #F4F6F9;
  font-Family: Merriweather;
  font-Size: 14px;
  line-Height: 150%;
  justify-content:right;
}
.search__input {
  padding-left: 16px;
  border: 1px solid #E1E1E1;
  box-sizing: border-box;
  height: 48px;
  width: 294px;
  background-color: rgb(246, 243, 243);
  color: 222222;
  align-self : Inside;
  font-Family: Merriweather;
  font-Size: 14px;
  line-Height: 150%;
  justify-content:right;
}
@media only screen and (max-width:901px) {
  .search {
    width: 90%;
    .search__input {
      width: 70%;
    }
    .search__button {
      width: 30%;
    }
  }
}

.footer {
  background:#222222;
  display: flex;
  position: fixed;
	left: 0;
  right: 0;
	bottom: 0;
	width: auto;
  justify-content: space-around;
}

.footer__name {
  text-transform: uppercase; 
  color: #F4F6F9;
  font-size: 16px;
  align-self: center;
}

h1 {
  font-weight: bold;
  font-size: 24px;
 }

h2 {
  font-weight: normal;
  font-size: 18px;  
 }

h3 {
  font-weight: 300;
  font-size: 16px;
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
}

</style>
