<script>
import AppHeader from './components/AppHeader.vue';
import TextGallery from './components/TextGallery.vue';
import AppFooter from './components/AppFooter.vue';
import ImageGallery from './components/ImageGallery.vue';
import PasswordInput from './components/PasswordInput.vue';
import FontEditor from './components/FontEditor.vue';
import LampToggle from './components/LampToggle.vue';
import ImageEditor from './components/ImageEditor.vue';
import AppStaff from './components/AppStaff.vue';
import LogoEditor from './components/LogoEditor.vue';
import MemGenTemplate from './components/MemGenTemplate.vue';
import ImageGalleryArray from './components/ImageGalleryArray.vue';
import TodoList from './components/TodoList.vue';
import TodoListTemplate from './components/TodoListTemplate.vue';
import NotesApp from './components/NotesApp.vue';
import SpyGameTemplate from './components/SpyGameTemplate.vue';
import BooksAppTemplate from './components/BooksAppTemplate.vue';
import BookCardTemplate from './components/BookCardTemplate.vue';
import BlogAppTemplate from './components/BlogAppTemplate.vue';
import BlogPost from './components/BlogPost.vue';

export default {
  components: {
    AppHeader,
    BlogPost,
    TextGallery,
    AppFooter,
    ImageGallery,
    PasswordInput,
    FontEditor,
    LampToggle,
    ImageEditor,
    AppStaff,
    LogoEditor,
    MemGenTemplate,
    ImageGalleryArray,
    TodoList,
    TodoListTemplate,
    NotesApp,
    SpyGameTemplate,
    BooksAppTemplate,
    BookCardTemplate,
    BlogAppTemplate
  }
}
</script>

<template>

  <header>
    <app-header></app-header>
  </header>

  <body>
    <h6>Компонент №1. Текстовая галерея</h6>
    <text-gallery></text-gallery>
    <hr>

    <h6>Компонент №2. Галерея картинок</h6>
    <image-gallery></image-gallery>
    <hr>

    <h6>Компонент №3. Пароль</h6>
    <password-input></password-input>
    <hr>

    <h6>Компонент №4. Редактор текстовый</h6>
    <font-editor></font-editor>
    <hr>

    <h6>Компонент №5. Редактор картинок</h6>
    <image-editor></image-editor>
    <hr>

    <h6>Компонент №6. Редактор лого</h6>
    <logo-editor></logo-editor>
    <hr>

    <h6>Компонент №7. Список задач 1</h6>
    <todo-list-template></todo-list-template>
    <hr>

    <h6>Компонент №8. Список задач 2</h6>
    <todo-list></todo-list>
    <hr>

    <h6>Компонент №9. Заметки</h6>
    <notes-app></notes-app>
    <hr>

    <h6>Компонент №10. Кумир</h6>
    <spy-game-template></spy-game-template>
    <hr>

    <h6>Компонент №11. Книги</h6>
    <books-app-template></books-app-template>
    <hr>

    <h6>Компонент №12. Блог</h6>
    <blog-app-template></blog-app-template>
    <hr>

    <h6>Компонент №13. Лампочка</h6>
    <lamp-toggle></lamp-toggle>
    <hr>

    <h6>Компонент №14. Команда</h6>
    <app-staff></app-staff>
    <hr>

    <h6>Компонент №15. Массив из изображений</h6>
    <image-gallery-array></image-gallery-array>
    <hr>

    <h6>Компонент №16. Генератор мемов</h6>
    <MemGenTemplate></MemGenTemplate>
    <hr>
  </body>

  <footer>
    <app-footer></app-footer>
  </footer>

</template>

<style scoped>
body {
  text-align: center;
}

</style>
