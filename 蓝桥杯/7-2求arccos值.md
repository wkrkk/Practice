### 7-2求arccos值

![](https://github.com/wkrkk/RandomPictures/blob/master/%E8%93%9D%E6%A1%A5%E6%9D%AF/TIM%E6%88%AA%E5%9B%BE20190302092040.png?raw=true)

```
#include<stdio.h>
#include<math.h>
#define PI 3.1415926
int main() {
	double x,sum;
	scanf("%lf", &x);
	if (x == 0)
		sum = PI / 2;
	else if (x < 0)
		sum = PI - acos(fabs(x));
	else
		sum = acos(fabs(x));
	printf("%.5lf", sum);
	return 0;
}
```

