###问题
希望能在迭代或者其他形式的处理过程中对最后几项纪录做一个有限的历史记录统计。
###解决方案
按照我的理解，这实际上就是对数据的一些操作，d.append(), d.pop(),d.popleft()等等，这个不难，就直接调用collections里面的deque模块就好了。
```Python
from collections import deque
```
这样就能满足相应的应用场景了。
###讨论
这个题目中一般会涉及到的就是yield生成器，生成器以后可以继续学习。
```
deque(maxlen=N)
```
能够创建一个固定长度的队列，当有新的记录录入队列的时候回自动删除掉最老的那条记录。
可以尝试运行一下：
```
q = deque(maxlen=3)
for i in range(10):
    q.append(i)
    print q
    
q.appendleft(400)
print q
q.pop()
print q
q.popleft()
print q
```
尝试之后你会发现，尽管在列表上手动操作（append、del）也是可以的，但是队列这种解决方案要优雅的多，速度也会更快！
再次强调：**注意缩进**