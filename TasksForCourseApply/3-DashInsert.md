# DashInsert

You have to implement a function with the following signature - `dashInsert(num)`

* The argument `num` is of type integer.
* The function should return a string


Insert dashes `'-'` between each two neighboring odd numbers in `num`. 

Don't count zero as an odd number.

**You can use any language you know.**

Examples:

```python
dashInsert(99946)
"9-9-946"
dashInsert(56730)
"567-30"
```
#include <iostream>
using namespace std;

string dashInsert(int num)
{
	string str, ret;
	int a, b;
	
	a = num%10;
	num = num/10;
	str = a + '0';

	
	while (num != 0)
	{
		b = num%10;
		num = num/10;
		if ((a == 0) or (b == 0))
		{
			str += b + '0';
		}
		else if ((a%2 != 0) and (b%2 != 0))
		{
			str += '-';
			str += b + '0';
		}
		else
		{
			str += b + '0';
		}
		a = b;
	}
	for (unsigned int i = 0; i < str.length(); i++)
	{
		ret += str[str.length()-i-1];
	}
	return ret;
}

int main()
{
	int num = 10597;
	string str = dashInsert(num);
	
	for (unsigned int i = 0; i < str.length(); i++)
	{
		cout << str[i];
	}
	
	cout << endl;
	
	return 0;
}
