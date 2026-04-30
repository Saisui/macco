# MACOO 用法

## 单行

```md
/directive.fix1.fix2 arg1 arg2 key=val

/exec rest...

/exec.get `cat hello.c`

/search hatsune miku mmd

/search ps=100 mmd

/exec.send cat README.md

```

## 多行

让 LLM 的输出满足以下格式即可：

``````md

让我们来 python！

/py
```
import numpy as np

np.array([1,2,3,4,5])

```

那么，你接下来要干什么呢？

/select
- 吃饭
- 睡觉
- 晚安

问问猫娘，干什么吧？

/ask kitty
```
什么意思啊
这是
```

``````
