<template>
  <div class="mt-10 text-3xl mx-auto max-w-6xl">
    <div>Name: host</div>
    <div>Framework: vue3</div>
    <Counter />
    <div class="bg-sky-600">
      <input type="file" @change="handleFileChange" />
      <p>Archivo seleccionado: {{ selectedFile ? selectedFile.name : 'Ningún archivo seleccionado' }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
import ref from "vue";

const fileInput = ref();
const handleFileChange = (event) => {
  const file = event.target.files[0]; // Obtiene el primer archivo seleccionado

  if (file) {
    this.selectedFile = file; // Asigna el archivo seleccionado a la variable
    // Aquí puedes realizar cualquier acción adicional con el archivo seleccionado, como enviarlo a una API, procesarlo, etc.
  } else {
    this.selectedFile = null; // Si no se selecciona ningún archivo, establece la variable en null
  }
};

// import Counter from "remote/Counter";
</script>
