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

/select 那么，你接下来要干什么呢？
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


# 定义

```ruby
class MyMacco > Macco
  enter do |r|

    r.on 'exec', :rest, :body, desc: '运行命令' do |code, blockcode|
      code ||= blockcode
      execute code
    end

    r.on 'create', :list, :body, desc: '创建文件'do |filepath, content|
      File.write filepath, content
    end

    r.on 'select', :list, desc: '建议' do |advice, selections|
      puts advice
      selections.each { puts it }
    end
    
  end
end
```

测试

```ruby
markdown = <<~MARKDOWN
  /select which do you want?
  1. play game
  2. wash body
  3. do exercise
  4. running
  5. eat breakfast
  6. other
MARKDOWN

MyMacco.run markdown
```
