<script>
export default {
  methods: {
    isActive(path) {
      return window.location.pathname === path;
    }
  }
};
</script>
<template>
  <nav role="navigation" class="horinav">
    <ul>
      <li>
        <a :class="{ active: isActive('/') }" href="#">Home</a>
      </li>
      <li><a href="#">Sponsors</a></li>
      <li><a :class="{ active: isActive('/robots') }" href="#">Robots</a></li>
      <li>
        <p>Team <i class="fa-solid fa-caret-down"></i></p>
        <ul>
          <a href="#">
            <li>About</li>
          </a>
          <a href="#">
            <li>History</li>
          </a>
          <a href="#">
            <li>Join</li>
          </a>
        </ul>
      </li>
      <li><a href="#">Outreach</a></li>
    </ul>
  </nav>
</template>

<style scoped lang="scss">
@import "../assets/base.scss";

nav {
  display: block;
  width: max-content;
  height: 40px;
  font-size: 120%;
  font-weight: 300;

  ul {
    height: 100%;
    background: transparent;
    list-style: none;
    margin: 0;
    padding-left: 0;
    font-size: 120%;
    display: flex;
    gap: 10px;
    font-size: 90%;
  }

  li {
    width: 120px;
    height: 100%;
    color: inherit;
    background: transparent;
    display: block;
    position: relative;
    text-align: center;

    ul {
      height: auto;
      background: rgba($secondary, $alpha: 0.05);
      border-radius: 10px;
      width: 100%;
      position: absolute;
      transition: all 0.5s ease;
      left: 0;
      display: none;

      a:hover {
        background-color: rgba($secondary, $alpha: 0.2);
      }

      li {
        margin-left: 0px;
        clear: both;
        width: 90%;
        padding: 0.5em;
      }

    }
  }

  a,
  p {
    margin: 0;
    text-decoration: none;
    color: inherit;
    transition-duration: 0.5s;
    border-radius: 10px;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    outline: 0px solid $primary;
  }

  a:hover {
    transition: all 0.5s ease;
    background-color: rgba($secondary, $alpha: 0.2);
    outline: 1px solid $secondary;
  }

  a.active {
    color: white;
    background-color: $secondary;
  }
  
  i {
    position: absolute;
    right:25px;
    top:8px;
  }
}

ul li:hover>ul,
ul li:focus-within>ul,
ul li ul:hover,
ul li ul:focus {
  display: block;
  transition: all 1s ease;
}

@media screen and (max-width: 500px) {
  .horinav {
    margin: auto;
    clear: both;
  }

  header h2 {
    text-align: center;
    height: min-content;
    margin-left: auto;
  }
}
</style>
