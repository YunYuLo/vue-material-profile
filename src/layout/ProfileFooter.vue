<template>
  <footer
    class="footer"
    :class="{ [`footer-${type}`]: type }"
    :data-background-color="backgroundColor"
  >
    <div class="container">
      <nav>
        <ul>
          <li>
            <a href="#">VIVIAN</a>
          </li>
          <li>
            <a href="https://www.cakeresume.com/s--1xGDbMhNbFwD1-7BQU2Nlw--/vivian-lo">Resume</a>
          </li>
          <li>
            <a href="https://medium.com/@yunyubee" target="_blank">Medium</a>
          </li>
          <li>
            <a href="https://www.linkedin.com/in/vivian-lo-2aba35184/" target="_blank">LinkedIn</a>
          </li>
        </ul>
      </nav>
      <div class="copyright">
        &copy; {{ year }}, made with
        <md-icon>favorite</md-icon>by
        Vivian
      </div>
    </div>
  </footer>
</template>
<script>
export default {
  props: {
    backgroundColor: String,
    type: String
  },
  data() {
    return {
      year: new Date().getFullYear()
    };
  }
};
</script>
<style></style>
