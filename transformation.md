## bufferTime bufferCount 
缓冲一段时间或者一定数量再以数组形式发出来

## map concatMap mergeMap
将value 映射到 Observable, concat 按订阅顺序， merge按收到消息顺序

## mapTo concatMapTo 
将收到的消息映射成常量，不论收到啥，都是发出相同的指定内容

## reduce(function(res, currentVal), seed)
將observable归并为单一值，输入observable结束后发出

## scan(function(res, currentVal), seed)
归并，每来一个值就会发出一个归并结果
```
const source = of(1, 2, 3, 4);
const example1 = source.pipe(reduce((acc, val) => acc + val));
// 输出: Sum: 10'
const subscribe1 = example1.subscribe(val => console.log('Sum:', val));

const example2 = source.pipe(scan((acc, curr) => acc + curr, 0));
// 输出累加值
// 输出: 1,3,6,10
const subscribe2 = example2.subscribe(val => console.log(val));
```
## switchMap(function: Observable, resultSelector: function(outerValue, innerValue, outerIndex, innerIndex): any): Observable
具有取消效果，有新消息来时，就会取消内部的observable
```
// 发出每次点击
const source = fromEvent(document, 'click');
// 如果3秒内发生了另一次点击，则消息不会被发出
const example = source.pipe(
  switchMap(val => interval(3000).pipe(mapTo('Hello, I made it!')))
);
// (点击)...3s...'Hello I made it!'...(点击)...2s(点击)...
const subscribe = example.subscribe(val => console.log(val));
```
