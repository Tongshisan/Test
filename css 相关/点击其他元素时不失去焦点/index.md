# 点击元素外部不失去焦点

假设点击 `test` 外的部分时不让 `test` 失去焦点

## 知道具体节点时

监听这个节点的 `mousedown` 事件, 阻止默认事件 `preventDefault`
```js
const div = document.getElementById('div');
div.addEventListener('mousedown', (e) => {
  e.preventDefault()
})
```


## 不知道具体节点时
监听 `body` 的 `mousedown` 事件, 判断 `target` 是否是 `test`, 不是则 阻止默认事件

```js
const input = document.getElementById('input');
document.body.addEventListener('mousedown', (e) => {
  console.log(e.target === input);
  if (e.target !== input) {
    e.preventDefault()
  }
})
```
