---
layout: post
title: "Javascript实现Map结构"
data: 2015-05-15
tag: [Javascript,算法]
category: [文章,技术,Javascript]
summary: "Javascript实现Map结构"
---
####Javascript实现Map结构。

{% highlight javascript %}
function Map(){

    var __struct__ = function(key,value){
        this.key = key;
        this.value = value;
    }

    var __map__  = new Array();


    this.put = function(key,value){
        for (var i = 0; i < __map__.length ; i++){
            if(__map__[i].key === key){
                __map__[i].value = value;
                return;
            }
        }

        __map__[__map__.length] = new __struct__(key,value);
    }

    this.get = function(key){
        for(var i=0; i<__map__.length;i++){
            if(__map__[i].key === key){
                return __map__[i].value;
            }
        }
        return null;
    }


    this.remove = function(key){
        for(var i=0; i<__map__.length;i++){
            if(__map__[i].key === key){
                var index = 0;
                if (i > 0){
                    index = i-1
                }
                __map__ = __map__.splice(index,1)
                return ;
            }
        }
        return ;
    }

    this.size = function(){
        return __map__.length
    }

    this.isEmpty = function(){
        return __map__ <= 0
    }

    this.keys = function(){
        var keys = [];
        for(var i=0; i<__map__.length;i++){
            keys[i] = __map__[i].key;
        }
        return keys
    }

    this.values = function(){
        var values = [];
        for(var i=0; i<__map__.length;i++){
            values[i] = __map__[i].value;
        }
        return values
    }
}

{% endhighlight %}

###实例：
1.创建一个'Map'对象
```javascript
var map = new Map();
```

2.在 'map' 对象里添加一个数据
```javascript
map.put('1','a');
map.put('2','b');  
map.put('3','c');
```

3.这个'map'的大小
```javascript
map.size();
3
```

4.获取 'key = 1' 的数据
```javascript
map.get('1');
"a"
```

5.删除 'key = 1' 的数据
```javascript
map.remove('1');
map.szie();
2
```

6.查看'map'对象是否空
```javascript
map.isEmpty();
false
```

7.得到所有的'key'
```javascript
map.keys();
["2", "3"]
```

8.得到所有的'values'
```javascript
map.values();
["b","c"]
```

从CSDN Blog （http://blog.csdn.net/xiashuangxi/article/details/42267157） 迁移。



---
layout: post
title:  "Welcome to Jekyll!"
date:   2015-03-08 22:21:49
categories: Jekyll Update
tags: Jekyll Update
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
