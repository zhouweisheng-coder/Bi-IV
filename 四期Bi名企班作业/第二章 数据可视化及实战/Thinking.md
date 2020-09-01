# Thinking1  MVC框架指的是什么      能简要说出MVC框架的内容（20points） 

* Model

  与数据库相关的模型层，是应用程序中用于处理应用程序数据逻辑的部分。
  通常模型对象负责在数据库中存取数据。

* Views

  网页的地址，以及渲染网页等，是应用程序中处理数据显示的部分。
  通常视图是依据模型数据创建的。

* Controller

  访问网页地址后，读取页面数据，调用业务逻辑。是应用程序中处理用户交互的部分。
  通常控制器负责从视图读取数据，控制用户输入，并向模型发送数据。

# Thinking2  基于Python的可视化技术都有哪些，你使用过哪些      分享自己使用过的工具（20points）

* python可视化技术有matplotlib，seaborn，词云展示、决策树可视化Graphviz、pyecharts、Bokeh、图可视化networkx、地学geoplotlib、web交互式可视化等
* 自己常用的工具主要是matplotlib和seaborn，是数据分析最常用的可视化工具。Matplotlib是可以实现高度定制化绘图的，高度定制化可以让你获得最符合心意的可视化输出结果，但也因此需要设置更多的参数。Seaborn的底层是基于Matplotlib的，将可视化绘图过程进行了函数封装，相比Matplotlib的好处是代码更简洁。

