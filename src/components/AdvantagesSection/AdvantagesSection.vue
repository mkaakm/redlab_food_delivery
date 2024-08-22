<template>
    <section class="advantages-section">
      <Card 
        v-for="(advantage, index) in advantages" 
        :key="index" 
        :title="advantage.title" 
        :image="advantage.image" 
        :description="advantage.description" 
      />
    </section>
  </template>
  
  <script>
  import Card from '../Card/Card.vue';
  
  export default {
    components: {
      Card
    },
    data() {
      return {
        advantages: [
          { title: 'Висока якість продукції', image: './Check.svg', description: 'Наша доставка гарантує вам високу якість продуктів.  Кожна страва, яку ми готуємо, пройшла строгий контроль якості, щоб забезпечити вам найкращий смаковий досвід.' },
          { title: 'Різноманітність страв', image: './Bowl.svg', description: 'Наша доставка гарантує вам високу якість продуктів.  Кожна страва, яку ми готуємо, пройшла строгий контроль якості, щоб забезпечити вам найкращий смаковий досвід.' },
          { title: 'Швидка доставка', image: './Roket.svg', description: 'Наша доставка гарантує вам високу якість продуктів.  Кожна страва, яку ми готуємо, пройшла строгий контроль якості, щоб забезпечити вам найкращий смаковий досвід.' },
          { title: 'Працюємо цілодобово', image: './clock.svg', description: 'Наша доставка гарантує вам високу якість продуктів.  Кожна страва, яку ми готуємо, пройшла строгий контроль якості, щоб забезпечити вам найкращий смаковий досвід.' },
        ]
      };
    }
  };
  </script>
  
  <style scoped>
  .advantages-section {
    display: flex;
    justify-content: center;
    gap: 40px;
    margin-top: 73px;
    margin-bottom: 70px;
  }

  @media (max-width: 768px) {
    .advantages-section {
    gap: 20px;
    margin-top: 50px;
    margin-bottom: 50px;
  }
  }
  @media (max-width: 480px) {
    .advantages-section {
      box-sizing: border-box;
    align-items: center;
    gap: 15px;
    margin-top: 30px;
    margin-bottom: 30px;
    padding: 0 15px;
  }
  }
  </style>
  