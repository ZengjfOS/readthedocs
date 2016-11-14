# readthedocs

个人觉得这个主题挺符合个人习惯，于是对[Mkdocs](https://github.com/mkdocs/mkdocs/)的[readthedocs](https://github.com/mkdocs/mkdocs/tree/master/mkdocs/themes/readthedocs)主题进行修改定制，来符合自己的需求。在修改的过程中，参考[sphinx_rtd_theme](https://github.com/snide/sphinx_rtd_theme)主题中的处理方法，并且参考了如下文档：
  * [MkDocs 文档生成逻辑浅析](http://www.jianshu.com/p/c9410da484fb)
  * [Welcome to Jinja2](http://jinja.pocoo.org/docs/dev/)

## 主题添加Logo

  * 修改`css/theme.css`文件图片相关的CSS：  
    `.wy-side-nav-search img{display:block;height:45px;width:45px;margin:auto auto 0.809em auto;background-color:#2980B9;padding:5px;border-radius:100%}`  
    为  
    `.wy-side-nav-search img{display:block;height:100px;width:295px;margin:auto auto 0.809em auto;background-color:#2980B9;padding:5px;border-radius:0%`
  * 修改`base.html`，添加img标签添加图片：
```html
    <div class="wy-side-nav-search">
    {%- block site_name %}
    <a href="{{ nav.homepage.url }}" class="icon icon-home"> {{ config.site_name }}
    </a>
    {%- endblock %}
    <img src="{{ config.site_logo }}"/>
    {%- block search_button %}
    {% include "searchbox.html" %}
    {%- endblock %}
    </div>
```
  * 在mkdocs.yml中添加logo设置
```
    site_logo: images/os.png
```
  * 图片大小如下：
    * height: 100px;
    * width: 295px;

## 右侧内容区自适应浏览器宽度

  * 修改`css/theme.css`文件CSS：  
  `.wy-nav-content{padding:1.618em 3.236em;height:100%;max-width: 800px;margin:auto}`  
  为  
  `.wy-nav-content{padding:1.618em 3.236em;height:100%;argin:auto}`
