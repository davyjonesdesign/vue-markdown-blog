<template>
  <div class="home page">
    <div class="headline">
      <h1 class="center">Davy Jones'<br><span class="locker">Locker</span></h1>
      <p class="center">Another graphic and web design blog.</p>
      <DownArrow />
    </div>
    <div class="sections" id="sections">
      <div v-for="(section, index) in Object.keys(entries)" :key="index" class="group">
        <h5 class="center">{{section}}</h5>
        <div class="section" v-for="entry in entries[section]" :key="entry.id">
          <div class="entry" @click="$router.push({name: entry.id}); scrollToTop();">
            <div class="img-wrapper">
              <img :src="entry.image" :alt="entry.title"/>
            </div>
            <div class="entry-content">
              <div class="entry-sub">
                <h6 v-if="entry.week" class="subtitle">Week {{entry.week}}</h6>
                <h6 v-if="entry.type" class="subtitle">{{entry.type}}</h6>
              </div>
              <h3>
              {{entry.title}}
              </h3>
              <p>{{entry.subtitle}}</p>
              <div class="entry-sub">
                <p class="entry-date">{{entry.date}}</p>
              </div>
              
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BLOGENTRIES from '@/statics/data/blogs.json';
import DownArrow from '@/components/DownArrow.vue';

export default {
  name: 'home',
  components: {
    DownArrow
  },
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
  padding: 30vh 4rem 2rem;
  margin: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.25), rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.9)), url('../assets/davy-jones-locker.jpg');
  background-size: cover;
  background: $egg;
  color: $charcoal;
  position: sticky;
  top: 0;
  & h1 {
    font-weight: 700;
    font-size: 1.25rem;
    letter-spacing: 15px;
    text-transform: uppercase;
  }
  & p {
    margin: auto;
  } & .locker {
    font-family: "Merriweather";
    color: $burn;
    font-size: 6rem;
    font-weight: 500;
    text-transform: capitalize;
    letter-spacing: 3px;
    line-height: 4rem;
  }
}
img {
  display: block;
  margin: 0 auto;
  height: 250px;
  // max-height: 300px;
}
.img-wrapper {
  max-width: 175px;
  height: auto;
  overflow: hidden;
  display: flex;
    align-items: center;
    justify-content: center;
}

h3 {
  font-family: "Merriweather";
  color: $burn;
  font-size: 1.5rem;
  font-weight: 600;
  text-transform: capitalize;
  letter-spacing: 1px;
  line-height: 2rem;
}
.subtitle {
  color: $charcoal;
  font-size: .85rem;
  padding: 5px 10px 3px;
  border-radius: 3px;
  letter-spacing: 2px;
  background: $egg;
  border: 1px solid $charcoal;
  margin: 5px 10px 5px 0;
  font-weight: 600;
  border-radius: 20px;
  text-transform: uppercase;
}

p {
  margin-top: .4rem;
  line-height: 1.5rem;
}

.sections {
  width: 100%;
  margin: 0 auto;
  // padding-top: 4rem;
  background: $tan;
  border-top: 1px solid $charcoal;
  z-index: 10;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.group {
  margin-bottom: 30px;
  z-index: 100;
  display: flex;
  flex-direction: column;
  align-content: center;
  & h5 {
    display: inline-block;
    color: $charcoal;
    padding: 14px 6px 12px;
    position: sticky;
    top: 0;
    font-weight: 800;
    text-transform: uppercase;
    letter-spacing: 6px;
    font-size: 1rem;
    background: $tan;
    min-width: 200px;
    margin: 30px 0 1px;
  }
}
.entry {
  background: $egg;
  max-width: 60vw;
  border-radius: 0;
  margin: 0 0 10px;
  transition: $transition;
  overflow: hidden;
  // height: 250px;
  display: flex;
  border: 1px solid $charcoal;
  cursor: pointer;
  &:hover {
    transform: translate(-4px, -2px);
    transition: $transition-fastest;
    box-shadow: 4px 5px 2px $charcoal;
    background: $tan;
    border-color: $charcoal;
    border-radius: $border-radius;
  } &:hover h3 {
    text-decoration: underline;
    transition: $transition-fastest;
    // color: $charcoal;
  } &:hover .subtitle {
    // color: $burn;
  }
}
.entry-content {
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: center;
  margin: 0 40px 0 30px;
  padding: 10px 0;
  & h3 {
    margin: 10px 0;
  }
  & p {
    margin: 0 0 15px;
  }
  & .entry-sub {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
  }
  & .entry-date {
    color: $charcoal;
    font-size: .875rem;
  }
}
.back-link {
  display: none;
}
@import '@/styles/media.scss';
</style>