##CSS 类型及获取

```js
var a = 12; //number型
alert(typeof a);

var a = "stringnoj"; //string型
alert(typeof a);

var a = function() {
  //function型
};
alert(typeof a);

var a = true; //boolean型
alert(typeof a);

var a = document; //object型
alert(typeof a);

var a; //undefined型
alert(typeof a);
```
------

### 数据类型强制转换

转整数型：`var a=parseInt('abc');`
转小数型：`var b=parseFloat('efg');`


### NaN 的意义

NaN： Not a Number
NaN 与任何数相加都是 NaN，包括它自身。
判断是否为 NaN:

```js
var a;
if (isNaN(a)) {
}
```
-------

### 隐式类型转换

```js
var a = 5;
b = "5";
alert(a == b); //先转换类型，后比较内容，结果为真
alert(a === b); //既要比较内容又要比较类型，结果为假
```
----

### 闭包

子函数可以使用父函数的局部变量

```js
function aaa() {
  //父函数
  var a = 12;
  function bbb() {
    //子函数
    alert((a += 2));
  }
  a++;
}
```
------

### 匈牙利命名法

- 类型前缀：

| 类型                 | 前缀 | 示例         |
| -------------------- | ---- | ------------ |
| 数组（Array）        | a    | aItems       |
| 字符串（String）     | s    | sUserName    |
| 布尔值（Boolean）    | b    | bIsComplete  |
| 浮点数（Float）      | f    | fPrice       |
| 函数（Function）     | fn   | fnHandler    |
| 整数（Integer）      | i    | iItemCount   |
| 对象（Object）       | o    | oDiv1        |
| 正则表达式（RegExp） | re   | reEmailCheck |
| 变体变量（Variant）  | v    | vAnything    |

- 首字母大写,如：
  > odiv1 > oDiv1
  > `var oTxt1=document.getElementById('txt1');`
-----

### 运算符

- 算术：+ 加、- 减、\* 乘、/ 除、% 取余
  > 实例：隔行变色、秒转时间
- 赋值：=、+=、-=、\*=、/=、%=
- 关系：<、>、<=、>=、==、===、!=、!==
- 逻辑：&&与、||或、!否
  > 实例：全选与反选
- 运算符优先级：括号优先
-----

### 隔行变色：

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <script>
        window.onload=function()
        {
           var aLi=document.getElementsByTagName('li') ;
           for(i=0;i<aLi.length;i++)
           {
               if(i%2==0)
               {
                   aLi[i].style.background='#ccc';
               }
               else
               {
                   aLi[i].style.background='' ;
               }
           }
        }
    </script>
</head>
<body>
    <ul>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
    </ul>
</body>
</html>
```
-----

### 秒转时间

```js
var a = 1234;
alert(parseInt(a / 60) + "分" + (a % 60) + "秒");
```
------

### 程序流程控制

- 判断：if、switch、？
  > if 语句、if-else 语句、if-else if 语句

```js
switch (变量) 
{
    case "值":语句;
    break;
    default:
    语句;
}
```

> `条件1?语句1:语句2` 等同于 if-else 语句

- while、for
- 跳出：break、continue
- 什么是真、什么是假
  > 真：true、非零数字、非空字符串、非空对象
  > 假：false、数字零、空字符串、空对象、undefined
------

### Json

- 什么是 Json
- Json 和数组
- Json 和 for in

```js
var a=5;
    b=7;
    c='ABC';
var json={a:5,b:7,c:'ABC'};   //Json可以用来存放数据
    alert(json.a);            //对Json里的对象取值
    alert(json['a']);         //意义同上，下标是字符串
    json.b++;                 //对Json里的对象运算

var json={5,7,12};
var arr=[5,7,12];
    alert(arr[0]);            //对数组里的元素取值
alert(json.length);           //undefined,Json没有length
alert(arr.length);            //3,数组有length

for(i=0;i<arr.length;i++)     //数组的循环 0-length
{
    alert('第'+i+"个元素是："+arr[i]);
}

for(var i in arr)             //数组的 for in 循环
{
    alert('第'+i+"个元素是："+arr[i]);
}

for(var i in json)            //Json的 for in 循环
{
    alert('第'+i+'个元素是：'+json[i]);
}
```
-----

## 函数的返回值

- 什么是函数的返回值
  > 函数的执行结果
  > 可以没有 return

```js
function show(a, b) {
  return a + b;
}
alert(show(3, 5));
```

- 一个函数应该只返回一种类型的值
-----

### 函数传参

- 可变参（不定参）：arguments
  > 参数的个数可变、参数数组
- 例子 1：求和
  > 求所有参数的和
- 例子 2：CSS 函数
  > 判断arguments，参数数组
  > 给参数取名，增加可读性
- 取非行间样式（不能用来设置）
  > obj.current.Style[attr]
  > getComputedStyle(obj,false)[attr]
-----

## 数组基础
- 数组的使用
    - 定义
    > var arr=[12,5,8,9]
    > var arr=new Array(12,5,8,9)
    > 没有任何差别，[]的性能略高，因为代码更短
- 数组的属性
    - length
    > 既可以获取，又可以设置
    > 例子：快速清空数组
- 数组的使用原则：数组中应该只存一种类型的变量

### 添加、删除元素
- 数组的方法
    - 添加
    > push（元素），从头部添加
    > unshift（元素），从尾部添加
    - 删除
    > pop()，从头部弹出
    > shift()，从尾部弹出

### 排序、转换
- 排序
    - sort（[比较函数]），排序一个数组
    > 排序一个字符串数组
    > 排序一个数字数组
- 转换类
    -concat（数组2）
    > 连接两个数组
    - join（分隔符）
    > 用分隔符，组合数组元素，生成字符串
    > 字符串split

### 插入、删除
- splice
> splice（开始、长度、元素...）
> 先删除，后插入
- 删除
> splice（开始、长度）
- 插入
> splice（开始、0、元素）
- 替换
------

### 定时器的作用
- 开启定时器
> setInterval         间隔型
> setTimeout          延时型
> 两种定时器的区别
- 停止定时器
> clearInterval
> clearTimeout

### 数码时钟
- 效果思路
- 获取系统时间
> Date对象
> getHours、getMinutes、getSeconds
- 显示系统时间
> 字符串连接
> 空位补零
- 设置图片路径
> charAt方法

### Date对象其他方法
- 年
> getFullYear()
- 月
> getMonth()
- 日
> getDate()
- 星期
> getDay()
-----

### 延时提示框
- 效果演示
- 原来的方法
> 移入显示，移出隐藏
- 移出延时隐藏
> 移入下面的Div后，还是隐藏了
- 简化代码
> 合并两个相同的mouseover和mouseout
--------

### 无缝滚动——基础
- 效果演示
- 物体运动基础
> 让Div移动起来
> offsetLeft的作用
> 用定时器让物体连续移动

### 无缝滚动
- 效果原理
> 让ul一直向左移动
- 复制li
> innerHTML 和 +=
> 修改ul的width
- 滚动过界后，重设位置
> 判断过界

### 无缝滚动——扩展
- 改变滚动方向
> 修改speed
> 修改判断条件
- 鼠标移入暂停
> 移入关闭定时器
> 移出重新开启定时器

# DOM基础

### DOM基础-1
- DOM基础
    - 什么是DOM
    - 浏览器支持情况
- DOM 节点
    - childNodes      nodeType
        > 获取子节点
        > children
    - parentNodes
        > 例子：点击链接，隐藏整个li    
    - offsetParent
        > 例子：获取元素在页面上的真实位置

### 操作元素属性
- 元素属性操作
    - 第一种：`oDiv.style.display="block";`
    - 第二种：`oDiv.style["display"]="block";`
    - 第三种：Dom方式 
- DOM方式操作元素属性
    - 获取：`getAttribute(名称)`
    - 设置：`setAttribute(名称,值)`
    - 删除：`removeAttribute(名称)`

### DOM元素灵活查找
- 用className选择元素
    - 如何用className选择元素
        > 选出所有元素
        > 通过className条件筛选
    - 封装成函数

### DOM基础-2
- DOM节点（2）
    - 首尾子节点
        > 有兼容性问题
        > firstChild、firstElementChild
        > lastChild、lastElementChild

    - 兄弟节点
        > 有兼容性问题
        > nextSibling、nextElementSibling
        > previousSibling、previousElementSibling

# DOM操作应用

### 创建、插入和删除元素
- 创建DOM元素
    - `creatElement(标签名)`----------创建一个节点
    - `appendChild(节点)`--------------追加一个节点
        - 例子：为ul插入li
- 插入元素
    - `insertBefore(节点，原有节点（在谁之前）)`--------在已有元素前插入
        - 例子：倒序插入li
- 删除DOM元素
    - `removChild(节点)`---------------删除一个节点
        - 例子：删除li

### 文档碎片
- 文档碎片
    - 文档碎片可以提高DOM操作水平（理论上）
    - 文档碎片原理
    - `document.creatDocumentFragment()`

# DOM操作应用高级

### 表格应用-1

- 获取
    - tBodies、tHead、tFoot、rows、cells
- 隔行变色
    - 鼠标移入高亮
- 添加、删除一行
    - DOM方法的应用

### 表格应用-2

- 搜索
    - 版本1：基础版本——字符串 比较
    - 版本2：忽略大小写——大小写转换
    - 版本3：模糊搜索——search的使用
    - 版本4：多关键词——split
    - 显示效果：高亮显示、筛选
- 排序
    - 移动Li
    - 元素排序：转换——排序——插入

### 表单应用-1

- 表单基础知识
    - 什么是表单
        > 向服务器提交数据，比如：用户注册 
    > action---------提交到哪里
- 表单事件 
    > onsubmit-------提交时发生
    > onreset--------重置时发生

### 表单应用-2

- 表单内容验证
    > 阻止用户输入非法字符-------阻止事件
    > 输入时、失去焦点时验证------onkeyup、onblur
    > 提交时检查-----------------onsubmit
    > *后台数据检查

# JS运动基础

### 运动基础

- 运动基础
    - 让Div运动起来
    - 速度——物体运动的快慢
    - 运动中的Bug
        - 不会停止
        - 速度取某些值会无法停止
        - 到达位置后再点击还会运动
        - 重复点击速度加快
- 匀速运动
    - 速度不变

### 运动框架及应用
- 运动框架
    - 在开始运动时，关闭已有定时器
    - 把运动和停止隔开（if/else）
- 运动框架实例
    - 例子1：“分享到侧边栏”
        - 通过目标点，计算速度值
    - 例子2：淡入淡出的图片
        - 用变量存储透明度

### 缓冲运动
- 逐渐变慢，最后停止
- 距离越远速度越大
    - 速度由距离决定
    > 速度=（目标值-当前值）/缩放系数
- 例子：缓冲菜单
    - Bug：速度取整
    - 跟随页面滚动的缓冲侧边栏
        - 潜在问题：目标值不是整数时

### 匀速运动的停止条件
- 运动终止条件
    - 匀速运动：距离足够近
    - 缓冲运动：两点重合

# JS运动应用

### 多物体运动框架
- 多个物体同时运动
    - 例子：多个div、鼠标移入变宽
        - 单定时器、存在问题
        - 每个div一个定时器
- 多物体运动框架
    - 定时器作为物体的属性
    -  参数的传递：物体、目标值
    - 例子：多个div淡入淡出
        - 所有东西都不能公用
        - 属性与运动对象绑定：速度、其他属性值（如透明度等）

### 任意值运动框架
- offset属性的bug
    - 有边框的div变宽
        - 用currentStyle代替offset
- 原有运动框架的问题
    - 只能让某个值运动起来
    - 如果想让其他值运动起来，要修改程序
- 扩展的运动框架
    - 运动属性作为参数
    - 封装opacity
        - 小数的问题

### 仿Flash图片展示-1
- 效果思路
    - 两边的按钮——淡入淡出
    - 大图下拉——层级、高度变化
    - 下方的li——多物体淡入淡出
    - 下方的UI——位置计算
- 左右按钮
    - 淡入淡出
        - 鼠标移到按钮上，按钮会消失
            - 层级问题
            - 按钮和遮罩上都得加上事件

### 仿Flash图片展示-2
- 下方li效果
    - 点击切换大图——选项卡
    - li 淡入淡出——移入移出
    - UI 移动——位置计算
- 大图片切换
    - 图片层级——zIndex一直+1
    - 图片下拉效果（运动框架）
        - 可以改为淡入淡出
- 加上自动播放
    - 和选项卡一样


### null vs undefined
1. 肯定有结果：返回结果
1. 有或者没有结果: null + 结果
2. 肯定没有结果: undefined















