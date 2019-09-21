请访问: <a href="https://doctording.github.io/code/" target="_blank">解题代码</a>

---

# 学习目的

* 《程序员代码面试指南》: <a href="https://www.nowcoder.com/ta/programmer-code-interview-guide?page=1" target="_blank">牛客网刷题地址</a>

# 解题思路(全)

1. 在行列都排好序的矩阵中找指定的数

# simiki 部署使用

```bash
$ simiki g # 生成output
$ simiki p # 本地运行：http://127.0.0.1:8000/code/
```

```bash
# 部署到 https://doctording.github.io/code/
$ ghp-import -p -m "Update output documentation" -r origin -b gh-pages output
```

可参考： https://blog.csdn.net/u013041398/article/details/73958706

# tool.py处理git提交

```bash
$ python tool.py ["本次commit的描述信息"]
```

如
```bash
$ python tool.py "更新了README文档"
```

或者，默认的commit描述信息为："updated"
```bash
$ python tool.py
```

图片使用例子

```bash
![](https://raw.githubusercontent.com/doctording/sword_at_offer/master/content/solved_by_java/imgs/circle.png)
```
