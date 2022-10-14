# 12
递归（上）

int main()
{
	printf("hehe\n");
	main()
		; return 0;
}
//死循环
//错误原因:0xC00000FD Stack flow
//递归常见的错误


练习一 一位一位输出1,2,3,4
void print(int n)//如输入的是1 2 3 4
{
	if (n > 9)//说明这个函数两位及以上
	{
		print(n / 10);
	}
	printf("%d", n % 10);
}

int main()
{

	unsigned int num = 0;
	scanf("%d", &num);
	//递归
	print(num);
	//print (1234)
	//print (123)4
	//print (12)34
	//print (1)234
	//print 1234
	return 0;
}

//练习二 不创建临时变量，求字符串变量
#include<string.h>
int my_strlen(char* str)
{
	if (*str != '\0')
		return 1 + my_strlen(str + 1);
	else
		return 0;
	//my_strlen("bit");
	//1+my_strlen("it");
	//1+1+my_strlen("t");
	//1+1+1+my_strlen("");
	//1+1+1+0
}

int main()
{
	char arr[] = "tao"
		//模拟实现了一个strlen函数
		; int len = my_strlen(arr);
	printf("len=%d\n", len);
	return 0;
}
