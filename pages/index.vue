<template>
  <section class="section">
    <div class="hero is-danger">
      <div class="hero-body">
        <div class="container">
          <h1 class="title is-1">러버독</h1>
          <h2 class="subtitle">Alphadog has a Megalomaniac</h2>
        </div>
      </div>
    </div>
    <br>
    <article class="message">
      <div class="message-header">what is dog</div>
      <div class="message-body">데꿀데굴멍멍왈왈 개정보는 https://dog.ceo/dog-api/documentation/</div>
    </article>
    <div class="columns">
      <div class="column">
        <div class="notification is-info">
          <figure class="image is-squre">
            <img src="https://i.ytimg.com/vi/SfLV8hD7zX4/maxresdefault.jpg" alt>
          </figure>
        </div>
      </div>
      <div class="column">
        <div class="message is-info">
          <div class="message-header">
            <p>today's canine</p>
          </div>
        <div class="message-body">
      <figure class="image is-squre">
        <img alt v-bind:src="image">
      </figure>
          </div>
        </div>
      </div>
    </div>
    <div class="box">
      <h1 class="title">Dog list</h1>
      <span v-for="dog in dogs" v-bind:key="dog"></span>
      <a class="button is-success is-rounded" href="#">
        {{dog}}
      </a> &nbsp;
    </div>
  </section>
</template>

<script>
    import axios from 'axios';
    export default {
      data() {
        return {};
      },
      async asyncData() {
        const myImage = await axios.get('https://dog.ceo/api/breeds/image/random');
        const myDogs = await axios.get('https://dog.ceo/api/breeds/list/all');
        return { image: myImage.data.message, dogs: myDogs.data.message};
      }
    };
  </script>
