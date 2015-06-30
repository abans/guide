# Style Guide

*编码规范

## Table of Contents

  1. [命名规范](#命名规范)
  1. [Naming](#naming)
  1. [Declaration](#declaration)
  1. [Alignment](#alignment)
  1. [Quotes](#quotes)
  1. [Spacing](#spacing)
  1. [Props](#props)
  1. [Parentheses](#parentheses)
  1. [Tags](#tags)
  1. [Methods](#methods)
  1. [Ordering](#ordering)

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
