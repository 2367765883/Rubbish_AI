<template>
  <div class="hm-talk-card">
    <div class="head">
      <div class="state">
        <div class="imghead">
          <image class="avator" :src="options.avator" />
          <text class="name">{{ options.name }}</text>
        </div>
        <image class="stateimg" :src="options.stateimg" />
      </div>
      <div class="main">
        <text class="text">{{ options.text }}</text>
      </div>
      <div class="body">
        <div class="block">
          <image class="iconfriendsHelp" :src="options.iconfriendsHelp" />
          <text class="num">{{ options.num }}</text>
          <text class="like">{{ options.like }}</text>
        </div>
        <div class="group">
          <image class="iconTest" :src="options.iconTest" />
          <text class="commentNum">{{ options.commentNum }}</text>
          <text class="comments">{{ options.comments }}</text>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'HmTalkCard',
  props: {
    dataId: {
      type: String,
      default: 'hm-talk-card'
    },
    options: {
      type: Object,
	  time:"2021-06-06"
    }
  },
  data() {
    return {
	};
  },
  methods: {}
};
</script>
<style>
@import './index.response.css';
</style>
