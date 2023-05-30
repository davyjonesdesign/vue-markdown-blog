<template>
  <div class="page">
    <div class="blog">
      <router-view />
      <!-- <router-link to="/" tag="a" class="back">&laquo; Back</router-link> -->
      <BackButton class="back-btn" />
      <UtterancesComments  />
    </div>
  </div>
</template>
<script>
import UtterancesComments from '@/components/UtterancesComments.vue';
import BackButton from '@/components/BackButton.vue';

export default {
  components: {
    UtterancesComments,
    BackButton,
  },
};
</script>

<style lang="scss" scoped>
@import '@/styles/main.scss';

.blog {
  max-width: 50vw;
  margin: 10rem auto;
  // display: flex;
  // flex-direction: column;
  // align-items: center;
  // padding-bottom: 3rem;

 /deep/ {
    h1 {
      font-family: "Merriweather";
      color: $blue-light;
      font-size: 3rem;
      font-weight: 500;
      text-transform: capitalize;
      letter-spacing: 3px;
      line-height: 4rem;
    }
    h4 {
      margin-bottom: 3rem;
      font-weight: 700;
      letter-spacing: 6px;
      font-weight: 900;
      color: $blue-dark;
    }
    pre {
      overflow-x: auto;
      background-color: $text-dark;
      border: 2px solid $blue-dark;
      color: $blue-light-2;
      border-radius: .3rem;
      padding: 1rem;
    }
    iframe {
      
    }
    img {
      max-width: 100%;
    }
  }
}
.back-btn {
  position: fixed;
  top: 8px;
  right: 10px;
}

@import '@/styles/media.scss';

</style>
