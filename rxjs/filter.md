## debounceTime(t)
observable 消息间隔小于t的消息被忽略，可用以filter键盘输入变化

## distinctUntilChanged
observable值发生改变时才会发送消息

## first & last
只发送第一个(最后一个)值

## single 
发出通过断言函数的第一项

## skip
跳过N个发出值

## skipUntil
跳过源 observable 发出的值，直到内部 observable 发出值 
`source.pipe(skipUntil(timer(6000)))`

## skipWhile
跳过源 observable 发出的值，直到提供的表达式结果为 false 。
`source.pipe(skipWhile(val => val < 5))`

## take
取前n个值

## takeUntil、 takeWhile 类似skip...