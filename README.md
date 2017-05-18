# UITableViewCellCustomHeightDemo
这是一个UITableView自动计算Cell高度的Demo.

应用了iOS 8 新增的estimatedRowHeight属性，但是这个方法必须使用autolayout，设置约束的时候必须注意每个控件在垂直方向上必须都有约束。
在写Demo的过程中，遇到一个问题，在 ShowImageView.swift 中的 func loadImage(array: [UIImage]) 方法内，动态创建显示图片，然后给每个图片添加约束，用的是第三方的SnapKit,创建UIImageView的时候如果给每个UIImageView设置了高度，就会报错，然后页面就会出现错乱。

后来查了很多资料发现在动态添加图片的时候不给图片设置 height 等于 某个值， 而是设置成 lessThanOrEqualTo 或者 greaterThanOrEqualTo 即可。
