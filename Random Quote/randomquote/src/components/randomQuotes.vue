
<script setup>
import { ref, onMounted} from 'vue'
const quotes = ref([
  {
    text: "The only way to do great work is to love what you do.",
    author: "Steve Jobs",
  },
  {
    text: "Believe you can and you're halfway there.",
    author: "Theodore Roosevelt",
  },
  {
    text: "Life is what happens when you're busy making other plans.",
    author: "John Lennon",
  },
  {
    text: "Success is not the key to happiness. Happiness is the key to success. If you love what you are doing, you will be successful.",
    author: "Albert Schweitzer",
  },
  {
    text: "The best time to plant a tree was 20 years ago. The second best time is now.",
    author: "Chinese Proverb",
  },
  {
    text: "It does not matter how slowly you go as long as you do not stop.",
    author: "Confucius",
  },
  {
    text: "Your time is limited, so don’t waste it living someone else’s life.",
    author: "Steve Jobs",
  },
  {
    text: "If you want to lift yourself up, lift up someone else.",
    author: "Booker T. Washington",
  },
  {
    text: "Don’t watch the clock; do what it does. Keep going.",
    author: "Sam Levenson",
  },
  {
    text: "Keep your face always toward the sunshine—and shadows will fall behind you.",
    author: "Walt Whitman",
  },
  {
    text: "The only limit to our realization of tomorrow is our doubts of today.",
    author: "Franklin D. Roosevelt",
  },
  {
    text: "Act as if what you do makes a difference. It does.",
    author: "William James",
  },
  {
    text: "Success usually comes to those who are too busy to be looking for it.",
    author: "Henry David Thoreau",
  },
  {
    text: "Don't be afraid to give up the good to go for the great.",
    author: "John D. Rockefeller",
  },
  {
    text: "I find that the harder I work, the more luck I seem to have.",
    author: "Thomas Jefferson",
  }
]);

const currentQuote = ref({text : '', author : ''})


const getRandomQuote =() =>{
    const randomIndex = Math.floor(Math.random()* quotes.value.length
)
currentQuote.value =quotes.value[randomIndex]
}

onMounted(getRandomQuote)
</script>

<template>

<div class="quote-generator">
    <h1 class="app-title"> Random Quote </h1>
    <blockquote class="quote-container">
        <p>{{ currentQuote.text }}</p>
        <cite> {{ currentQuote.author }}</cite>
    </blockquote>

    <button @click="getRandomQuote" class="quote-button">Get Random Quote</button>
</div>

</template>
<style scoped>
.quote-generator {
  max-width: 400px;
  margin: 50px auto;
  padding: 20px;
  text-align: center;
  border: 1px solid #ccc;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.app-title {
  font-size: 24px;
  margin-bottom: 20px;
  color: #f2eeee;
}

.quote-container {
  background-color: #f2eff5;
  padding: 20px;
  border-radius: 8px;
  border: 1px solid #ddd;
  margin-bottom: 20px;
}

p {
  font-size: 18px;
  margin-bottom: 10px;
  color: black;
}

cite {
  font-style: normal;
  color: #420feb;
}

.quote-button {
  padding: 10px 20px;
  font-size: 16px;
  background-color: #3498db;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.quote-button:hover {
  background-color: #2980b9;
}
</style>