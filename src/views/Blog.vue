<template>
  <div class="page">
    <div class="blog">
      <router-view />
      <UtterancesComments  />
      <BackButton class="back-btn" />
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
  max-width: 60vw;
  margin: 10rem auto 40px;
  display: flex;
  flex-direction: column;
  max-width: 600px;
  // align-items: flex-end;
  // padding-bottom: 3rem;

 /deep/ {
    h1 {
      font-family: "Merriweather";
      color: $burn;
      font-size: 2.25rem;
      font-weight: 900;
      // text-transform: capitalize;
      letter-spacing: 1px;
      line-height: 3rem;
    }
    pre {
      overflow-x: auto;
      background-color: $tan;
      border: 2px solid $burn;
      color: $burn;
      border-radius: .3rem;
      padding: 1rem;
    }
    img {
      max-width: 100%;
    }
  }
}
.back-btn {
  margin-bottom: 10rem;
}

@import '@/styles/media.scss';

</style>
