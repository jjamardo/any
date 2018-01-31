# any
Implementation of the C++ "any" type

This is practically a copy and paste of the Kevlin Henney class described in
"Valued Conversions", C++ Report 12(7), July/August 2000 (see
ValuedConversions.pdf), the same that is implemented in the Boost Library
(boost:any).

## Use

```c++
std::vector<any> v;
any i = 42;
any s = std::string("Hello, world!");

v.push_back(i);
v.push_back(s);

std::vector<any>::const_iterator it = v.begin();
for (; it != v.end(); ++it)
{
	if (it->type_info() == typeid(int))
	{
		std::cout << any::as<int>(*it) << std::endl;
	}
	else if (it->type_info() == typeid(std::string))
	{
		std::cout << any::as<std::string>(*it) << std::endl;
	}
}
```
