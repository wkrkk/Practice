#### Bigram 分词

[题目](https://leetcode-cn.com/problems/occurrences-after-bigram/)

```
class Solution(object):
    def findOcurrences(self,text,first,second):
        words=text.split()
        l1=[]
        #分割后单词的长度
        for i in range(len(words)-2):
            if words[i]==first and words[i+1]==second:
                l1.append(words[i+2])
        return l1

text=input()
first=input()
second=input()

solution=Solution()
print(solution.findOcurrences(text,first,second))
```

