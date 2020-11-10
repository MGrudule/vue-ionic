<template>
  <div id="container">
    <strong>{{ name }}</strong>
    <p>
      Explore
      <a
        target="_blank"
        rel="noopener noreferrer"
        href="https://ionicframework.com/docs/components"
        >UI Components</a
      >
    </p>
    <button @click="count++" />
    <input v-model="book.title" />
    <div>{{ count }} {{ book.title }}</div>
  </div>
</template>

<script lang="ts">
import { ref, reactive, watchEffect, defineComponent } from "vue";
interface Book {
  title: string;
  author: string;
  year: number;
}
export default defineComponent({
  name: "ExploreContainer",
  props: {
    name: String,
  },
  data() {
    return {
      book: {
        title: "Vue 3 Guide",
        author: "Vue Team",
        year: 2020,
      } as Book,
    };
  },
  setup(props) {
    const count = ref(2);
    watchEffect(() => {
      console.log(`name is: ` + props.name);
    });
    // expose to template
    return {
      count,
    };
  },
});
</script>

<style scoped>
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  color: #8c8c8c;
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>