<template>
  <section class="plugins-widget-header">
    <div class="content-pad">
      <div class="header-content">
        <div v-if="image" class="header-image">
          <img :src="image" :alt="title" />
        </div>
        <div>
          <h1 class="page-title">{{ title }}</h1>
          <div class="page-title-sub">
            <slot name="subtitle"/>
          </div>
        </div>
      </div>
      <div class="header-figure">
        <slot name="figure"/>
      </div>
    </div>
  </section>
</template>
<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    image: { type: String, default: "" },
    title: { type: String, default: "", required: true }
  }
})
</script>
<style lang="less">
.plugins-widget-header {
  overflow: hidden;
  border-top: 1px solid rgba(0, 0, 0, 0.04);
  border-bottom: 1px solid rgba(0, 0, 0, 0.04);

  .content-pad {
    display: grid;
    grid-template-columns: 4fr 3fr;
  }

  .header-content {
    padding: 8em 0;

    .page-title {
      font-size: 2.5em;
      line-height: 1.1;
      font-weight: 500;
      letter-spacing: -0.03em;
      text-transform: capitalize;
    }
    .page-title-sub {
      font-size: 1.6em;
      opacity: 0.7;
    }
    @media (max-width: 900px) {
      padding: 3rem 0;
      .page-title {
        font-size: 2.4rem;
        line-height: 1.3;
      }
      .page-title-sub {
        font-size: 1.4rem;
        line-height: 1.3;
      }
    }
  }

  .header-figure {
    position: relative;
  }

  @media (max-width: 900px) {
    .content-pad {
      grid-template-columns: 1fr;
    }
  }
}
</style>
