<template>
  <div class="main">
    <div v-for="post in posts" class="blog">
      <h2>
        <router-link :to="post.path">{{post.frontmatter.title}}</router-link>
      </h2>
      <div v-for="tag in post.frontmatter.tags" class="blog-tag">{{tag}}</div>
      <div>{{post.frontmatter.date}}</div>
      <div class="description">{{post.frontmatter.description}}</div>
      <div>
        <router-link :to="post.path">Read More</router-link>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  computed: {
    posts() {
      console.log(this.$site);
      return this.$site.pages
        .filter(
          (page) => page.path.startsWith(`/tutorials/`) && page.title != "blogs"
        )
        .sort((a, b) => b.frontmatter.postId - a.frontmatter.postId);
    },
  },
};
</script>
<style lang="stylus">
.blog {
  padding: 2rem;
  background: white;
  margin-bottom: 3rem;
  background-image: linear-gradient(to right, #ff40af, #b330ff);
  color: black;
  border-image-slice: 1;
  border-radius: 10px;
}

.blog-tag {
  display: inline-block;
  margin: 0.3rem;
  padding: 0.2rem;
  border-radius: 10px;
  background: #8cecff;
  font-weight: bold;
}

.description {
  font-size: 1.5rem;
  margin-bottom: 1.5rem;
}

h2 {
  font-size: 2.1rem;

  a {
    color: #09269b;
    font-weight: 600;
  }
}
</style>