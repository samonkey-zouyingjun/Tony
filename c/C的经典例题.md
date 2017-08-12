# c语言基础（能读懂c代码，会调用）

## 指针的一些问题
指针申明不赋值引用会报错，不确定指向那个内存地址。

## 双重指针

    #include <stdio.h>
    #include <stdlib.h>
    
    void function(int** p){ //2
    	int i = 3;  //3
    	*p = &i;//4
    	printf("子函数打印地址%#x\n",&i);//问题1 
    } 
    
    main(){
    	int* mainp;//1
    	function(&mainp);
    	
    	printf("主函数打印地址%#x\n",mainp); //问题2 
    	printf("i的值为%d\n",*mainp);//问题3 
    	system("pause");
    }
    //切记画图 1和2的答案为0x28ff20;3的答案为随机值，局部变量会被销毁    

