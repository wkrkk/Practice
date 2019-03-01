### Torry的困惑(基本型)

![](https://github.com/wkrkk/RandomPictures/blob/master/%E8%93%9D%E6%A1%A5%E6%9D%AF/TIM%E6%88%AA%E5%9B%BE20190301164946.png?raw=true)

```
#include<stdio.h>
#include<math.h>
int main() {
	int n, tag, count, sum;
	count = 0;
	sum = 1;
	scanf("%d", &n);
	for (int i = 2; i <= 100000; i++) {
		tag = 1;
		for (int j = 2; j <=sqrt(i); j++) {
			if (i%j == 0) {
				tag = 0;
				break;
			}
		}
		if (tag==1&&count<n) {
			sum *= i;
			sum %= 50000;
			count++;
		}
	}
	printf("%d", sum);
	return 0;
}
```

