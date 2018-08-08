[toc]

# Design Patterns
设计模式

# 单例模式

使用场景：

1. 需要生成唯一序列号的环境
2. 在整个项目中需要一个共享访问点或共享数据
3. 创建一个对象消耗资源过多

## Singleton.simple.class.js

简单的单例模式

## Singleton.simple1.class.js

将单例放到原型上

## Singleton.multi.class.js

单例模式的加强版, 新建实例的时候传入不同的名称即可得到不同的实例, 若名称相同则得到相同的实例

## Singleton.multi1.class.js

将 instances 放到原型链上

# 工厂方法模式

# 模板方法模式

优点：

1. 封装不变部分，扩展可变部分。 
2. 提取公共代码，便于维护。 
3. 行为由父类控制，子类实现。

缺点：

* 增加代码的阅读难度.

使用场景： 

1. 多个子类有共有的方法，且逻辑基本相同。 
2. 重要的、复杂的方法，可以考虑把核心算法设计为模板方法, 周边的相关细节功能由子类实现.
3. 对外开放自定义拓展功能, 用户只需要实现此模板方法即可实现自定义功能

## Templete.class.js

简单的模板方法

## Templete.hook.class.js

带钩子的模板方法

## Template.sequence.class.js

可自定义模板方法的执行顺序

# 建造者模式

建造者模式的特点是分步构建一个复杂的对象，可以用不同组合或顺序建造出不同意义的对象，通常使用者并不需要知道建造的细节。

优点: 

1. 建造者模式的封装性很好。使用建造者模式可以有效的封装变化
2. 建造者模式很容易进行扩展。如果有新的需求，通过实现一个新的建造者类就可以完成，基本上不用修改之前已经测试通过的代码，因此也就不会对原有功能引入风险。

# 代理模式

代理模式也叫做 _委托模式_, 负责对真实角色的应用, 把所有抽象主题类定义的方法限制委托给真实的角色实现, 并在处理完毕前后做 __预处理__ 和 __善后__ 工作

ES6 中新增了一个代理类 [参考链接](http://es6.ruanyifeng.com/#docs/proxy) 用来实现相关功能

> 这里写的代理模式是参考设计模式中实现的代码

## Proxy.introduction.class.js

代理模式介绍

## Proxy.common.class.js

普通的代理模式
