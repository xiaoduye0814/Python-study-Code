# 0  oop :python面向对象
- Pyhton的面向对象
- 面向对象编程
    - 基础
    - 公有私有
    - 继承
    - 组合，Minxi
- 魔法函数
    - 魔法函数概述
    - 构造类魔法函数
    - 运算类魔法函数
# 1 面向对象概述（ObjectOriented, OO）
- OOP思想
    - 接触接触意一个任务，首先想到的是任务这个世界的构成，是由模型构成的
- 几个名词
    - OO:面向对象
    - OOA: 面向对象的分析
    - OOD: 面向对象的设计
    - OOI: xxx的实现
    - OOP: XXX的编程
    - OOA -> OOD -> OOI：面向对象的实现过程
- 类和对象的概念
    - 类：抽象名词，代表一个集合，共性的事物
    - 对象：具象的东西，单个个体
    - 类跟对象的关系
        - 一个具象，代表一类食物的某一个个体
        - 一个是抽象，代表的是一大类事物
    - 类中的内容，应该具有两个内容
        - 表明事物的特征，叫做属性（变量）
        - 表明事物的功能或动作，称为成员方法（函数）
        
# 2. 类的基本实现
- 类的命名
    - 遵守变量命名的规范
    - 大驼峰（由多个单词构成，么个单词首字母大写，每个单词首字母大写）
    - 尽量避开跟系统命名相似的命名
- 如何让声明一个类
    - 必须使用class关键字
    - 类由属性和方法构成，其他不允许出现
    - 成员属性定义可以直接变量赋值，如果没有值，需要使用None
    - 案例 01.py
- 实例化类
    变量 = 类名() #实例化了一个对象
- 访问对象成员
    - 使用点操作符
        obj.成员属性名称
        obj.成员方法
- 可以通过默认内置变量检查类和对象的所有成员
    - 对象所有成员检测
    
        # dict前后各有两个下划线
        obj.__dict__
    - 类所有成员
    
        # dict前后各有两个下划线
        class_name.__dict__
    
# 3. Anaconda基本使用
- anaconda主要是一个虚拟环境器
- 还是一个安装包管理器
- conda list:显示anaconda安装的包
- conda env list:显示anaconda的虚拟环境表
- conda create -n xxx python=3.6:创建Python版本为3.6.5的虚拟环境，名称为xxx


# 4.类跟对象的成员分析
- 类和对象可以存储成员，成员可以归类所有，也可以归对象所有
- 类存储成员是使用的是与类关联的一个对象
- 对象存储成员是存储在当前对象中
- 对象访问一个成员是，如果对象中没有该成员，尝试访问类中的同名成员，如果对象中有此成员，一定使用对象中的成员
- 创建对象的时候，类中成员不会放入对象当中，而是得到一个空对象，没有成员
- 通过对象对类中成员重新赋值或者通过对象添加成员时候，对应成员会保存在对象中，而不会修改原有类成员变量

# 5.关于self
- self在对象的方法中表示当前对象本身，如果通过通过对象调用一个方法，那么该对象会自动传入到当前方法的第一个参数当中。
- self并不是关键字，只是一个用于接收对象的普通参数，理论上可以用任何一个普通变量名代替
- 方法中有self形参的方法称为非绑定类的方法，可以通过对象访问，没有self的是绑定类的方法，只能通过类访问
- 使用类访问绑定类的方法时，如果类方法中需要访问当前类的成员，可以通过__class__成员名访问

# 6. 面向对象的三个特性
- 封装
- 继承
- 多态

## 6.1 封装
- 封装就是对对象的成员进行访问限制
- 封装的三个级别
    - 公开：public
    - 受保护的，protected
    - 私有的，private
    - public，protected，private不是关键字
- 判别对象的位置
     - 对象内部
     - 对象外部
     - 子类中
- 私有
    - 私有成员是最高级别的封装，只能在当前类或对象中访问
    - 实现：自爱成员前面添加两个下划线即可
        
            class Person():
                # name是公有成员
                name = "liuying"
                # age就是私有成员
                __age = 18
    - Python的私有不是真私有，是一种称为name mangling的改名策略
    可以使用对象._classname__attributename访问