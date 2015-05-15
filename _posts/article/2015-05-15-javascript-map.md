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
1.创建一个`Map`对象
{% highlight javascript %}
var map = new Map();
{% endhighlight %}

2.在 `map` 对象里添加一个数据
{% highlight javascript %}
map.put('1','a');
map.put('2','b');  
map.put('3','c');
{% endhighlight %}

3.这个`map`的大小
{% highlight javascript %}
map.size();
3
{% endhighlight %}

4.获取 `key = 1` 的数据
{% highlight javascript %}
map.get('1');
"a"
{% endhighlight %}

5.删除 `key = 1` 的数据
{% highlight javascript %}
map.remove('1');
map.szie();
2
{% endhighlight %}

6.查看`map`对象是否空
{% highlight javascript %}
map.isEmpty();
false
{% endhighlight %}

7.得到所有的`key`
{% highlight javascript %}
map.keys();
["2", "3"]
{% endhighlight %}

8.得到所有的`values`
{% highlight javascript %}
map.values();
["b","c"]
{% endhighlight %}

从CSDN Blog （http://blog.csdn.net/xiashuangxi/article/details/42267157） 迁移。
