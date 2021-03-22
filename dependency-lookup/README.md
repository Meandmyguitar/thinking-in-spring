

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
