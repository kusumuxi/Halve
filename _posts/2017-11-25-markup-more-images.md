---
layout: post
title: "标记：图像的另一个职能"
excerpt: "用于在帖子中显示图像的示例和代码。"
image: "http://farm9.staticflickr.com/8426/7758832526_cc8f681e48_c.jpg"
tags: 
  - 标记
  - 图像
  - 学习笔记
  - 职能
---

下面是一些图片文章的例子。如果你想显示两个或三个图像相邻的响应地使用`figure`适当的`class`。每个实例都`figure`被自动编号并显示在标题中。

### 数字 (用于图像或视频)

#### 一张：

<figure>
	<a href="http://farm9.staticflickr.com/8426/7758832526_cc8f681e48_b.jpg"><img src="http://farm9.staticflickr.com/8426/7758832526_cc8f681e48_c.jpg"></a>
	<figcaption><a href="http://www.flickr.com/photos/80901381@N04/7758832526/" title="Morning Fog Emerging From Trees by A Guy Taking Pictures, on Flickr">在Flickr拍摄的从树上冒出的晨雾。</a>.</figcaption>
</figure>


#### 两张：

`half` 像这样应用这个类，并排显示两个共享相同标题的图像。

```html
<figure class="half">
    <a href="/images/image-filename-1-large.jpg"><img src="/images/image-filename-1.jpg"></a>
    <a href="/images/image-filename-2-large.jpg"><img src="/images/image-filename-2.jpg"></a>
    <figcaption>Caption describing these two images.</figcaption>
</figure>
```

你会得到像这样的东西：

<figure class="half">
	<a href="http://placehold.it/1200x600.JPG"><img src="http://placehold.it/600x300.jpg"></a>
	<a href="http://placehold.it/1200x600.jpeg"><img src="http://placehold.it/600x300.jpg"></a>
	<figcaption>Two images.</figcaption>
</figure>

#### 三张：

 `third` 像这样应用这个类，并排显示三个共享相同标题的图像。
 
```html
<figure class="third">
	<img src="/images/image-filename-1.jpg">
	<img src="/images/image-filename-2.jpg">
	<img src="/images/image-filename-3.jpg">
	<figcaption>Caption describing these three images.</figcaption>
</figure>
```

你会得到像这样的东西：

<figure class="third">
	<img src="http://placehold.it/600x300.jpg">
	<img src="http://placehold.it/600x300.jpg">
	<img src="http://placehold.it/600x300.jpg">
	<figcaption>三张图像</figcaption>
</figure>

### 另一种方式

另一种达到相同结果的方法是包含`gallery`Liquid模板。在这种情况下，您不必编写任何HTML标记 - 只需复制一小段代码，调整参数（请参阅下面的内容），并使用任意数量的图像链接填充该块。您可以混合相关和外部链接。

以下是您可能要使用的模块：

{% highlight liquid %}
{% raw %}
{% capture images %}
	http://placehold.it/600x300.jpg
	http://placehold.it/600x300.jpg
	http://placehold.it/600x300.jpg
{% endcapture %}
{% include gallery images=images caption="Test images" cols=3 %}
{% endraw %}
{% endhighlight %}

参数：

- `caption`: 设置图库下的标题（请参阅`figcaption`上面的HTML标签）;
- `cols`:设置图库的列数。可用值: [1..3].

它看起来像这样：

{% capture images %}
	http://placehold.it/600x300.jpg
	http://placehold.it/600x300.jpg
	http://placehold.it/600x300.jpg
{% endcapture %}
{% include gallery images=images caption="测试图像" cols=3 %}
