<p id="罗马数字转整数"></p>



<p id="二进制求和"></p>





<p id="最常见的单词"></p>





<p id="亲密字符串"></p>


### 686. 重复叠加字符串匹配

[力扣原题链接（点我直达）](https://leetcode-cn.com/problems/repeated-string-match/)

给定两个字符串 A 和 B, 寻找重复叠加字符串A的最小次数，使得字符串B成为叠加后的字符串A的子串，如果不存在则返回 -1。

举个例子，A = "abcd"，B = "cdabcdab"。

答案为 3， 因为 A 重复叠加三遍后为 “abcdabcdabcd”，此时 B 是其子串；A 重复叠加两遍后为"abcdabcd"，B 并不是其子串。

**注意:**

 `A` 与 `B` 字符串的长度在1和10000区间范围内。





#### 第一版，很精妙,很经典，很厉害

执行用时 :16 ms, 在所有 cpp 提交中击败了92.28%的用户

内存消耗 :9.2 MB, 在所有 cpp 提交中击败了78.79%的用户

```c++
if (A.empty()) {
		return -1;
	}
	string T = A;
	int i = 1;
	while (T.size() < B.size()) {
		T.append(A);
		++i;
	}
	//A的长度大于等于B了
	if (T.find(B) != string::npos) {//顺序增长的就可以了,比如abcd 和 abcdabcdabcd
		return i;
	}
	T.append(A);
	++i;
	if (T.find(B) != string::npos) { //不是按序增长，比如abcd 和 cdabcdabcdabcdab
		return i;
	}
	return -1;

```

<p id="验证回文字符串"></p>



