<template>
  <div style="position: relative">
    <v-carousel class="header" height="600" cycle hide-delimiters>
      <v-carousel-item
        :src="item.src"
        v-for="(item, i) in items"
        :key="i"
        cover
      />
    </v-carousel>

    <div class="header-text">
      <div class="header-text-heading text-center">
        <h1>Build A-Dream</h1>
        <p>Dream gardens that don't cost the earth</p>
      </div>

      <div class="d-flex justify-center mt-4">
        <v-btn variant="outlined" density="comfortable"> View our work </v-btn>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
export default defineComponent({
  name: "Header",
  setup() {
    const items = [
      {
        src: "/img/background.jpg",
      },
      {
        src: "/img/background.jpg",
      },
      {
        src: "/img/background.jpg",
      },
      {
        src: "/img/background.jpg",
      },
    ];

    return {
      items,
    };
  },
});
</script>

<style lang="scss">
.header {
  &-text {
    background: linear-gradient(180deg, #086500 0%, rgba(8, 101, 0, 0.8) 100%);
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    color: white;
    padding: 30px;
    z-index: 100;

    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 90%;
    max-width: 320px;

    &-heading {
      line-height: 30px;

      h1 {
        margin: 0;
        font-size: 36px;
        text-shadow: 2px 2px 4px rgb(30, 30, 30);
      }
    }

    p {
      font-size: 14px;
    }
  }

  .v-window__controls {
    .v-btn {
      background: none;
      color: white;
      box-shadow: none;

      @media (max-width: 769px) {
        position: absolute;
        bottom: 10px;

        &:nth-child(1) {
          left: 10px;
        }

        &:nth-child(2) {
          right: 10px;
        }
      }
    }
  }
}
</style>
