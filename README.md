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
  - 1、数据、模型相关的属性
  - 2、涉及url中有关的所有地方
    ```javascript
    // bad
    {memberInfo:String};

    // good
    {member_info:String};
    ```

  - 格式：首字母大写，驼峰法


	```javascript
	var ClassName={
	findById:function(){
	}
	}
	```


**[⬆ back to top](#table-of-contents)**
