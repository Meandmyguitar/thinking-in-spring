

# 依赖查找安全性对比

## 依赖查找类型：
```text
单一类型查找:
   BeanFactory$getBean 不安全
   ObjectFactory#getObject 不安全
   ObjectProvider#getIfAvailable 安全（推荐）
   
集合类型查找：
    ListableBeanFactory#getBeansOfType 安全
    ObjectProvider#stream 安全
    
    
注意：层次性依赖查找的安全性取决于其扩展的单一或者集合类型的BeanFactory接口

```

## ObjectFactory和BeanFactory的区别？
```text
    ObjectFactory与BeanFactory均提供了依赖查找的能力。
    不过ObjectFactory仅仅关注一个或一种类型的Bean依赖查找，并且自身不具备
依赖查找的能力，能力是由BeanFactory输出。
    BeanFactory则提供了单一类型，集合类型以及层次性等多种依赖查找方式。
```
## BeanFactory.getBean 操作是否线程安全？
```text
    BeanFactory.getBean 方法的执行是线程安全的，操作过程中会增加互斥锁。
    
```
