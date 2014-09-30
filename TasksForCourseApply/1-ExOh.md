# ExOH

Implement a function with the following signature: `ExOh(str)`

`str` is of type string.

The function should return `true` if there is an **equal number of x's and o's** in `str`.
It should return `false` otherwise.

Things to know:

* Only these two letters will be entered in the string, no punctuation or numbers. 
* You don't have to check for valid input.
* **You can use any language you know.**

Examples:

```python
ExOh('xoxoox') # true
ExOh('oooxoo') # false
``
#include <iostream>
using namespace std;

bool ExOh(string str)
{
	int x_count=0;
	int o_count=0;
	unsigned int i;
	
	for(i = 0; i < str.length(); i++)
	{
		if(str[i] == 'x')
			x_count++;
		else if (str[i] == 'o')
			o_count++;
	}
	if(x_count==o_count) 
	{
		return true;
	}
	else
	{
		return false;
	}
}

int main()
{
	string str1 = "oxoxox";
	string str2 = "oxooox";
	
	cout << ExOh(str1) << endl;
	cout << ExOh(str2) << endl;
	
	return 0;
}
