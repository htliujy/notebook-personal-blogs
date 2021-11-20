# markdown思维导图

Markdown自带一些思维导图和流程图的模版，非常简洁实用<sup>[1]</sup>。

1. **sequence**

    ```sequence
    A->B: 因果关系
    Note right of B: 思维导图
    B-->A: 反向因果关系
    ```

    测试结果：正常

2. **流程图**

    ```flow
    st=>start: 第一步
    op=>operation: 第二步
    cond=>condition: Yes or No?
    e=>end

    st->op->cond
    cond(yes)-->e
    cond(no)-->op
    ```

3. **mermaid横向图**

    ```mermaid
    graph LR
    A[第一步] -->B(第二步)
        B --> C{决策}
        C -->|原因1| D[结果1]
        C -->|原因2| E[结果2]
    ```

    思维导图中的换行要用`<br/>`:

    ```mermaid
    graph LR
    A[第一步<br/>开始] -->B(第二步<br/>执行)
        B --> C{收获}
        C -->|路径1| D[结果1<br/>好]
        C -->|路径2| E[结果2<br/>很好]
            E -->|持续发展1| G[结果5<br/>brilliant]
        C -->|路径3| F[结果3<br/>极好]
            F -->|持续发展2| G[结果4<br/>excellent]
            F -->|持续发展3| H[结果5<br/>brilliant]
    ```

4. **mermaid纵向图**

    ```mermaid
    graph TB
    A[编程语言] -->B[Java]
    A --> F[Python]
        F --> I[入门快]
    A --> G[C++]
    A --> H[html]
        H --> J[网页制作]
    ```

5. **mermaid扇形图**

    ```mermaid
    pie
        title 国土面积(瞎写的，别参考)
        "中国" : 960
        "俄罗斯" : 1700
        "加拿大" : 970
        "美国" : 960
        "澳大利亚" : 700
        "巴西" : 500
        "其他" : 2000
    ```

## 参考及引用

[1] 《Markdown语法系列4:思维导图/图片导入》. 知乎.<https://zhuanlan.zhihu.com/p/351796866>
