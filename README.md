# helloWord
Python练习项目
# 下划线约定方法：
   - _xxx:表示内部使用,不能被from M imoprt *导入
   - xxx_:表示避免和关键字冲突,如Tkinter.Toplevel(master, class_='ClassName')
   - __xxx:更彻底的private.用到了name mangling技术,会自动加上类名前缀.不能被子类和类外访问.
   - __xxx__:魔术方法(构造函数)或用户控制的命名空间.

# oop -Python面向对象
- python 的面向对象
- 面向对象的变成
    - 基础
    - 公有
    - 继承
    - 组合 Minxi
 - 魔法函数
    - 魔法函数概述
    - 构造类魔法函数
    - 运算类魔法函数


# 1 面向对象概述 （ObjectOriented:  OO）
- OOP思想
- 几个名词
    - oo:面向对象
    - OOA：面向对象的分析
    - OOD:面向对象的设计
    - OOI:面向对象的实现
    - OOP:面向对象的编程
    - OOA ->OOD->OOI:面向对象的实现 过程
# 2. 类和对象的概念
   - 类：抽象名词 ，代表一个集合，共性的事物
    - 对象：具象的事物，单个个体
    - 类跟对象的 关系
        -一个具象，代表一类事物的某一个个体
        - 一个是抽象的，代表的是一大类事物
   - 类中的内容，应该具有两个内容
        - 标明事物的特征，叫做属性（变量）
        - 标明事物功能或者动作，称为成员方法（函数）
# 2.类的基本实现
- 类的命名
    - 遵守变量命名的规范
    - 大驼峰（由一个或者多个单词构成，每个单词首字母大写，单词跟单词之间相连）
    - 尽量避开跟系统命名相似的名称
- 你如何生成一个类
    - 必须用class 关键字
    - 类由属性和方法构成 其他不允许出现
    - 成员属性定义可以直接使用变量赋值，如果没有纸 允许使用None
    案例：01.py


- 实例化类
    变量 = 类名（）# 实例化了一个对象
- 访问对象成员
    - 使用点操作符
        
            ojb.成员属性名称
            obj.成员方法
            
- 可以通过默认内置变量检查类和对象的所有成员
    - 对象所有成员检查
    
            # dict前后各有两个下划线
            obj.__dict__
    - 类所有成员
            # dict前后各有两个下划线
            class_name.__dict__

# 3 anaconda基本使用

- anaconda 主要是一个虚拟环境管理器
- 还是一个安装包管理器
- conda list:显示anaconda安装的包
- conda env list:显示anaconda虚拟环境列表
- conda create -n xxx(环境名称) python=3.6：创建python版本为3.6的虚拟环境 名称为xxx

# 类和对象的成员分析

- 类和对象都可以存储成员，成员可以归 类所有，也可以归对象所有
- 类存储成员时使用的是与类关联的一个对象
- 独享存储成员是存储在当前对象中
- 对象访问一个成员时，如果对象中没有成员 ，那么尝试访问类中的同名成员
    如果对象中有此成员，一定使用对象中的成员
- 创建对象时候，类中的成员不会放到对象中，而是得到一个空的对象，没有成员
- 通过对象对类中成员重新赋值或者通过对象添加成员时， 对应成员会保存在对象中，而不会修改类成员

# 5. 关于self
- self 在对象的方法中表示当前对象本身，如果通对象调用一个方法，那么该对象会自动传入到当前方法的第一个参数中
- self并不是关键字，只是一个用于接受对象的普通参数，理论上可以用任何一个普通变量代替
- 方法中有self 形参的方法成为非绑定类的方法，可以通过对象访问，没有self的是绑定类的方法，只能通过类访问
- 使用类访问绑定

# 6.面向对象的三大特性
- 封装
- 继承
- 多态
## 6.1 封装
- 封装就是对对象的成员进行访问限制
- 封装的三个级别：
    - 公开的 public
    - 私有的 private
    - 受保护的 protected
    - public protected private 不是关键字
 - 判别对象的位置
    - 对象内部
    - 对象外部
    - 子类中
    【下划线使用】https://blog.csdn.net/handsomekang/article/details/40303207
 - 私有
    - 私有成员最高级别的封装，只能在当前类或对象中访问
    - 在成员前面添加两个下划线即可
        - class Person():
            # name 是共有的成员
            name = "dana"
            # __age 就是私有的成员（前边加上两个下划线即可）
            __age = 12  
    - Python 的私有不是真正的私有 是一种为 name mangling 的改名策略
    可以使用对象._classname_attributename访问
 - 受保护的封装 protected 
    - 受保护的封装是将对象成员进行一定级别的封装，然后在类中或者子类中都可以进行访问，但是在外部不可以
    - 封装方法：在成员名称前边添加一个下划线即可
 - 公开的，公共的 public
    - 公共的封装实际对成员没有任何操作限制，任何地方都可以访问   
    
# 3.2继承
- 继承就是一个类可以获得另外一个类中的成员属性和成员方法
- 作用：减少代码，增加代码的复用功能，同时可以设置类与类直接的关系
- 继承与被继承的概念
    - 被继承的类叫父类，也叫基类，也叫超类
    - 用于继承的类，叫子类，也叫派生类
    - 继承与被继承一定存在一个 is-a 关系
    - 继承的语法：
    - 在python中，任何类都有一个共同的父类叫object
        - 详见 Oop_jiCheng.py
    - 继承特征
        - 所有的类都继承自object类，即所有的类都是object类的子类
        - 子类一旦继承父类，则可以使用父类中除私有的成员外的所有内容
        - 子类继承父类后并没有将父类成员完全赋值到子类中，而是通过引用关系访问调用的
        - 子类中可以定义独有的成员属性和方法
        - 子类中定义的成员和父类成员相同，则优先使用子类成员
        - 子类如果想扩充父类方法，可以在定义新方法的同时访问父类成员来进行代码重用，
        可以使用“[父类名.父类成员]”  的格式来调用父类成员，也可以使用“[super().父类成员]”
        的格式来调用
    - 继承变量函数的查找顺序问题
        - 优先查找自己的变量
        - 没有则查找父类
        - 如果构造函数本类中没有定义，则自动查找调用父类构造函数
        - 如果本类有定义，则不在继续向上查找
    
    - 构造函数
        - 是一类特殊的函数， 在类进行实例化之前进行调用
        - 如果定义了构造函数，则实例化时使用自己的构造函数，不查找父类的构造函数
        - 如果没有定义，则向上查找父类构造函数
        - 如果子类没有定义，父类的构造函数带参数，则构造对象应该按父类参数构造
- super
    - super 不是关键字，而是一个类[ print(help(Super))     help(Super)]
    - super 的作用是获取[MRO(MethodResolustionOrder)]列表中的一个类
    - super 与父类没有直接实质性关系，但是通过super可以调用到父类
    - super 常见使用两个方法，参见在构造函数中调用父类的构造函数
        
- 单继承和多继承
    - 单继承：每个类只能继承一个类
    - 多继承：每个类允许继承多个类

- 单继承和多继承的优缺点
    - 单继承：
        - 传承有序逻辑清晰语法简单隐患少
        - 功能不能无限扩展，只能在当前唯一的继承链中扩展
    - 多继承：
        - 优点：类的功能扩展方便
        - 缺点：继承关系混乱
        
- 菱形继承/钻石继承的问题
    - 多个子类继承自同一个父类，这些子类由又被同一个类继承，于是继承关系图形成了一个菱形图谱
    - [MRO https://www.cnblogs.com/whatisfantssy/p/6046991.html]
    - 关于多继承的MRO
        - MRO 就是多继承中，用于保证继承顺序的一个列表
        - Python本身采用C3算法来计算继承的菱形继承进行计算的结果
        -  MRO 列表的计算原则：
            - 子类永远在父类的前面
            - 如果多个父类,则根据继承语法中括号内 类的书写顺序存放
            - 如果多个类继承了同一个父类，算子类中只会选取继承语法括号中第一个父类的父类
            
- 构造函数
    - 在对象进行实例化的时候，系统自动调用的一个函数叫做构造函数，通常此函数用来对实例对象进行初始化操作，顾明构造函数
    - 构造函数一定要有，如果没有则自动向上查找 按照MRO顺序直到找到为止


## 3.3 多态
- 多态就是同一个对象在不同情况下有不同的状态出现
- 多态不是语法，是一种设计思想
- 多态性： 一种调用方式，不同的执行效果
- 多态：同一事物的多种形态，动物分为人类，狗类，猪类
- [多态和多态性]（https://www.cnblogs.com/luchuangao/p/6739557.html）
- Mixin设计模式：
    - 主要采用多继承方式对类的功能进行扩展
    
- 我们使用多继承的语法来实现Minxin
- 使用Mixin实现多继承的时候要非常小心
    - 首先他必须表示一个单一功能，而不是某个物品
    - 职责必须单一，如果有多个功能，则写多个Mixin  
    - Mixin 不能依赖于子类的实现
    - 子类即使没有继承这个Mixin类 ，也能照样工作，只是缺少了某个功能
- 优点
    - 使用Mixin可以在不对类进行任何修改的情况下，扩充功能
    - 可以方便的组织和维护不同功能组件的划分
    - 可以根据需要任意吊证功能类的组合
    - 可以避免创建很多新的类，导致类的继承混乱
    
    
## 4 类 相关函数
- issubclass :检测一个类是否是另一个类的子类
- isinstance :检测一个对象是否是一个类的实例
- hasattr :检测一个对象是否含有成员XXX
- getattr: get attribute
- setattr: set attribute
- delattr: delete attribute
- dir :获取对象成员列表


# 类的成员描述符（属性）-- LeiShuxing.py
- 类 的成员描述是为了在类中对类的成员属性进行相关操作而创建的各种方式
    - get：获取属性的操作
    - set：修改或添加属性操作
    - delete：删除属性的操作
    
- 如果想使用类的描述符，有三种方法
    - 使用类实现描述器
    - 使用属性修饰符
    - 使用property 函数
        - property 函数
        - x = property(fget ,fset,fdel,doc)
        
- 无论哪种修饰符都是为了对成员属性进行相应的控制
    - 类的方式：适合多个类中的多个属性共用一个描述符
    - property：使用当前类中使用，可以控制一个类中多个属性
    - 属性修饰符：适用于当前类中使用，控制一个类中的一个属性
# 6.类的内置属性
    __dict__:以字典的方式显示类的成员组成
    __doc__:获取类的文档信息
    __name__：获取类的名称，如果在模块中使用，则获取模块的名称
    __bases__:获取某个类的所有父类，以元组的方式显示

# 7.类的常用魔术方法
- 魔术方法就是不需要人为调用方法基本是在待定的时刻自动触发
- 魔术方法的统一特征，方法名被前后各两个下划线包裹
- __init__：构造函数
- __new__：对象实例化方法，此函数比较特殊，一般不需要使用
- __call__：对象当函数使用的时候触发
- __str__:当对象被当做字符串使用的时候触发
- __repr__：返回字符串 跟 __str__ 具体区别 百度下