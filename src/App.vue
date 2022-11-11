<template>
  <appEmojiPicker :native="true" @select="onSelectEmoji" />
</template>

<script>
import EmojiPicker from 'vue3-emoji-picker';
import 'vue3-emoji-picker/css';

import { ref } from 'vue';

export default {
  name: 'EmojiPicker',
  emits: ['select'],
  components: {
    appEmojiPicker: EmojiPicker,
  },
  setup() {
    const input = ref('');

    function onSelectEmoji(emoji) {
      console.log(emoji);
      input.value += emoji.i;
    }

    function showEmoji(emoji) {
      console.log(emoji);
    }

    return {
      input,
      onSelectEmoji,
    };
  },
};
</script>
