## 1.3.5 (2016-12-23)
* 修复了升级1.3.3导致旧项目报`id is not defined`的错误。
* 发布过程中加入了LF强制转换逻辑，确保MAC在更新后不会出现`env: node\r: No such file or directory`的错误。
* 修复了用`<component>`时，导致样式丢失的问题。
* 修复了用`<component>`时，props不工作的问题。
* 更新了`wepy-wechat-demo`使用自定义component与props，并添加toast组件。

## 1.3.3 (2016-12-22)
* 修复了config使用单引号导致解析出错的问题。感谢[@Lxxyx]()
* 支持自定义组件标签，`<component id="mycom" path="mycom"></component>` 优化为 `<mycom></mycom>`。
* 新增props传值功能，支持静态传值如 `num="50"` 或者绑定传值如 `v-bind:num="parentnum"`，使用方式基于与[Vue Props传值](https://vuejs.org.cn/guide/components.html#Props)一致。
* 修复了组件支持事件传参，但页面不支持的问题。


## 1.3.2 (2016-12-19)
* 修复wx:else, scroll-x等boolean属性报warning的[问题](https://github.com/wepyjs/wepy/issues/5)。
* 修复了组件method不存在时，mixin的method不会被注册的BUG。感谢[@huike1989]()。
* 修复了引用第三方组件路径报错的BUG。感谢[@huike1989]()。

## 1.3.1 (2016-12-16)
* 新增对第三方Compiler的支持。
* 新增pug编译器。
* 重新整理代码结构，使用lerna维护不同的NPM包。
* 重新处理Plugins，同样交由第三方包处理。
* 添加了编译时检测依赖的Compiler或者Plugins是否缺失的逻辑，如果缺失会自行安装。
* 添加了cli工具版本检测的功能。

*老版本在升级1.3.1版本时，要修改`wepy.config.js`并且添加compilers属性，并且安装对应的编译器方可使用。[参考这里](https://github.com/wepyjs/wepy#wepyconfigjs-配置文件说明)*


## 1.1.9 (2016-12-14)
* 新增了wepy upgrade命令升级wepyjs版本。
* 新增对第三方组件的支持。
* 新增第三方组件[wepy-com-toast](https://github.com/wepyjs/wepy-com-toast)。
* 模板中添加toast组件测试。


## 1.1.8 (2016-12-08)
* 修复了script使用src外链报错的BUG。
* 修复了LESS编译会调用到SASS的BUG。
* 优化了事件传参数，支持直接传参。详情[参考文档](https://github.com/wepyjs/wepy#2-优化事件参数传递)。
* 加入了Travis-CI以及Coveralls。
* 修复其它细节BUG问题

## 1.1.7 (2016-12-06)
* script/template/style的属性同时支持type和lang。
* 添加mixins支持，详情请[参考文档](https://github.com/wepyjs/wepy#混合)。

## 1.1.6 (2016-12-02)
* 修复了组件ID大写导致无法识别的问题。
* 添加了对小程序页面所有响应事件的支持。
* 修改wepy.config.js支持plugins。
* 添加UglifyJsPlugin，在编译时对生成的所有JS文件进行压缩。
* 添加ImageMinPlugin(不推荐使用，处理大图片时还有问题)，
* 添加`wepy build --no-cache`参数，编译时会重新编译所有依赖文件。
* `wepy new demo`时，由在当前目录下生成项目改为创建demo目录，然后再生成项目。
* 更新生成demo支持最新功能。

## 1.1.4 (2016-12-01)

* 添加了小程序其它页面事件的支持
* 修改默认配置文件.wepyrc为wepy.config.js，方便以后功能扩展。（兼容老配置文件）

## 1.1.3 (2016-11-28)

* 修复SASS编译异常导致watch结束的BUG
* 修复子组件修改时不会触发父组件更新的BUG
* 修复`$invoke('../')`的BUG
* 修复页面onLoad事件中传参的BUG

## 1.1.1 (2016-11-23)

* 添加了对sass/scss的编译支持
* .wepyrc中加入对less/sass的配置支持
* .wepyrc中添加`wpyExt`选项
* 更新生成模板
