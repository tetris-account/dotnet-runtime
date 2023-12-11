C# Coding Style
===============

The general rule we follow is "use Visual Studio defaults".
我们遵循的一般规则是“使用Visual Studio默认值”。

1. We use [Allman style](http://en.wikipedia.org/wiki/Indent_style#Allman_style) braces, where each brace begins on a new line. A single line statement block can go without braces but the block must be properly indented on its own line and must not be nested in other statement blocks that use braces (See rule 18 for more details). One exception is that a `using` statement is permitted to be nested within another `using` statement by starting on the following line at the same indentation level, even if the nested `using` contains a controlled block.  
我们使用[Allman style](http://en.wikipedia.org/wiki/Indent_style#Allman_style)大括号，其中每个大括号开始于新的一行。单行语句块可以不带大括号，但该语句块必须在自己的行上正确缩进，并且不能嵌套在使用大括号的其他语句块中(更多细节请参见规则18)。一个例外是，允许一个using语句嵌套在另一个using语句中，从下一行开始，在相同的缩进级别，即使嵌套的using包含一个受控块。一个例外是，允许一个using语句嵌套在另一个using语句中，从下一行开始，在相同的缩进级别，即使嵌套的using包含一个受控块。

2. We use four spaces of indentation (no tabs).
我们使用四个空格缩进(没有制表符)。

3. We use `_camelCase` for internal and private fields and use `readonly` where possible. Prefix internal and private instance fields with `_`, static fields with `s_` and thread static fields with `t_`. When used on static fields, `readonly` should come after `static` (e.g. `static readonly` not `readonly static`).  Public fields should be used sparingly and should use PascalCasing with no prefix when used.
我们对内部和私有字段使用' _camelCase '，并在可能的情况下使用' readonly '。在内部和私有实例字段前面加上' _ '，静态字段前面加上' s_ '，线程静态字段前面加上' t_ '。当用于静态字段时，“readonly”应该在“static”之后。'静态只读'而不是'只读静态')。公共字段应该谨慎使用，并且在使用时应该使用不带前缀的pascal套管。

4. We avoid `this.` unless absolutely necessary.
我们要避免这种情况。除非绝对必要。

5. We always specify the visibility, even if it's the default (e.g.
   `private string _foo` not `string _foo`). Visibility should be the first modifier (e.g.
   `public abstract` not `abstract public`).
我们总是指定可见性，即使它是默认的(例如:
' private string _foo '不是' string _foo ')。可见性应该是第一个修饰符(例如:
“公共抽象”而不是“抽象公共”)。

6. Namespace imports should be specified at the top of the file, *outside* of
   `namespace` declarations, and should be sorted alphabetically, with the exception of `System.*` namespaces, which are to be placed on top of all others.
命名空间导入应该指定在文件的顶部，*outside* of ' namespace '声明，并应按字母顺序排序，' System '除外。*的命名空间，它将被放置在所有其他命名空间的顶部。

7. Avoid more than one empty line at any time. For example, do not have two
   blank lines between members of a type.
避免在任何时候出现超过一行的空行。例如，不要有两个类型成员之间的空白行。

8. Avoid spurious free spaces.
   For example avoid `if (someVar == 0)...`, where the dots mark the spurious free spaces.
   Consider enabling "View White Space (Ctrl+R, Ctrl+W)" or "Edit -> Advanced -> View White Space" if using Visual Studio to aid detection.
避免虚假的自由空间。
例如，避免' if (someVar == 0)…，其中的圆点标记了虚假的自由空间。
如果使用Visual Studio来辅助检测，请考虑启用“查看留白区(Ctrl+R, Ctrl+W)”或“编辑->高级->查看留白区”。

9. If a file happens to differ in style from these guidelines (e.g. private members are named `m_member`
   rather than `_member`), the existing style in that file takes precedence.
如果一个文件碰巧在风格上与这些准则不同(例如私有成员被命名为' m_member ')
而不是' _member ')，该文件中的现有样式优先。

10. We only use `var` when the type is explicitly named on the right-hand side, typically due to either `new` or an explicit cast, e.g. `var stream = new FileStream(...)` not `var stream = OpenStandardInput()`.
    - Similarly, target-typed `new()` can only be used when the type is explicitly named on the left-hand side, in a variable definition statement or a field definition statement. e.g. `FileStream stream = new(...);`, but not `stream = new(...);` (where the type was specified on a previous line).
只有当类型在右侧显式命名时才使用var，通常是由于' new '或显式强制转换，例如:' var stream = new FileStream(…)'而不是' var stream = OpenStandardInput() '。
-类似地，目标类型的' new() '只能在变量定义语句或字段定义语句的左侧显式命名类型时使用。如。' FileStream stream = new(…);'，但不是' stream = new(…);'(其中类型在前一行指定)。

11. We use language keywords instead of BCL types (e.g. `int, string, float` instead of `Int32, String, Single`, etc) for both type references as well as method calls (e.g. `int.Parse` instead of `Int32.Parse`). See issue [#13976](https://github.com/dotnet/runtime/issues/13976) for examples.
我们使用语言关键字代替BCL类型(例如;' int, string, float '而不是' Int32, string, Single '等)用于类型引用和方法调用(例如:“int。Parse '而不是' Int32.Parse ')。参见问题[#13976](https://github.com/dotnet/runtime/issues/13976)的例子。

12. We use PascalCasing to name all our constant local variables and fields. The only exception is for interop code where the constant value should exactly match the name and value of the code you are calling via interop.
我们使用pascal套管来命名所有的常量局部变量和字段。唯一的例外是互操作代码，其中常量值应该与您通过互操作调用的代码的名称和值完全匹配。

13. We use PascalCasing for all method names, including local functions.
我们对所有方法名都使用pascal套管，包括局部函数名。

14. We use ```nameof(...)``` instead of ```"..."``` whenever possible and relevant.
我们用“……的名字”来代替“……”只要有可能和相关。

15. Fields should be specified at the top within type declarations.
字段应该在类型声明的顶部指定。

16. When including non-ASCII characters in the source code use Unicode escape sequences (\uXXXX) instead of literal characters. Literal non-ASCII characters occasionally get garbled by a tool or editor.
当在源代码中包含非ascii字符时，使用Unicode转义序列(\uXXXX)代替文字字符。文字非ascii字符偶尔会被工具或编辑器弄乱。

17. When using labels (for goto), indent the label one less than the current indentation.
当使用标签时(对于goto)，将标签缩进比当前缩进少一个。

18. When using a single-statement if, we follow these conventions:
    - Never use single-line form (for example: `if (source == null) throw new ArgumentNullException("source");`)
    - Using braces is always accepted, and required if any block of an `if`/`else if`/.../`else` compound statement uses braces or if a single statement body spans multiple lines.
    - Braces may be omitted only if the body of *every* block associated with an `if`/`else if`/.../`else` compound statement is placed on a single line.
当使用单语句if时，我们遵循以下约定:
-永远不要使用单行形式(例如:' if (source == null) throw new ArgumentNullException("source"); ')
-使用大括号总是可以接受的，如果' if ' / ' else if ' /…/ ' else '复合语句使用大括号，或者如果单个语句体跨越多行。
-只有当*每个*块的主体与' if ' / ' else if ' /…/ ' else '复合语句放在单行上。

19. Make all internal and private types static or sealed unless derivation from them is required.  As with any implementation detail, they can be changed if/when derivation is required in the future.
将所有内部类型和私有类型设置为静态或密封，除非需要从它们派生。与任何实现细节一样，如果/当将来需要派生时，可以更改它们。

An [EditorConfig](https://editorconfig.org "EditorConfig homepage") file (`.editorconfig`) has been provided at the root of the runtime repository, enabling C# auto-formatting conforming to the above guidelines.
一个[EditorConfig](https://editorconfig.org "EditorConfig主页")文件(' . EditorConfig ')已经在运行时存储库的根目录下提供，使c#自动格式化符合上述指导方针。

We also use the [.NET Codeformatter Tool](https://github.com/dotnet/codeformatter) to ensure the code base maintains a consistent style over time, the tool automatically fixes the code base to conform to the guidelines outlined above.
我们也用[。. NET Codeformatter Tool](https://github.com/dotnet/codeformatter)以确保代码库随着时间的推移保持一致的风格，该工具会自动修复代码库以符合上面概述的指导方针。

### Example File:

``ObservableLinkedList`1.cs:``

```C#
using System;
using System.Collections;
using System.Collections.Generic;
using System.Collections.Specialized;
using System.ComponentModel;
using System.Diagnostics;
using Microsoft.Win32;

namespace System.Collections.Generic
{
    public partial class ObservableLinkedList<T> : INotifyCollectionChanged, INotifyPropertyChanged
    {
        private ObservableLinkedListNode<T> _head;
        private int _count;

        public ObservableLinkedList(IEnumerable<T> items)
        {
            if (items == null)
                throw new ArgumentNullException(nameof(items));

            foreach (T item in items)
            {
                AddLast(item);
            }
        }

        public event NotifyCollectionChangedEventHandler CollectionChanged;

        public int Count
        {
            get { return _count; }
        }

        public ObservableLinkedListNode AddLast(T value)
        {
            var newNode = new LinkedListNode<T>(this, value);

            InsertNodeBefore(_head, node);
        }

        protected virtual void OnCollectionChanged(NotifyCollectionChangedEventArgs e)
        {
            NotifyCollectionChangedEventHandler handler = CollectionChanged;
            if (handler != null)
            {
                handler(this, e);
            }
        }

        private void InsertNodeBefore(LinkedListNode<T> node, LinkedListNode<T> newNode)
        {
            ...
        }

        ...
    }
}
```

``ObservableLinkedList`1.ObservableLinkedListNode.cs:``

```C#
using System;

namespace System.Collections.Generics
{
    partial class ObservableLinkedList<T>
    {
        public class ObservableLinkedListNode
        {
            private readonly ObservableLinkedList<T> _parent;
            private readonly T _value;

            internal ObservableLinkedListNode(ObservableLinkedList<T> parent, T value)
            {
                Debug.Assert(parent != null);

                _parent = parent;
                _value = value;
            }

            public T Value
            {
                get { return _value; }
            }
        }

        ...
    }
}
```

For other languages, our current best guidance is consistency. When editing files, keep new code and changes consistent with the style in the files. For new files, it should conform to the style for that component. If there is a completely new component, anything that is reasonably broadly accepted is fine. For script files, please refer to the scripting blog for [tips](https://devblogs.microsoft.com/scripting/tag/powertip) and [best practices](https://devblogs.microsoft.com/scripting/tag/best-practices).
