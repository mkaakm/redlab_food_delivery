<template>
  <nav :class="{'navbar': true, 'scrolled': isScrolled}">
    <div class="navbar-action">
      <div class="logo">FoodDeliver</div>
    <div class="toggle">
      <button :class="{'active': activeTab === 'delivery'}" @click="setActiveTab('delivery')">Доставка</button>
      <button :class="{'active': activeTab === 'pickup'}" @click="setActiveTab('pickup')">Самовивоз</button>
    </div>
    </div>
    <Burger @toggle="toggleBurgerMenu"/>
    <div class="links">
      <a href="#">Заклади</a>
      <a href="#">Доставка і оплата</a>
      <a href="#">Акції</a>
      <a href="#">Про нас</a>
    </div>
    <div class="mobile-links" v-if="open">
      <a href="#">Заклади</a>
      <a href="#">Доставка і оплата</a>
      <a href="#">Акції</a>
      <a href="#">Про нас</a>
    </div>
    <div class="contact-info">
      <div >
        +380 67 451 99 57 
      </div>
      <div class="line">
        |
      </div>
      <div>
        24/7
      </div>
    </div>
  </nav>
</template>

<script>
import Burger from './Burger.vue';

export default {
  components:{
    Burger,
  },
  data() {
    return {
      isScrolled: false,
      activeTab: 'delivery',
      open:false,
    };
  },
  methods: {
    setActiveTab(tab) {
      this.activeTab = tab;
    },
    handleScroll() {
      this.isScrolled = window.scrollY > 50; 
    },
    toggleBurgerMenu(){
      this.open = !this.open
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
  }
};
</script>

<style scoped>
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 16px 32px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  transition: background-color 0.3s ease;
  background-color: transparent;
  z-index: 1000;
  box-sizing: border-box;
}
.navbar-action{
  display: flex;
  align-items: center;
  gap:27px;
}


.navbar.scrolled {
  background-color: white;
}

.logo {
  font-family: 'Verdana', sans-serif;
  font-weight: 700;
  font-size: 18px;
  color: #404040;
  
}

.toggle {
  display: flex;
  border-radius: 48px;
  background-color: #fff;
}

.toggle button {
  border: 1px solid #fff;
  border-radius: 48px;
  padding: 3px 12px;
  font-family: 'TT Travels', sans-serif;
  font-size: 16px;
  color: #404040;
  background-color: #fff;
}

.toggle .active {
  background-color: #5A30F0;
  color: #fff;
}

.links {
  display: flex;
  gap: 32px;
  position: absolute;
  left: 50%;
  transform:translateX(-50%);
}

.links a {
  font-family: 'TT Travels', sans-serif;
  font-weight: 500;
  font-size: 16px;
  color: #404040;
  text-decoration: none;
}

.contact-info {
  font-family: 'TT Travels', sans-serif;
  font-weight: 600;
  font-size: 16px;
  color: #404040;
  display: flex;
  justify-content: center;
  align-items: center;
}
.line{
  margin-left: 15px;
  margin-right: 15px;
}
.mobile-links{
  display: none;
}
@media (max-width: 768px) {
  .navbar {
    padding: 16px 8px;
    justify-content: space-between;
    flex-wrap: wrap;
  }

  .logo {
    margin-left: 0;
    margin-right: 0;
    font-size: 16px;
  }

  .toggle {
    margin-right: 0;
  }

  .links {
    display: none;
  }

  .contact-info {
    display: none;
  }
  .mobile-links{
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    width: 100%;
  }
  .mobile-links a{
    text-decoration: none;
    color: #404040;
    position: relative;
    top: 10px;
  }
}

@media (max-width: 480px) {
  .navbar {
    padding: 12px 4px;
  }

  .logo {
    font-size: 14px;
  }

  .toggle {
    margin-right: 0;
  }

  .links {
    gap: 8px;
    font-size: 14px;
    text-align: center;
  }

  .contact-info {
    font-size: 12px;
  }
  .mobile-links a{
    font-size: 12px;
  }
}
</style>
 