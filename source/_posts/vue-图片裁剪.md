---
title: vue 图片裁剪
date: 2019-12-12 20:05:50
tags:
  - 菜鸡互啄
category:
  - vue
---

公司项目中移动端用到的图片需要固定比例，在后台添加数据时需要对图片进行裁剪，这里推荐使用`vue-cropperjs`（对Cropper.js进行再次的封装适用于vue）。

<!-- more -->

[vue-cropperjs官方地址](https://github.com/Agontuk/vue-cropperjs)

[vue-cropperjs 在线example](https://agontuk.github.io/vue-cropperjs/)

[Cropper.js官方地址](https://github.com/fengyuanchen/cropperjs#crop)

### 安装`vue-cropperjs`

```bash
npm install vue-cropperjs
```

### 使用

```js
// Global
import Vue from 'vue';
import VueCropper from 'vue-cropperjs';
import 'cropperjs/dist/cropper.css';
Vue.component(VueCropper);

// Local
import VueCropper from 'vue-cropperjs';
import 'cropperjs/dist/cropper.css';
export default {
  components: { VueCropper}
}

...
<vue-cropper
  ref="cropper"
  :src="imgSrc"
  alt="Source Image"
  :cropmove="cropImage"
>
</vue-cropper>
...
```

