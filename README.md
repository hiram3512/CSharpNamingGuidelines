# C#命名规范中文版


### 示例

```csharp
/*******************************************************************
 * Description:This is a example class
 * Version: 1.0.0
 * Date: 20131031 
 * Author: Hiram  
 * Email: hiramtan@live.com    
 * Copyright @ www.wikipedia.org
 *******************************************************************/

using System;

/// <summary>
/// 命名空间(Pascal)
/// </summary>
namespace Namespace
{
    /// <summary>
    /// 类(Pascal)
    /// </summary>
    public class Class
    {
        /// <summary>
        /// 属性(Pascal)
        /// </summary>
        public int Property { get; set; }

        /// <summary>
        /// 委托(Pascal)
        /// EventHandler后缀
        /// </summary>
        public delegate void EvnetHandler();

        /// <summary>
        /// 事件
        /// On前缀
        /// </summary>
        public event EvnetHandler OnEvent;

        /// <summary>
        /// 私有字段(Camel)
        /// </summary>
        private int field1;

        /// <summary>
        /// 私有只读字段(Camel)
        /// </summary>
        private readonly int field2;

        /// <summary>
        /// 私有静态字段(Camel)
        /// </summary>
        private static int field3;

        /// <summary>
        /// 私有常量(Camel)
        /// </summary>
        private const int field4 = 4;

        /// <summary>
        /// 公有字段(Pascal)
        /// </summary>
        public int Field5;

        /// <summary>
        /// 公有只读字段(Pascal)
        /// </summary>
        public readonly int Field6;

        /// <summary>
        /// 公有静态字段(Pascal)
        /// </summary>
        public static int Field7;

        /// <summary>
        /// 公有常量(Pascal)
        /// </summary>
        public const int Field8 = 8;

        /// <summary>
        /// 方法(Pascal)
        /// </summary>
        /// <param name="args">参数(Camel)</param>
        public void Method(int args)
        {
            //变量(Camel)
            int variable = 10;
        }
    }

    /// <summary>
    /// 接口(Pascal)
    /// </summary>
    public interface IInterface
    {
        /// <summary>
        /// 属性接口(Pascal)
        /// </summary>
        int Property { get; set; }

        /// <summary>
        /// 方法接口(Pascal)
        /// </summary>
        /// <param name="args"></param>
        void Method(int args);
    }

    /// <summary>
    /// 枚举(Pascal)
    /// </summary>
    enum Enum
    {
        Enum1,//枚举值(Pascal)
        Enum2,//枚举值(Pascal)
    }
}
```
-----
### 参考资料

- 微软官方老版本:[https://msdn.microsoft.com/en-us/library/ms229043(v=vs.100).aspx](https://msdn.microsoft.com/en-us/library/ms229043(v=vs.100).aspx)
- 微软官方新版本:[https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/capitalization-conventions](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/capitalization-conventions)
- ReSharper:[https://www.jetbrains.com/help/resharper/Coding_Assistance__Naming_Style.html](https://www.jetbrains.com/help/resharper/Coding_Assistance__Naming_Style.html)
- dofactory:[http://www.dofactory.com/reference/csharp-coding-standards](http://www.dofactory.com/reference/csharp-coding-standards)
- [https://github.com/ktaranov/naming-convention/blob/master/C%23%20Coding%20Standards%20and%20Naming%20Conventions.md](https://github.com/ktaranov/naming-convention/blob/master/C%23%20Coding%20Standards%20and%20Naming%20Conventions.md)
- [https://gist.github.com/jburditt/3178227739d3a604663e58fc2e6c15c5](https://gist.github.com/jburditt/3178227739d3a604663e58fc2e6c15c5)
- [https://www.jianshu.com/p/0d09cc624dae](https://www.jianshu.com/p/0d09cc624dae)
- [https://github.com/wanfangdata/guide/blob/master/dotnet%E5%BC%80%E5%8F%91%E8%A7%84%E8%8C%83/%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83.md](https://github.com/wanfangdata/guide/blob/master/dotnet%E5%BC%80%E5%8F%91%E8%A7%84%E8%8C%83/%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83.md)
- [https://gist.github.com/zhuqling/a2700703d088b8746f0c](https://gist.github.com/zhuqling/a2700703d088b8746f0c)

-----
### 通用规则
所有的命名都是以下面两种方式进行命名:
- PascalCasing(匈牙利命名法:每个词的第一个字母大写)
- camelCasing(骆驼命名法:第一个词的第一个字母小写,之后每个词的第一个字母大写)



类型|命名方式|示例
---|:--:|---:
Namespace|Pascal|`namespace System.Security { ... }`
Type|Pascal|`public class StreamReader { ... }`
Interface|Pascal|`public interface IEnumerable { ... }`
Method|Pascal|`public virtual string ToString();`
Property|Pascal|`public int Length { get; }`
Event|Pascal|`public event EventHandler Exited;`
Field|Pascal|`public int Min = 0;`
Enum|Pascal|`public enum FileMode`
Parameter|Camel|`public static int ToInt32(string value)`
Variable|Camel|`void Method(){int number = 10;}`

-----
### 命名细节

<font color=#0000FF size=5>注释</font>

**文件注释**: 文件注释以如下方式进行,在扩展注释时(回车换行时)会自动添加注释行.
 
  ```csharp
 /*******************************************************************
 * Description:This is a example class
 * Version: 1.0.0
 * Date: 20131031 
 * Author: Hiram  
 * Email: hiramtan@live.com    
 * Copyright @ www.wikipedia.org
 *******************************************************************/
  ```
**命名空间 类型 接口 方法名 属性 事件 字段 枚举 变量**:以"///"的方式注释,编辑器会自动完善注释,并且可以用生成工具直接生成代码注释文档.
  ```csharp
        /// <summary>
        /// 方法(Pascal)
        /// </summary>
        /// <param name="args">参数(Camel)</param>
        public void Method(int args)
        {
            //变量(Camel)
            int variable = 10;
        }
  ```
**其他注释**:以"//"的方式注释在上一行或行尾添加注释(比如局部变量,逻辑行)

**段落注释**:以如下方式进行
```csharp
/*
        public void Method()
        {

        }
*/
```
<font color=#0000FF size=5>命名空间</font>

<font color=#0000FF size=5>类型</font>

<font color=#0000FF size=5>接口</font>

<font color=#0000FF size=5>方法名</font>

<font color=#0000FF size=5>属性</font>

<font color=#0000FF size=5>字段</font>

<font color=#0000FF size=5>枚举</font>

<font color=#0000FF size=5>参数</font>

<font color=#0000FF size=5>变量</font>

### 详细示例

