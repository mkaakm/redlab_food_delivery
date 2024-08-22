   <template>
    <div class="card-container">
      <div class="card" @mouseover="flipped = true" @mouseleave="flipped = false">
      <div class="card-inner" :class="{ flipped }">
        <div class="card-front">
          <h2>{{ title }}</h2>
          <img :src="image" alt="Card Image" />
        </div>
        <div class="card-back">
          <p>{{ description }}</p>
        </div>
      </div>
    </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: String,
      image: String,
      description: String
    },
    data() {
      return {
        flipped: false
      };
    }
  };
  </script>
  
  <style scoped>
  @keyframes show {
  to {transform: translateY(0%)}
}
  .card-container{
    position: relative;
    z-index: 5;
    overflow: hidden;
  }
  .card {
    width: 300px;
    height: 328px;
    perspective: 1000px;
    position: relative;
    transform: translateY(100%);
    z-index: 1;
    animation-name: show;
    animation-duration: 4s;
    animation-fill-mode: forwards;
  }
  .card-container:nth-child(1) .card{
    transform: translateY(100%);
  }
  .card-container:nth-child(2) .card{
    transform: translateY(140%);
  }
  .card-container:nth-child(3) .card{
    transform: translateY(180%);
  }
  .card-container:nth-child(4) .card{
    transform: translateY(220%);
  }
  
  .card-inner {
    width: 100%;
    height: 100%;
    transition: transform 2s;
    transform-style: preserve-3d;
    position: relative;
  }
  
  .card-front, .card-back {
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
    position: absolute;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    border-radius: 16px;
  }
  
  .card-front {
    background-color: #F3F6FB;
  }
  
  .card-back {
    background-color: #5A30F0;
    color: white;
    transform: rotateY(180deg);
  }
  
  .card-inner.flipped {
    transform: rotateY(180deg);
  }
  
  .card-front h2 {
    font-family: 'TT Travels', sans-serif;
    font-weight: 500;
    font-size: 24px;
    color: #404040;
  }
  
  .card-front img {
    width: 190px;
    height: 190px;
    margin-top: 16px;
  }
  
  .card-back p {
    font-family: 'TT Travels', sans-serif;
    font-weight: 400;
    font-size: 16px;
    line-height: 22.4px;
    margin: 15px;
    display: block;
    width: 240px;
    height: 250px;
    text-align: left;
  }

  @media (max-width: 768px) {
    .card-container{
      display: flex;
      justify-content: center;
      align-items: center;
    }
  .card {
    width: 150px;
    height: 200px;
  }

  .card-front img {
    width: 100px;
    height: 100px;
  }

  .card-front h2 {
    font-size: 14px;
  }

  .card-back p {
    font-size: 10px;
    line-height: 15px;
    width: 100px;
    height: 100px;
  }
}

/* Mobile devices */
@media (max-width: 480px) {
  .card-container{
      width: 24%;
    }
  .card {
  width: 100%;
  height: 150px;
  }
  .card-front h2 {
    font-size: 10px;
  }

  .card-back p {
    font-size: 8px;
    line-height: 10px;
    width: 100%;
    height: auto;
  }
}
  </style>
  