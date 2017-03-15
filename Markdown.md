# 标题
使用 :hash:，可表示1-6级标题
```md
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```
效果：
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题

# 文字修饰符
```md
*这是斜体标记*

_这是斜体标记_

**这是粗体标记**

__这是粗体标记__

~~这是删除标记~~
```

效果：

*这是斜体标记*

_这是斜体标记_

**这是粗体标记**

__这是粗体标记__

~~这是删除标记~~

# 列表
## 无序列表
主要使用 - 和 * 来标记无序列表，-和***之后要有空格**
```md
- george washington
* thomas jefferson
```
效果：
- george washington
* thomas jefferson

## 有序列表
开头可以是其他数字
```md
1. james madison
1. john monroe
1. james
```
效果：
1. james madison
1. john monroe
1. james
## 任务列表
```md
- [x] finish my changes
- [ ] push my commit to github
* [ ] open a pull request
```
效果：
- [x] finish my changes
- [ ] push my commit to github
- [ ] open a pull request

## 层次样式
```sh
1. Mske my changes
   1. Fix bug
   2. Improve formatting
      * Make the headings bigger
 2. Push my commits to github
 3. Open a pull request
    * Describe my changes
    * Mention all the mebers of my team
      * Ask for feedback
```
效果：
1. Mske my changes
   1. Fix bug
   2. Improve formatting
      * Make the headings bigger
 2. Push my commits to github
 3. Open a pull request
    * Describe my changes
    * Mention all the mebers of my team
      * Ask for feedback
# 链接
```md
[github](http://github.com)
[百度网址](http://www.baidu.com)
```
效果：

[github](http://github.com)

[百度网址](http://www.baidu.com)
# 图片
```md
![图片](图片的网址)
```
效果：
![图片](http://octodex.github.com/images/yaktocat.png)


# 代码快
```c

#include <stdio.h>
int main(void)
{
  printf("hello world!\n");
  return 0;
}

```

效果：
```c
#include <stdio.h>
int main(void)
{
  printf("hello world!\n");
  return 0;
}
```

# 支持Emoji表情
* [Emoji表情](https://www.webpagefx.com/tools/emoji-cheat-sheet/)
