# 根路径（root:）

除了相对路径，我们还支持根路径写法，以src 为根路径，src/img/cat.png 可以写成root:img/cat.png

使用场景：

1.相对路径层级太深，难写难读的时候，比如src/dir1/dir2/dir3/dir4/demo.vue 里面要访问src/img/cat.png，这时候相对路径是这样../../../img/cat.png,写成根路径就是root:img/cat.png

2.当前vue作为组件的时候，这时候计算相对路径是以宿主页面为当前路径，这时候会导致路径计算错误，这种情况**必须**使用根路径写法

和路径相关的都会标注是否支持此写法

