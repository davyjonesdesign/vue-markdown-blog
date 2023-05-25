<template>
  <div class="home page">
    <div class="headline">
      <h1 class="center">Davy Jones' Locker</h1>
      <p class="center">A web designer's blog about the ins and outs of designing for the web.</p>
    </div>
    <div class="sections">
      <div v-for="(section, index) in Object.keys(entries)" :key="index" class="group">
        <h2 class="center">{{section}}</h2>
        <div class="section" v-for="entry in entries[section]" :key="entry.id">
          <div class="entry" @click="$router.push({name: entry.id}); scrollToTop();">
            <div class="img-wrapper">
              <img :src="entry.image" :alt="entry.title"/>
            </div>
            <div class="entry-content">
              <h3>
              {{entry.title}}
              </h3>
              <h6 class="subtitle">{{entry.date}}</h6>
              <p>{{entry.description}}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BLOGENTRIES from '@/statics/data/blogs.json'

export default {
  name: 'home',
  computed: {
    entries() {
      return BLOGENTRIES
    }
  },
  methods: {
    scrollToTop() {
      window.scrollTo(0, 0);
    },
  },
}
</script>
<style lang="scss" scoped>
@import '@/styles/main.scss';

.center {
  text-align: center;
}
.headline {
  padding: 30vh 4rem 4rem;
  margin: 0;
  background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.25), rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.9)), url('../assets/davy-jones-locker.jpg');
  background-size: cover;
  border-bottom: 1px solid $outline;
  color: $text;
  position: sticky;
  top: 0;
  & p {
    margin: auto;
  }
}
img {
  display: block;
  margin: 0 auto;
  height: 100%;
}
.img-wrapper {
  min-width: 150px;
  overflow: hidden;
}

h2 {
  color: $sub-text;
  // text-transform: capitalize;
  margin-bottom: 2rem;
}

h3 {
  color: $heavy;
  margin-bottom: 0;
  cursor: pointer;
  &:hover {
    text-decoration: underline;
  }
}
.subtitle {
  color: $sub-text;
  font-size: .98rem;
  margin: 5px 0 15px;
  font-weight: normal;
  text-transform: uppercase;
}

p {
  margin-top: .4rem;
}

.sections {
  width: 100%;
  margin: 0 auto;
  padding-top: 4rem;
  background: $off;
  z-index: 10;
}

.section {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-bottom: 3rem;
}

.group {
  margin-bottom: 4rem;
  z-index: 100;
  & h2 {
    position: sticky;
    top: 0;
    padding: 20px 0 18px;
    background: $off;
    margin: 0;
  }
}
.entry {
  background: $menuBack;
  max-width: 60vw;
  border-radius: $border-radius;
  transition: $transition;
  overflow: hidden;
  display: flex;
  border: 1px solid $outline;
  cursor: pointer;
  &:hover {
    transform: translate(-3px, -3px);
    transition: $transition-fastest;
    box-shadow: 3px 3px 2px $menuBack;
    border-color: $heavy;
  } &:hover h3 {
    text-decoration: underline;
    transition: $transition-fastest;
    color: $text;
  }
}
.entry-content {
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: center;
  margin: 0 40px 0 30px;
  & h3 {
    margin-top: 10px;
  }
  & p {
    margin: 0 0 20px;
  }

}
.back-link {
  display: none;
}
@import '@/styles/media.scss';
</style>