<template>
    <div>
      <header>
        <h1>Mi Increíble Aplicación Nuxt</h1>
        <nav>
          <NuxtLink to="/">Inicio</NuxtLink> |
          <NuxtLink to="/about">Acerca de</NuxtLink>
        </nav>
      </header>
  
      <NuxtPage /> 
  
      <footer>
        <p>&copy; {{ new Date().getFullYear() }} Mi App Nuxt</p>
      </footer>
    </div>
  </template>
  
  <script setup>
  // Aquí no necesitas export default {}
  // Si quisieras un "name" para el componente (menos común en app.vue),
  // podrías usar el macro defineOptions (si lo necesitas, lo cual no es usual para app.vue).
  // Pero para un app.vue, simplemente deja el script setup vacío si no hay lógica específica.
  
  // Por ejemplo, si necesitaras el año actual en el script:
  const currentYear = new Date().getFullYear(); 
  // Este 'currentYear' ya estaría disponible en el template.
  </script>
  
  <style>
  /* Estilos globales para toda la aplicación */
  body {
    margin: 0;
    font-family: sans-serif;
    background-color: #f4f4f4;
  }
  
  header {
    background-color: #333;
    color: white;
    padding: 1rem;
    text-align: center;
  }
  
  nav a {
    color: white;
    margin: 0 10px;
    text-decoration: none;
  }
  
  footer {
    text-align: center;
    margin-top: 2rem;
    padding: 1rem;
    background-color: #eee;
  }
  </style>