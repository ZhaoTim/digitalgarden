---
{"dg-publish":true,"permalink":"/types/value-of/","dgPassFrontmatter":true,"created":"2023-10-10T22:25:13.441+08:00","updated":"2025-03-18T01:05:17.351+08:00"}
---



我们来封装一个泛型，它接收一个对象的类型，返回所有可能属性值的类型。
```ts
type ValueOf<O> = O[keyof O]
```
声明一个对象，测试一下：
```ts
const obj = {
	a: 1,
	b: 2,
	c: 3
} as const;
type Obj = typeof obj;
type ObjValues = ValueOf<Obj>;
```

![Pasted image 20231010223300.png](/img/user/Pasted%20image%2020231010223300.png)