# zhengze
正则复习
# 正则表达式
定义：就是一个规则，一个强大的字符串匹配工具，是一种很难懂的文字，有两种写法
1. js风格--new RegExp("a","i");
2. perl风格--/a/i

## 方法
### search
字符串搜索，返回匹配到的位置,如果找到返回下标，否则就返回-1，i为不区分大小写。
```js
let str = 'abcdefg';
let reg = /eF/i

console.log(str.search(reg))
```

### match
获取匹配的项目，如果找到返回一个数组，否则返回null, 其中g为全局匹配，如果不加g的话，默认只会匹配第一项。
```js
let str = 'abcdefgasdwef';
let reg = /ef/g

console.log(str.match(reg))
```

### replace
替换所有匹配，返回替换后的字符串,replace接收两个参数，第一个是参数，第二个是想要替换成的字符串。
```js
let str = 'abcdefgasdwef';
let reg = /ef/g

console.log(str.replace(reg,''))
```
### test
检验字符串是否符合正则的规则
```js
let str11 = 'abcdefgasdwef';
let reg11 = /^ef$/g
console.log(reg11.test(str11))
```

### 相关方法
  1. 任意字符串 [],可以是里面的任何一个字符串
  ```js
  let str = 'apcbpccpcfpcfesefegpc';
  let reg = /[abc]pc/g;
  console.log(str.match(reg)) //['apc','bpc','cpc']

  ```
  2. 范围[a-z]、[0-9],规定了一个范围a-z的所有字母，0到9的所有数字
  ```js
  let str = 'apcbpccpcfpcfesefegpc';
  let reg = /[a-b]pc/g;
  console.log(str.match(reg)) //['apc','bpc']
  ```
  3. 排除[^bc],^排除后面的条件的字符串
  ```js
  let str = 'apcbpccpcfpcfesefegpc';
  let reg = /[^a-c]pc/g;
  console.log(str.match(reg))
  ```

### 转译字符
  1. \d  数字  [0-9]
  2. \w  英文数字下划线 [0-9a-z_]
  3. \s  空白字符
  4. \D  数字  [^0-9]
  5. \W  英文数字下划线  [^0-9a-z_]
  6. \S  非空白字符

### 其他语法
  1. ?   可以有也可以没有
  2. ()  包起来
  3. *   可以有也可以没有,尽量不要使用
  4. i   不区分大小写
  5. ^   行首
  6. $   行尾
  7. g   全局匹配
  8. \+   数量不定，直到结束位置
  8. {}  出现几次 {n}正好出现n次,{n,m}最少出现n次最多出现m次,{n,}最少出现n次 最多不限
  ```js
  let str10 = '0728-3549429-3224'
  let reg10 = /(^0\d{2,3}-)([1-9]\d{6,7})(-\d{2,4}$)?/g
  console.log(str10.match(reg10))
  ```
