## Funtor
- 集合中的每个元素都能应用函数
- 不会改变集合元素的结构
- 集合中的每个元素应用函数后，返回一个新的结果集
- 每一个Functor都有一个基础值，例如：0  “”
- fmap(id) = id
- fmap(g + h) = fmap(g) + fmap(h)

```
  trait Functor[T[_]]{
    def fmap[A,B](list:List[A])(f:A => B):List[B]
  }

  object ListFuntor extends Functor[List] {
    def fmap[A,B](list:List[A])(f: A => B):List[B] = list map f
  }
```

## Monoid
- append(x,y)  == append(y,x)
- (identiy,x) == x
```
trait Monoid[T] {
  def append(m1:T ,m2:T)
  val identiy:T
}
```
