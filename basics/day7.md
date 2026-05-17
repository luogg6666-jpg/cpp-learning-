## 学习了静态在类与结构体中的使用

# 静态变量只占用一块内存，在存在的过程中只会初始化一次
比如这里
'''cpp
#include <iostream>

void Function()
{
  static int i = 0;
  i++;
  std::cout<< i <<std::endl;
}
int main(){
  Function()
  Function()
  Function()
  Function()
  std::cin.get();
}'''
输出的是
'''1
2
3
4'''
# 内在幕后的实际工作方式：每个非静态方法总是获得一个类的实例作为参数
# 关于为什么静态方法无法访问非静态成员，这样一句话非常生动形象“你不能在末影箱（静态方法）中拿到别人背包（实例化对象）里的东西（非静态变量）”，
但是其实可以通过选定对象来做到成功调用非静态变量
