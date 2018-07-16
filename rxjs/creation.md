## create(function)
```
Observable.create(function(observer) {
  observer.next('Hello');
  observer.next('World');
});
```
## from
```
from('Hello World'); // output: 'H','e','l','l','o',' ','W','o','r','l','d'
from([1, 2, 3, 4, 5]); // output: 1, 2, 3, 4, 5
```
## interval
```
const source = interval(1000);
// output: 0,1,2,3,4,5....
```
## of 
```
of(1, 2, 3, 4, 5); // output: 1, 2, 3, 4, 5
// output: {name: 'Brian}, [1,2,3], function hello() { return 'Hello' }
of({ name: 'Brian' }, [1, 2, 3], function hello() {
  return 'Hello';
});
```
## range
 `range(1, 10); // output 1,2,3,4,5,6,7,8,9,10`

## timer
```
// 1秒后发出0，然后结束，因为没有提供第二个参数
const source = timer(1000);
// 输出: 0

const source = timer(1000, 2000);
// 输出: 0,1,2,3,4,5...... 每2秒发出序列值
```