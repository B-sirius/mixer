<template>
  <div class="keyboard">
    <div class="bpm">
      <span class="text">Tempo: {{bpm}} BPM</span>
      <input v-model="bpm" class="range" type="range" min="30" max="240">
    </div>
    <div class="row" v-for="tone in toneList" :key="tone.name">
      <div class="effect-name">{{tone.name}}</div>
      <a href="javascript:" class="key" v-for="demiquaver in demiquaverList" :key="demiquaver">{{demiquaver}}</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "Keyboard",
  props: {
    msg: String
  },
  data: function() {
    return {
      toneList: [
        {
          name: "Open Hat"
        },
        {
          name: "Closed Hat"
        }
      ],
      demiquaverList: Array.from({ length: 16 }, (val, key) => key),
      bpm: 100,
    };
  },
  computed: {}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.keyboard {
  width: 70%;
  grid-template-columns: 124px 1fr 1fr 1fr;
  background: #fff;
  .bpm {
    display: flex;
    line-height: 50px;
    background: rgb(209, 209, 209);
    margin-bottom: 2px;
    .text {
      font-size: 14px;
      box-sizing: border-box;
      flex-basis: 124px;
    }
    .range {
      flex-grow: 1;
      margin: 0 20px;
    }
  }
  .row {
    height: 50px;
    display: flex;
    margin-bottom: 2px;
    &:last-child {
      margin-bottom: 0;
    }
    .effect-name {
      line-height: 50px;
      flex-basis: 124px;
      background: rgb(236, 236, 236);
      margin-right: 2px;
    }
    .key {
      line-height: 50px;
      flex-grow: 1;
      background: rgb(236, 236, 236);
      margin-right: 2px;
      &:last-child {
        margin-right: 0;
      }
    }
  }
}
</style>
