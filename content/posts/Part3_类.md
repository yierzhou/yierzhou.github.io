+++
date = '2025-07-05T12:17:01+08:00'
lastmod = '2025-07-05T12:44:13+08:00'
draft = false
title = 'Part3_类'
tags = ['C++', '类', '面向对象']

+++

# 多继承

***首先提一下：多继承了解一下就可以了。***

1. 多继承的概念

(1) 就是一个类同时继承多个类，在内存上，该类对象前面依次为第一个继承的类，第二个继承的类，依次类推。

***代码演示：***

```c++
#include <iostream>

class Base1
{
public:
	Base1(int base1I_) : base1I(base1I_) { std::cout << "Base1()" << std::endl; }
protected:
	int base1I;
};

class Base2
{
public:
	Base2(int base2I_) : base2I(base2I_) { std::cout << "Base2()" << std::endl; }
protected:
	int base2I;
};

class Dervied : public Base1, public Base2
{
public:
	Dervied(int base1I_, int base2I_, int i_): Base1(base1I_), Base2(base2I_), i(i_) 
	{
		std::cout << "Dervied" << std::endl;
	}
private:
	int i;
};

int main()
{
	Dervied dervied(10, 20, 30);
	return 0;
}

```

2. 多继承的注意点：

(1) 多继承最需要注意的点就是重复继承的问题，这个问题下一个将会详细讲解。

(2) 多继承会使整个程序的设计更加复杂，平常不推荐使用。C++语言中用到多继承的地方主要就是借口模式。相较于C++，java直接取消了多继承的功能，添加了借口。

 

多继承的总结：***多继承这个语法虽然在某些情况下使代码写起来更加简洁，但会使程序更加复杂难懂，一般来说除了接口模式不推荐使用。***
