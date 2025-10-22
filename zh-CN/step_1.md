交叉观察器用于检测元素（例如 `<img>`，`<p>` 或 `<div>`）何时进入或离开用户的浏览器视口。

你还可以向观察器添加选项，例如设置阈值。

阈值范围从 `0` 到 `1`。

`1` 表示元素的每个像素都必须位于视口中才能运行回调。

`0` 是默认值，表示只需一个像素相交即可运行回调。

以下是 [动画故事](https://projects.raspberrypi.org/zh-CN/projects/animated-story) 项目（[更多 Web](https://projects.raspberrypi.org/zh-CN/raspberrypi/more-web) 路径的一部分）中的交叉观察器使用 `threshold` 的示例。

此示例中的选项 `threshold: 1` 表示仅当所有蜗牛图像都在视口中时才会触发回调。

--- code ---
---
language: js
filename: 
line_numbers: true
line_number_start: 1
line_highlights: 6
---

const snailObserver = new IntersectionObserver((entries) => {
  if (entries[0].isIntersecting) {
    entries[0].target.classList.add("startCrawl");
  }
},
{ threshold: 1 }
);
snailObserver.observe(document.querySelector("#snail"));

--- /code ---
