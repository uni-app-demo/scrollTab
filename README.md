# scrollTab
简单的uni-app功能demo，实现横向可滚动tab和对应切换对应数据的功能

# 技术注意点
*隐藏横向滚动条
*横向滚动的必要样式：white-space: nowwarp;
*两个text横向排列，其中一个text多余字符需要以省略号形式展示，使用flex布局，必须给每个text指定宽度外，还需使用justify-content:space-between;然后加上对应的隐藏显示省略号的样式，否则无法展示对应的样式
