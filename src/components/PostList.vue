<template>
  <div class="post-list">
    <hr class="line" />
    <div v-if="language === 'en'">
      <p class="date">Part {{ post.order }}</p>
    </div>
    <div v-else>
      <p class="date">Parte {{ post.order }}</p>
    </div>
    <g-link :to="post.path" class="headerLink">
      <h1 class="title" v-html="post.title" />
    </g-link>
    <!-- <p class="description" v-html="post.description" /> -->
    <div v-if="language === 'en'">
      <b>{{post.timeToRead}} min read</b> &nbsp;
      <g-link :to="post.path" class="read">Read More...</g-link>
    </div>
    <div v-else>
      <b>Lectura {{post.timeToRead}} min</b> &nbsp;
      <g-link :to="post.path" class="read">Leer mas...</g-link>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: Object,
    language: String
  }
};
</script>

<style>
.line {
  border: 0.5px solid rgb(28, 70, 107);
  margin: 30px 0;
}

.date {
  font-weight: 300;
}

.read {
  padding: 7px;
  color: #333;
  text-decoration: underline;
  text-decoration-color: hsl(208, 59%, 26%);
}

a.headerLink {
  color: #333;
  text-decoration: none;
}

a.headerLink:hover {
  text-decoration: underline;
}

.read:hover {
  background-color: hsl(208, 59%, 20%);
  border-radius: 10px;
  color: whitesmoke;
  text-decoration: none;
}
</style>
