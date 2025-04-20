# 多语言



AngeliA 引擎提供了内置的多语言系统，您可以通过语言窗口编辑多语言内容，然后通过 Key 字符串来获取当前选择的语言对应的内容。

以下代码可输出 Test.Unique.Key 对应的语言内容

<img src="../../images/LanguageTest.png" width="100%"/>

```C#
using AngeliA;

namespace Test;

public static class LanguageTest {

	// Cache the Ange Hash
	private static readonly int KeyID = "Test.Unique.Key".AngeHash();

	[OnGameInitialize]
	internal static void OnGameInitialize () {
		string content = Language.Get(KeyID);
		Debug.Log(content);
	}

}
```

运行结果：
> Test Content

将切换语言为中文，重启游戏后的运行结果：

> 测试内容