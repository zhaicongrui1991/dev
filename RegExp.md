# 那些容易记混的正则

> 匹配 a 字符(包含 a 字符就可以)
```
/a/.test('javascript') // true
```

> 匹配 a 以外的字符(只要含有除了a以外的字符就可以) ([^a])
```
/[^a]/.test('a') // false
/[^a]/.test('aaa') // false
/[^a]/.test('aaab') // true
/[^a]/.test('你好') // true
```

> 匹配以 a 开头的字符串 (^)
```
/^a/.test('abc') // true
/^a/.test('bca') // false
```

> 匹配不是 a 开头的字符串 (^[^a])
```
/^[^a]/.test('bcd') // true
/^[^a]/.test('bcad') // true
/^[^a]/.test('abcad') // false
```

> 匹配以 a 结尾的字符串($)
```
/a$/.test("javascript") // false
/a$/.test("cba") // true
```

> 匹配不是 a 结尾的字符串 ([^a]$)
```
/[^a]$/.test('abc') // true
/[^a]$/.test('abca') // false
/[^a]$/.test('xyz') // true
```

> 匹配 abc （必须包含'abc'才可以）
```
/abc/.test('abcd') // true
/abc/.test('bcd') // false
```

> 匹配 a,b,c 以外的字符(只要含有a,b,c以外的字符就可以)
```
/[^abc]/.test('a') // false
/[^abc]/.test('ab') // false
/[^abc]/.test('abc') // false
/[^abc]/.test('d') // true
/[^abc]/.test('ad') // true
/[^abc]/.test('abcd') // true
/[^abc]/.test('你好') // true
```

> 匹配以 abc 开头的字符串 (^abc)
```
/^abc/.test('abcde') // true
/^abc/.test('bcde') // false
/^abc/.test('deabc') // false
```

> 匹配以 abc 结尾的字符串 ((abc)$)
```
/abc$/.test('xyzabc') // true
/abc$/.test('xyzab') // false
/abc$/.test('abcxyz') // false
/abc$/.test('abcbc') // false
```

> 匹配字符 a 或 b 或 c ([abc])
```
/[abc]/.test('abcd') // true
/[abc]/.test('a') // true
/[abc]/.test('b') // true
/[abc]/.test('c') // true
```

> 匹配字符串 abc 或 xyz (abc|xyz)
```
/abc|xyz/.test('abc') // true
/abc|xyz/.test('xyz') // true
/abc|xyz/.test('ab') // false
/abc|xyz/.test('xy') // false 
/abc|xyz/.test('abxy') // false
```

> 匹配 script 前面的 java (java(?=script))
```
/java(?=script)/.test('javascript') // true
/java(?=script)/.test('javaee') // false
/java(?=script)/.test('typescript') // false
```

> 匹配 type 后面的 script ((?<=type)script)
```
/(?<=type)script/.test('typescript') // true
/(?<=type)script/.test('javascript') // false
```

> 匹配非 script 前面的 java (java(?!script))
```
/java(?!script)/.test('javascript') // false
/java(?!script)/.test('javascripts') // false
/java(?!script)/.test('javaee') // true
```

> 匹配非 type 后面的 script ((?<!type)script)
```
/(?<!type)script/.test('typescript') // false
/(?<!type)script/.test('javascript') // true
```