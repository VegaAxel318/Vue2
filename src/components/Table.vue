<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <v-table>
      <thead>
        <tr>
          <th class="text-left">
            Autor
          </th>
          <th class="text-left">
            Titulo
          </th>
          <th class="text-left">
            Post
          </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="item in dataFull"
          :key="item.userId"
        >
          <td>{{ item.Autor }}</td>
          <td>{{ item.Titulo }}</td>
          <td>{{ item.Post }}</td>
        </tr>
      </tbody>
    </v-table>
  </template>

<script setup>
import { ref, onMounted } from 'vue';

const urlPosts = "https://jsonplaceholder.typicode.com/posts";
const urlAutores = "https://jsonplaceholder.typicode.com/users";
const dataFull = ref([]);

onMounted(async () =>
{
  try
  {
    const responsePosts = await fetch(urlPosts);
    const dataPosts = await responsePosts.json();

    const responseAutores = await fetch(urlAutores);
    const dataAutores = await responseAutores.json();

    const mergedData = dataPosts.map(post =>
    {
      const autor = dataAutores.find(autor => autor.id === post.userId);
      return {
        Autor: autor.name,
        Titulo: post.title,
        Post: post.body};
    });
    dataFull.value = mergedData;
  }
  catch (error)
  {
    console.error("Error al obtener los datos:", error);
  }
});
</script>