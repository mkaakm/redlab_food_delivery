<template>
  <section class="hero-section">
    <div class="image-container">
      <img src="../../../public/log_left.svg" alt="Hero Image" />
    </div>
    <div class="text-container">
      <h1>Доставка готової їжі в Києві</h1>
      <p>Ми пропонуємо доставку їжі прямо до ваших дверей. Насолоджуйтесь смачними стравами без необхідності готувати самостійно.</p>
      <OrderButton />
    </div>
  </section>
</template>

<script>
import OrderButton from '../../components/OrderButton/OrderButton.vue';

export default {
  components: {
    OrderButton
  }
};
</script>

<style scoped>
.hero-section {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  align-items: center;
}

.image-container {
  width: 720px;
  height: 800px;
}

.image-container img {
  width: 100%;
  height: auto;
}

.text-container {
  margin-left: 32px;
  width: 401px;
  height: 382px;
  margin-left: 155px;
  margin-right: 163px;
}

h1 {
  font-family: 'TT Travels', sans-serif;
  font-weight: 400;
  font-size: 76px;
  line-height: 83.6px;
  color: #404040;
}

p {
  font-family: 'TT Travels', sans-serif;
  font-weight: 400;
  font-size: 18px;
  line-height: 25.2px;
  color: #404040;
  width: 375px;
}
@media (max-width: 768px) {

  .image-container {
  width: 420px;
  height: 500px;
}
  .hero-section {
    margin-top: -41px;
  }

  .text-container {
    margin-left: 0;
    margin-right: 0;
    text-align: center;
    margin-top: 200px;
  }

  h1 {
    font-size: 22px;
    line-height: 22px;
    width: 87%;
  }

  p {
    font-size: 12px;
    line-height: 15px;
    width: 87%;
  }
}

@media (max-width: 480px) {

  .image-container {
  width: 100%;
  height: auto;
}
  .hero-section {
   margin-top: -41px;
  }

  .text-container {
    margin-left: 0;
    margin-right: 0;
    text-align: center;
    width: 100%;
    margin-left: 15px;
    height: auto;
    display: flex;
    align-items: center;
    flex-direction: column;
    margin: 0;
    /* position: relative; */
    top: 30px;
  }

  h1 {
    font-size: 15px;
    line-height: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 87%;
    margin-top: 120px;
    margin-bottom: 10px;
  }

  p {
    font-size: 10px;
    line-height: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 87%;
    margin-top: 0;
  }
}
</style>
