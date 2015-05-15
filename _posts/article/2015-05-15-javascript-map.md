---
layout: post
title: "Javascript实现Map结构"
data: 2015-05-15
tag: [Javascript,算法]
category: [文章,技术,Javascript]
summary: "Javascript实现Map结构"
---
####使用Javascript实现Map结构。
```javascript
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

```
从CSDN Blog （http://blog.csdn.net/xiashuangxi/article/details/42267157） 迁移。
