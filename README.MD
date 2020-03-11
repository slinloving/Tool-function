# 工作经常用的工具函数

## 数据校验 处理 if else 问题

### 数据不确定

```javascript
postShopAd() {
  const validateArray = [
    this.validateFn(this.storeAdItem.phone, '请输入手机号!'),
    this.validateFn(this.storeAdItem.address, '请输入商家地址!'),
    this.validateFn(this.storeAdItem.name, '请输入商家名称!'),
    this.validateFn(this.storeAdItem.adFile, '请上传店铺图片!')
  ]
  if (!validateArray.includes(false)) {
    this.$store.dispatch('PostCreateStore', this.storeAdItem)
  }
}
validateFn(value, msg) {
  if (!value) {
    this.$toast.fail(msg)
    return false
  } else {
    return true
  }
}
```

### 数据确定

```javascript
shop_icon(type) {
  const obj = {
    1: require('@/assets/image/my_icon.png'),
    2: require('@/assets/image/jd_icon.png'),
    3: require('@/assets/image/tb_icon.png'),
    4: require('@/assets/image/yz_icon.png'),
    5: require('@/assets/image/wd_icon.png')
  }
  return obj[type]
}
shop_text(type) {
  const obj = {
    1: '我的商品',
    2: '京东商品',
    3: '淘宝商品',
    4: '有赞商品',
    5: '微店商品'
  }
  return obj[type]
}
```
