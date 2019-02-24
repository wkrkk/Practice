### 1093 A+B for Input-Output Practice (V)

![](https://github.com/wkrkk/RandomPictures/blob/master/TIM%E6%88%AA%E5%9B%BE20190220140223.png?raw=true)

```
#include<stdio.h>
int main() {
	long long m, n, t, sum;
	scanf("%lld", &n);
	while (n > 0) {
		scanf("%lld", &m);
		sum = 0;
		for (long long i = 1; i <= m; i++) {
			scanf("%lld", &t);
			sum += t;
		}
		printf("%lld\n", sum);
		n--;
	}
	return 0;
}
```

