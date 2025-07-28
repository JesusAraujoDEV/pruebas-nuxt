<template>
  <div class="container">
    <AboutMe />
    <div class="contents"> <main>
        <ArticleCard 
          v-for="article in articles"
          :key="article.slug"
          :article="article" /> </main>
    </div>
  </div>
</template>

<script setup>
// 1. Importar componentes que estás usando en el template
import AboutMe from '~/components/AboutMe.vue'; // Asegúrate de que esta ruta sea correcta
import ArticleCard from '~/components/ArticleCard.vue'; // Asegúrate de que esta ruta sea correcta

// 2. Definir la variable 'articles' para que exista en el template
// Usamos 'ref' para que sea reactiva y los cambios en 'articles' actualicen la UI.
import { ref } from 'vue'; // Importa ref si no lo has hecho

const articles = ref([]); // Inicializamos como un array vacío

// Puedes simular que obtienes los artículos de algún lugar (API, archivo, etc.)
// Por ejemplo, con datos de prueba:
articles.value = [
  { slug: 'mi-primer-post', title: 'Mi Primer Post', description: 'Una descripción genial', author: 'Juan', date: '2023-01-01' },
  { slug: 'segundo-articulo', title: 'Segundo Artículo', description: 'Más contenido interesante', author: 'Maria', date: '2023-02-15' },
  { slug: 'nuxt-es-genial', title: 'Nuxt es Genial', description: 'Aprendiendo mucho con Nuxt', author: 'Pedro', date: '2023-03-20' },
];

// O si quisieras cargar datos asíncronamente (muy común en Nuxt):
// const { data: articles } = await useAsyncData('articles', () => $fetch('/api/articles'));
// Esto es para casos más avanzados con APIs.

</script>

<style lang="scss" scoped> /* Agregué 'scoped' para que los estilos sean locales */
.container {
  @apply m-auto;
}
/* Corregí el selector '.container .content' a '.container .contents' para que coincida con tu HTML */
.container .contents { 
  @apply flex flex-col justify-center items-center sm:p-2 md:p-4 lg:p-8 xl:p-16;
  main {
    @apply max-w-5xl grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6;
  }
}
</style>