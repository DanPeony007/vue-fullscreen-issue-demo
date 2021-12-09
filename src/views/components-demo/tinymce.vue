<template>
  <div class="components-container">
    <el-button style="margin-bottom:10px" type="primary" @click="onFullscreen">vue-fullscreen 全屏</el-button>
    <div class="document-wrapper">
      <el-select v-model="value" placeholder="请选择" style="margin-bottom:10px">
        <el-option
          v-for="item in options"
          :key="item.value"
          :label="item.label"
          :value="item.value"
        />
      </el-select>
      <div>
        <tinymce v-model="content" :height="300" />
      </div>
      <div class="editor-content" v-html="content" />
    </div>
  </div>
</template>

<script>
import Tinymce from '@/components/Tinymce'

export default {
  name: 'TinymceDemo',
  components: { Tinymce },
  data() {
    return {
      content: `<h1 style="text-align: center;">Welcome to the TinyMCE demo!</h1><p style="text-align: center; font-size: 15px;"><img title="TinyMCE Logo" src="//www.tinymce.com/images/glyph-tinymce@2x.png" alt="TinyMCE Logo" width="110" height="97" /><ul>
        <li>Our <a href="//www.tinymce.com/docs/">documentation</a> is a great resource for learning how to configure TinyMCE.</li><li>Have a specific question? Visit the <a href="https://community.tinymce.com/forum/">Community Forum</a>.</li><li>We also offer enterprise grade support as part of <a href="https://tinymce.com/pricing">TinyMCE premium subscriptions</a>.</li>
      </ul>`,
      fullscreen: false,
      options: [
        {
          value: '选项1',
          label: '黄金糕'
        },
        {
          value: '选项2',
          label: '双皮奶'
        },
        {
          value: '选项3',
          label: '蚵仔煎'
        },
        {
          value: '选项4',
          label: '龙须面'
        },
        {
          value: '选项5',
          label: '北京烤鸭'
        }
      ],
      value: ''
    }
  },
  methods: {
    onFullscreen() {
      this.$fullscreen.toggle(this.$el.querySelector('.document-wrapper'), {
        wrap: false,
        // teleport 设置为 true 时，左侧菜单栏遮挡，tinymce 内容丢失
        // teleport 设置为 false 时，下拉框，popover、drawer等打不开
        teleport: true,
        callback: this.fullscreenChange
      })
    },
    fullscreenChange(fullscreen) {
      this.fullscreen = fullscreen
    }
  }
}
</script>

<style scoped>
.editor-content {
  margin-top: 20px;
}
/* 避免左侧菜单栏压住全屏元素 */
.document-wrapper.fullscreen {
  z-index: 1002;
}
</style>

