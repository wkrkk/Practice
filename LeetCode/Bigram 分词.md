#### Bigram 分词

[题目](https://leetcode-cn.com/problems/occurrences-after-bigram/)

给出第一个词 first 和第二个词 second，考虑在某些文本 text 中可能以 "first second third" 形式出现的情况，其中 second 紧随 first 出现，third 紧随 second 出现。

对于每种这样的情况，将第三个词 "third" 添加到答案中，并返回答案。

**示例 1**：

```
输入：text = "alice is a good girl she is a good student", first = "a", second = "good"

输出：["girl","student"]
```

**示例 2：**

```
输入：text = "we will we will rock you", first = "we", second = "will"

输出：["we","rock"]
```




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

