# zip 
每一个observables都发出值后，以数组方式发出所有值

# forkjoin 
当所有 observables 完成时，发出每个 observable 的最新值。

# race 
返回速度最快的那个observable，之后一直发送这个observable的消息，忽略其它参与race的observables

# concat 
将observables的结果链接起来

# merge 
将多个observables合并成一个observable

# combineLatest
当任意 observable 发出值时，发出每个 observable 的最新值。

```
source a: a1,                a2
source b:    b1,    b2,   b3,                   b4
concat  : a1,                a2, b1,b2,b3,      b4
merge   : a1,b1,    b2,   b3,a2,                b4
race    : a1,                a2
forkjoin:                                       [a2, b4]
zip     :    [a1,b1],        [a2,b2] 
```

# pairwise 对一个observable的消息两两组队发送
# startwith 给observable添加若干个值
