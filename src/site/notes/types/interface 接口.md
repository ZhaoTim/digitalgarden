---
{"dg-publish":true,"permalink":"/types/interface/","dgPassFrontmatter":true,"created":"2023-10-06T16:05:38.619+08:00","updated":"2025-03-18T01:05:06.888+08:00"}
---

我来声明一个interface -> Square,正方形。
```ts
interface Square {
	width: number;
}
```

我还想声明一个长方形，它继承了Square。
```ts
interface Rectangle extends Square {
	height: number;
}
```

此时！如果某个变量的类型是 Rectangle接口，那么它必须是一个拥有width和height的对象！