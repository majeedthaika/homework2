<template>
  <div class="post">
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <span v-if="post.user"><i class="el-icon-information"></i> {{ post.user.email }}</span>
        <i class="el-icon-more" style="float: right;" ></i>
      </div>
      <div class="text item">{{ post.content }}</div>
    </el-card>
  </div>
</template>

<script>

export default {
  name: 'post',
  props: {
    post: {
      type: Object,
      required: false,
      default: {}
    }
  }
}
</script>

<style scoped>

</style>
