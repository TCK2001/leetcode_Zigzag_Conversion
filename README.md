# leetcode_Zigzag_Conversion
+ 지그재그 모양으로 출력하기
+ 設定row的大小之後照著row的大小輸出
>Kevin BKH 코드를 참고하였습니다
-----
+ Example1
```
Input: s = "PAYPALISHIRING", numRows = 3
Output: "PAHNAPLSIIGYIR"
```
----
+ Example2
```
Input: s = "PAYPALISHIRING", numRows = 4
Output: "PINALSIGYAHRPI"
Explanation:
P     I    N
A   L S  I G
Y A   H R
P     I
```
----
+ Example3
```
Input: s = "A", numRows = 1
Output: "A"
```
----
```python
class Solution:
    def convert(self, s: str, numRows: int) -> str: 
        if numRows == 1:
            return s
        strs = ['' for _ in range(numRows)] # 새로 알게된 파이썬 쓰는 방법 string이 있는데 높이는numRows만큼 만듬
        row,step = 0,1
        for char in s:
            strs[row] += char # 0,1,2밑으로 하나씩 더함
            if row == numRows - 1: #만약 최대 높이까지 더했을때 반대로 지그재그를 해야 하기때문에 step을 -1로 바꿈
                step = -1
            elif row == 0: # 만약 꼭대기 도달하면 다시 1로 만들어 밑으로 하나씩 더해감
                step = 1
            row += step # 다음칸 이동
        return ''.join(strs) # 이렇게 만든 []을  string 으로 합쳐서 출력
```
---
```
결론 : 
['' for _ in range(numRows)] 이것만 알면 어떻게 풀줄 앎 처음에 numpy못써서 고민 좀 많이함
```
---
```
結論:
透過這次的題目了解了python新的語法['' for _ in range(numRows)]知道這個後就容易上手這一題了
```
---
### Result
Runtime: 64 ms, faster than 85.53% of Python3 online submissions for Zigzag Conversion.\
Memory Usage: 14 MB, less than 50.24% of Python3 online submissions for Zigzag Conversion.
