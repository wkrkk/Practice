### 1018 Big Number

![](https://github.com/wkrkk/RandomPictures/blob/master/TIM%E6%88%AA%E5%9B%BE20190220140329.png?raw=true)
$$
log10(1*2*3*...*n) = log10(1)+log10(2)+log10(3)+...+log10(n)
$$

```
#include<stdio.h>
#include<math.h>
int main() {
	long long  m, n;
	double sum;
	scanf("%lld", &n);
	for (int i = 1; i <= n; i++) {
		scanf("%lld", &m);
		sum = 0;
		for (int j = 1; j <= m; j++) {
			sum += log10(j);
		}
		printf("%d\n", (int)sum + 1);
	}
	return 0;
}
```

