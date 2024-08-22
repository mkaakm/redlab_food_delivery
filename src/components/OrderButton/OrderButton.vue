<template>
    <div 
      class="order-button-container" 
      :style="buttonStyle" 
      @mousemove="onMouseMove" 
      @mouseleave="onMouseLeave"
    >
      <div class="order-button">
        <p>Замовити доставку</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isHovered: false,
        offsetX: 0,
        offsetY: 0
      };
    },
    computed: {
      buttonStyle() {
        return {
          transform: `translate(${this.offsetX}px, ${this.offsetY}px) scale(${this.isHovered ? 1.35 : 1})`,
          transition: this.isHovered ? 'none' : 'transform 0.3s ease'
        };
      }
    },
    methods: {
      onMouseMove(event) {
        this.isHovered = true;
        const rect = event.target.getBoundingClientRect();
        this.offsetX = (event.clientX - rect.left - rect.width / 2) / 10;
        this.offsetY = (event.clientY - rect.top - rect.height / 2) / 10;
      },
      onMouseLeave() {
        this.isHovered = false;
        this.offsetX = 0;
        this.offsetY = 0;
      }
    }
  };
  </script>
  
  <style scoped>
  .order-button-container {
    position: absolute;
    top:575px;
    left: 43%;
    transform: translateX(-50%);
    width: 195px;
    height: 195px;
    border: 1px solid #5A30F0;
    border-radius: 50%;
    background-color: #5A30F0;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: transform 0.3s ease;
  }
  
  .order-button p {
    font-family: 'TT Travels', sans-serif;
    font-weight: 600;
    font-size: 21px;
    line-height: 23.4px;
    color: #FFFFFF;
    text-align: center;
    transform: rotate(15deg);
    animation: rotateText 40s linear infinite;
  }
  
  @keyframes rotateText {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(360deg);
    }
  }

@media (max-width: 768px) {
  .order-button-container {
    top: 350px;
    width: 100px;
    height: 100px;
    margin-left: 45px;
  }

  .order-button p {
    font-size: 12px;
    line-height: 11px;
  }
}

@media (max-width: 480px) {
  .order-button-container {
    top: 185px;
    width: 50px;
    height: 50px;
    margin-left:7px;
  }

  .order-button p {
    font-size: 10px;
    line-height: 10px;
  }
}
  </style>
  