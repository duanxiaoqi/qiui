<template>
  <p>
    {{ all ? text : shortText }}
    <span v-if="text.length > limit"  @click="all = !all">{{all ? hideTip : showTip}}</span>
  </p>
</template>

<script>
export default {
  name: 'omit-text',
  props: {
    text: {
      type: String,
      default: ''
    },
    limit: {
      type: Number,
      default: 70
    },
    color: {
      type: String,
      default: 'orange'
    },
    showTip: {
      type: String,
      default: '更多'
    },
    hideTip: {
      type: String,
      default: '收起'
    }
  },
  data () {
    return {
      all: false
    };
  },
  computed: {
    shortText () {
      return this.text.substr(0, this.limit);
    }
  }
};
</script>

<style lang="scss" rel="stylesheet/scss" scoped>
p {
  background: pink;
  span {
    color: plum;
  }
}
</style>