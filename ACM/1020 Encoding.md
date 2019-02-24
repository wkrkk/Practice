### 1020 Encoding

![](https://github.com/wkrkk/RandomPictures/blob/master/TIM%E6%88%AA%E5%9B%BE20190220140306.png?raw=true)

```
#include<stdio.h>
int main() {
	char c, t, a[10000], b[10000];
	int i,n,k,count;
	scanf("%d", &n);
	getchar();
	while (n > 0) {
		i = k = 0;
		while ((c = getchar()) != '\n') {
			a[i++] = c;
		}
		a[i] = '\0';
		for (int j = 0; j < i; ) {
			t = a[j];
			count = 0;
			while (t == a[j]) {
				count++;
				j++;
			}
			if (count > 1)
				printf("%d", count);
			printf("%c", t);
		}
		printf("\n");
		n--;
	}
	return 0;
}
```

