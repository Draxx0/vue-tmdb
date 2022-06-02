<script>
import FilmsList from "./FilmsList.vue";
export default {
  name: "FormContact",
  data() {
    return {
      credentials: {
        title: "",
        duration: "",
        average: "",
      },

      filmsList: [],
    };
  },
  methods: {
    handleSubmit() {
      this.filmsList.push(this.credentials);
      this.credentials = {
        title: "",
        duration: "",
        average: "",
      };
    },
  },
  components: { FilmsList },
};
</script>

<template>
  <form @submit.prevent="handleSubmit">
    <input
      type="text"
      placeholder="Titre du film"
      v-model="credentials.title"
    />
    <input
      type="text"
      placeholder="Durée du film"
      v-model="credentials.duration"
    />
    <input
      type="text"
      placeholder="Note moyenne"
      v-model="credentials.average"
    />
    <input type="submit" value="Envoyer" />
  </form>

  <FilmsList :filmsList="filmsList" />
</template>

<style>
form {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  margin: 0 auto;
}
input {
  padding: 10px;
  outline: none;
  border: none;
  border-bottom: 1px solid black;
  transition: 0.5s ease-in-out;
}

input[type="submit"] {
  background: rgb(63, 233, 77);
  color: white;
  font-weight: bold;
  cursor: pointer;
  border: none;
  margin: auto;
  padding: 10px 20px;
  border-radius: 50px;
  font-size: 1.2rem;
  transition: 0.2s;
}

input[type="submit"]:hover {
  transform: scale(1.05);
}

input::placeholder {
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  font-weight: bold;
}

input:valid {
  border-color: green;
}

input:invalid {
  border-color: red;
}
</style>

<script></script>
