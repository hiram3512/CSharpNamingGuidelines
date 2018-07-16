# C#命名规范中文版/C#编码规范中文版


### 示例

```csharp
/*******************************************************************
 * Description:This is a example class
 * Version: 1.0.0
 * Date: 20180218
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
        /// 事件(Pascal):On前缀
        /// </summary>
        public event EvnetHandler OnEvent;

        /// <summary>
        /// 公有字段(Pascal)
        /// </summary>
        public int Field1;

        /// <summary>
        /// 受保护字段(Pascal)
        /// </summary>
        protected int Field2;

        /// <summary>
        /// 私有字段(Camel)
        /// </summary>
        private int field3;
        
        /// <summary>
        /// 方法(Pascal)
        /// </summary>
        /// <param name="args">参数(Camel)</param>
        public void Method(int args)
        {
            //局部变量(Camel)
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
Delegate|Pascal|`public delegate void EvnetHandler();`
Event|Pascal|`public event EventHandler Exited;`
Public Field|Pascal|`public int Min = 0;`
Protected Field|Pascal|`public int Min = 0;`
private Field|Camel|`public int min = 0;`
Enum|Pascal|`public enum FileMode`
Parameter|Camel|`public static int ToInt32(string value)`
Local Variable|Camel|`void Method(){int number = 10;}`

-----
### 特殊说明

>注释
>>**文件注释**: 文件注释以如下方式进行,在扩展注释时(回车换行时)会自动添加注释行. 
>>  ```csharp
>> /*******************************************************************
>> * Description:This is a example class
>> * Version: 1.0.0
>> * Date: 20180218 
>> * Author: Hiram  
>> * Email: hiramtan@live.com    
>> * Copyright @ www.wikipedia.org
>> *******************************************************************/
>>  ```
>>**命名空间 类型 接口 方法名 属性 事件 字段 枚举**:以"///"的方式注释,编辑器会自动完善注释,并且可以用生成工具直接生成代码注释文档.
>>  ```csharp
>>        /// <summary>
>>        /// 方法(Pascal)
>>        /// </summary>
>>        /// <param name="args">参数(Camel)</param>
>>        public void Method(int args)
>>        {
>>            //局部变量(Camel)
>>            int variable = 10;
>>        }
>>  ```
>>**其他注释**:以"//"的方式注释在上一行或行尾添加注释(比如局部变量,逻辑行)
>>**段落注释**:以如下方式进行
>>```csharp
>>/*
>>        public void Method()
>>        {
>>
>>        }
>>*/
>>```
>>**待办及高亮**:在注释中添加"ToDo"高亮显示注释

>命名空间

>类型
>>泛型默认T,U,V,W...

>接口
>>接口定义以"I"开头,比如`IInterface`,`IPlayer`

>方法

>属性
>>属性都以Pascal方式命名

>委托
>>微软官方建议添加以下两种后缀
>>- EventHandler
>>- Callback
>>微软官方不建议添加以下后缀
>>- ~~Delegate~~

>事件
>>- 微软官方建议:事件参数添加后缀"EventArgs"
>>- 习惯命名:事件以On为前缀(比如OnClick)

>字段
>>微软官方只规定了public/protected以Pascal方式命名,对internal,private类型的字段没有说明,因此各种第三方规范和插件中对私有字段规范也不一致.
>>针对官方的示例代码,书写习惯,智能提示,代码补全和约定俗成的C#规范,建议private采用Camel方式命名,非Private字段采用Pascal方式命名.
>>- public/protected/internal以Pascal方式命名
>>- private以Camel方式命名
>>```csharp
>>        public int Field1;
>>        public static int Field2;
>>        public readonly int Field3;
>>        public const int Field4 = 4;
>>
>>        internal int Field5;
>>        internal static int Field6;
>>        internal readonly int Field7;
>>        internal const int Field8 = 8;
>>
>>        private int field9;
>>        private static int field10;
>>        private readonly int field11;
>>        private const int field8 = 12;
>>```
>>- ~~以m_为前缀的方式不建议(C++命名方式)~~
>>- ~~以_为前缀的方式不建议(ReSharper命名方式)~~
>>- ~~以类型为前缀的方式不建议(比如bool类型的字段以b为前缀,枚举以e为前缀)~~
>>- ~~以类型为后缀的方式不建议(比如单位列表unitList,直接取名为units)~~

>枚举

>参数

>局部变量
>>局部变量可以使用var自动声明类型
