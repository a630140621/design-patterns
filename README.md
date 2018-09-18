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

## Proxy.dynamic.class.js

动态代理, 此处使用 ES6 Proxy 实现对类中函数访问的代理

> 实现了对类中方法进行动态代理，包括预处理和后续处理

# 中介者模式(未完成)

中介者模式（Mediator），用一个中介对象来封装一系列的对象交互。中介者使各对象不需要显式地相互引用，从而使其耦合松散，而且可以独立地改变它们之间的交互。

如果有多个模块(超过3个)进行相互调用,形成网状结构, 那么对于系统的维护是非常困难的;这时候使用中介者模式是非常好的, 对于每个类来说只处理自身相关的事情,其他的事情全部交给中介者类进行处理

# 命令模式(未完成)

将一个请求封装成一个对象, 从而让你使用不同的请求把客户端参数化, 对请求排队或者记录请求日志, 可以提供命令的撤销和恢复功能

敏捷开发原则告诉我们，不要为代码添加基于猜测的、实际不需要的功能，如果不清楚一个系统是否需要命令模式，一般就不要着急去实现它，事实上，在增加需求时通过重构实现这个模式并不困难，只有在真正需求如撤销、恢复操作等功能时，把原来的代码重构为命令模式才有意义。

# 责任链模式

## Chain.class.js

财秘登录的责任链方式(目前的代码有点问题)

## Chain.classify.class.js

责任链基本用法

## Chain.class.1.js

责任链用法的一个模拟场景

## 妆饰者模式

定义：

* **装饰者(decorator)** 模式能够在不改变对象自身的基础上，在程序运行期间给 __对象动态的添加职责。__ 与继承相比，装饰者是一种更轻便灵活的做法。

优点：

* 可以动态的给某个对象添加额外的职责，而不会影响从这个类中派生的其它对象

## 策略模式

定义一系列的算法，把它们一个个封装起来，并且使它们可以相互替换。

> 使用策略模式重构代码，可以消除程序中大片的条件分支语句。

## 适配器模式

适配器模式（Adapter）是将一个类（对象）的接口（方法或属性）转化成客户希望的另外一个接口（方法或属性），适配器模式使得原本由于接口不兼容而不能一起工作的那些类（对象）可以一些工作。

> js （弱类型语言） 中，作用？？？

## 迭代器模式

这个模式,略过

> js 中实现迭代器接口(Iterator) 的对象均可被 `for ... of` 进行循环

## 组合模式

将对象组合成树形结构以表示 “部分-整体” 的层次结构，组合模式 __使得用户对单个对象和组合对象的使用具有一致性。__

> 没有完全理解这句话, 因为组合对象还是拥有比组件更多的方法, 而组件并不能调用不存在与他本身却存在与组合对象中的方法

组合模式主要有三个角色：

1. 抽象组件（`Component`）：抽象类，主要定义了参与组合的对象的公共接口
2. 子对象（`Leaf`）：组成组合对象的最基本对象
3. 组合对象（`Composite`）：由子对象组合起来的复杂对象

使用场景

* 维护和展示部分-整体关系的场景, 如树形菜单, 文件和文件夹管理.
* 从一个整体中能够独立出部分模块或功能的场景.

> 如果对象具有明显的层次结构并且想要统一地使用它们，这就非常适合使用组合模式。

## 观察者模式

观察者模式又叫发布订阅模式（Publish/Subscribe），它定义了一种 __一对多__ 的关系，让多个观察者对象同时监听某一个主题对象，这个主题对象的状态发生变化时就会通知所有的观察者对象，使得它们能够自动更新自己。

> 与事件机制的基础也是观察者模式

## 门面模式

使用场景:

* 辨认那些反复成组出现的代码。如果函数b经常出现在函数a之后，那么门面模式就派上用场了。
* 子系统相对独立, 外界的操作不需要深入到子系统内部, 只需要少量的接口(微服务)

> 门面模式中是不应该含有业务代码(逻辑)的, 门面模式只是对子系统的一层代理, 这一点使用时要特别注意

## 备忘录模式

定义：

在不破坏封装性的前提下，捕获一个对象的内部状态，并在该对象之外保存这个状态。这样就可以将该对象恢复到原先保存的状态

作用：

在我们的开发中偶尔会遇到这样一种情况，需要对用户的行为进行 __撤销__。要想实现撤销，首先需要保存软件系统的历史状态，当用户执行撤销时用之前的状态覆盖当前状态。

使用场景：

分页控件(缓存前一个页面的内容)、撤销组件

> 备忘录模式在 `js` 中经常用于数据缓存。

### Memento.class.js

模仿 `java` 的备忘录模式, 实际场景基本用不到

### Memento.sample.class.js

一个简单的分页控件, 使用备忘录模式来进行先前页面的存储

### Memento.sample2.class.js

将类的职责分开

## 访问者模式

定义:

封装一些作用于某中数据结构中的个元素的操作, 它可以在不改变数据结构的前提下定义作用于这些元素的新的操作.

使用场景:

1. 一个对象结构包含很多类对象, 他们有不同的接口, 而你相对这些对象实施一些依赖于其具体类的操作(java, 或者说强类型语言会遇到这种情况)
2. 需要对一个对象结构中的对象进行很多不同并且不相关的操作, 而你想避免让这些操作 "污染" 这些对象的类

## 状态模式

定义:

当一个对象内在状态改变时允许其改变行为, 这个对象看起来像改变了其类

使用场景:

* 行为随状态改变而改变

这是状态模式的根本出发点, 例如权限设计, 人员的状态不同及时执行相同的操作也会有不同的结果

> 状态模式适用于当摸个对象在他的状态发生改变时, 他的行为也随着发生比较大的变化, 也就是说在 __行为受状态约束的情况下__ 可以使用状态模式

## 解释器模式

定义:

给定一个语言，定义它的文法的一种表示，并定义一个解释器，这个解释器使用该表示来解释语言中的句子。

> 理念和js,python,bash等脚本语言的解释器相同, 一般情况下用不到(像xml,html,makedown解析等一般有成熟的工具)

## 享元模式

定义：

运用共享技术有效地支持大量细粒度对象的复用。系统只使用少量的对象，而这些对象都很相似，状态变化很小，可以实现对象的多次复用。

__内部状态__ 和 __外部状态__：

* 内部状态： _在享元对象内部不随外界环境改变而改变的共享部分_。
* 外部状态： _随着环境的改变而改变，不能够共享的状态就是外部状态_。

由于享元模式区分了内部状态和外部状态，所以我们可以通过设置不同的外部状态使得相同的对象可以具备一些不同的特性，而内部状态设置为相同部分。在我们的程序设计过程中，我们可能会需要大量的细粒度对象来表示对象，如果这些对象除了几个参数不同外其他部分都相同，这个时候我们就可以利用享元模式来大大减少应用程序当中的对象。如何利用享元模式呢？这里我们只需要将他们少部分的不同的部分当做参数移动到类实例的外部去，然后再方法调用的时候将他们传递过来就可以了。这里也就说明了一点： __内部状态存储于享元对象内部，而外部状态则应该由客户端来考虑__。

## 桥梁模式

定义:

将抽象部分与它的实现部分分离，使它们都可以独立地演化。

优点:

1. 分离抽象接口及其实现部分。 
2. 桥接模式提高了系统的可扩充性，在两个变化维度中任意扩展一个维度，都不需要修改原有系统。 
3. 实现细节对客户透明，可以对用户隐藏实现细节。

缺点:

1. 桥接模式的引入会增加系统的理解与设计难度
2. 桥接模式要求正确识别出系统中两个独立变化的维度，因此其使用范围具有一定的局限性。