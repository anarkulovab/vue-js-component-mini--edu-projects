<script>
import BookCardTemplate from './BookCardTemplate.vue';

export default {
  components: {
    BookCardTemplate
  },

  data() {
    return {
      books: [
        {
          title: 'Кладовки - лучшая альтернатива для IT',
          author: 'Иван Иванович',
          rating: 4.2,
          image: 'book1'
        },
        {
          title: 'Исповедь Питониста',
          author: 'Иван Иванович',
          rating: 4.76,
          image: 'book2'
        },
        {
          title: 'Пособие для сов программистов',
          author: 'Иван Иванович',
          rating: 3.15,
          image: 'book3'
        },
        {
          title: 'Бэкенд или фронтенд?',
          author: 'Иван Иванович',
          rating: 4.99,
          image: 'book4'
        },
      ],
      count: 0,
    };
  },

  computed: {
    countBooks() {
      let count = 0;
      for (let i = 0; i < this.books.length; i ++) {
        let book = this.books[i];
        if (book.rating > 4.5) {
          count++
        }
      }
      return count
    }
  }

};
</script>

<template>
  <header class="mb-5">
    <nav class="navbar">
      <div class="container-fluid">
        <h1 class="navbar-brand text-white">Количество книг с рейтингом 4.5 и более: {{ countBooks }}</h1>
      </div>
    </nav>
  </header>

  <main class="container">
    <h2>Книги недели:</h2>
    <div class="row g-2">
      <div class="col-6 col-md-4 col-lg-3" v-for="book in books">
        <book-card-template :book="book" :count="count"></book-card-template>
        
      </div>
    </div>
  </main>
</template>

<style scoped>
body {
  margin: 0;
}
.navbar {
  background-color: #008cd5;
  color: white;
}
</style>