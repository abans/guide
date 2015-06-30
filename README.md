# Style Guide

*编码规范

## Table of Contents

  1. [命名规范](#命名规范)
  1. [缩进](#缩进)
  1. [Return Early](#return-early)
  1. [循环](#循环)
  1. [多级对象取值](#多级对象取值)
  1. [函数参数的灵活定义](#函数参数的灵活定义)
  1. [额外的建议](#额外的建议)

## 命名规范

  - 格式：全小写，单词之间用下划线连接
    + `数据、模型相关的属性`
    + `涉及url中有关的所有地方`
    ```javascript
    // bad
    {memberInfo:String};

    // good
    {member_info:String};
    ```

  - 格式：首字母大写，驼峰法
    + `类名`
    + `必须使用new前缀的构造函数应该以大写字母开始`

    ```javascript
    // bad
    var className={
    	findById:function(){
    	}
    }

    // good
    var ClassName={
    	findById:function(){
    	}
    }
    ```

  - 格式：首字母小写，驼峰法
    + `函数名`
    + `变量名`

    ```javascript
    // bad
    var user_face;
    var find_byid:function(){
    }

    // good
    var userFace;
    var findById:function(){
    }
    ```

  - 格式：首字母$
    + `前端中的jquery/zepto选取的dom对象`

    ```javascript
    // bad
    var member=jQuery('#member');

    // good
    var $member=jQuery('#member');
    ```

  - 格式：全小写，单词之间用减号"-"连接
    + `css中的类名`

    ```javascript
    // bad
    iconName

    // good
    icon-name
    ```

**[⬆ back to top](#table-of-contents)**

## 缩进
  - 一律用tab缩进，一个tab 等于4个空格的宽度

## Return Early

  - 先把不可能的因素优先全部排除掉，在往下执行

    ```javascript
    // bad
    function(int x) {
    	if (x) {
    		// ...
    	}
    }

    // good
    function(int x) {
    	if (!x)
    		return;
    	// ...
    }
    ```

**[⬆ back to top](#table-of-contents)**


## 循环
  - 数组循环使用原生的forEach，并且在循环前要原型判断是否是数组

    ```javascript
    if (!Acan.isArr(arr))
    	return;
    arr.forEach(function(v,k){
    	// ...
    });
    ```
  - 对象循环使用for in 或者_.each()，并且在循环前要原型判断是否是对象

    ```javascript
    if (!Acan.isObj(obj))
    	return;
    for(var i in obj){
    	// ...
    };
    _.each(obj,function(v,k))
    	// ...
    });
    ```

**[⬆ back to top](#table-of-contents)**

## 多级对象取值
  - 对于不确定的多级对象直接取值要用Acan.objGet (可以防止程序崩溃)

    ```javascript
    Acan.objGet(a,'b.0.c') 等于 a.b[0].c
    Acan.objGet(a,'b.0.c','') 第三个参数为默认值，当值取不到的时候返回设置的默认值
    ```

## 函数参数的灵活定义
  - 支持多种写法，回调统一取法 a.__cb();

    ```javascript
    function test () {
    	var a=Acan.argObj(arguments,['url','filepath','name','maxWidth']);
    	console.log(a);//{"maxWidth":{"a":"4"},"name":["3"],"filepath":2,"url":"1","__cb":function(){var ttt=123;}}
    	//取参数值
    	a.url='1';
    	a.name=["3"];
    }
    test('1',2,['3'],{a:'4'},function(){
    	var ttt=123;
    });
    test('1',2,['3'],function(){
    	var ttt=123;
    });
    test('1',2,function(){
    	var ttt=123;
    });
    //支持多种写法，回调统一取法 a.__cb();
    ```

**[⬆ back to top](#table-of-contents)**

## 额外的建议 

  - {}和[]
    - 使用{}替代new Object()。使用[]替代new Array()。 
    - 当成员名字为连续的整数时使用数组。当成员名字为任意的字符串或名字时使用对象。

**[⬆ back to top](#table-of-contents)**
