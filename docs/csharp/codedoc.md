---
title: "XML 주석을 사용하여 코드 문서화"
description: "코드 문서화"
keywords: .NET, .NET Core
author: tsolarin
ms.author: wiwagn
ms.date: 02/14/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3f4add34162d8b63d033d7cb32828af67901eb11
ms.lasthandoff: 03/13/2017

---

# <a name="documenting-your-code-with-xml-comments"></a>XML 주석을 사용하여 코드 문서화

XML 문서 주석은 사용자 정의 형식이나 멤버의 정의 위에 추가되는 특수 주석입니다. 컴파일 시간에 XML 문서 파일을 생성하기 위해 컴파일러에서 처리될 수 있으므로 특별합니다.
Visual Studio 및 기타 IDE가 IntelliSense를 사용하여 형식이나 멤버에 대한 빠른 정보를 표시할 수 있도록 컴파일러에서 생성된 XML 파일은 .NET 어셈블리와 함께 배포될 수 있습니다. 또한 [DocFX](https://dotnet.github.io/docfx/) 및 [Sandcastle](https://github.com/EWSoftware/SHFB) 같은 도구를 통해 XML 파일을 실행하여 API 참조 웹 사이트를 생성할 수 있습니다.

XML 문서 주석은 모든 다른 주석처럼 컴파일러에서 무시됩니다.

다음 중 하나를 수행하여 컴파일 시간에 XML 파일을 생성할 수 있습니다.

- 명령줄에서 .NET Core를 사용하여 응용 프로그램을 개발할 경우 .csproj 프로젝트 파일의 `<PropertyGroup>` 섹션에 [DocumentationFile 요소](http://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties)를 추가할 수 있습니다. 다음 예제에서는 프로젝트 디렉터리에 프로젝트와 같은 루트 파일 이름을 가진 XML 파일을 생성합니다.

   ```xml
   <DocumentationFile>$(MSBuildProjectName).xml</DocumentationFile>
   ```

   XML 파일의 정확한 절대 또는 상대 경로를 지정할 수도 있습니다. 다음 예제에서는 응용 프로그램의 디버그 버전과 같은 디렉터리에 XML 파일을 생성합니다.

    ```xml
   <DocumentationFile>bin\Debug\netcoreapp1.0\App.xml</DocumentationFile>
   ```

- Visual Studio를 사용하여 응용 프로그램을 개발할 경우 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. [속성] 대화 상자에서 **빌드** 탭을 선택하고 **XML 문서 파일**을 선택합니다. 컴파일러가 파일을 쓰는 위치를 변경할 수도 있습니다. 

- 명령줄에서 .NET Framework 응용 프로그램을 컴파일할 경우 컴파일 시 [/doc 컴파일러 옵션](language-reference/compiler-options/doc-compiler-option.md)을 추가합니다.  

XML 문서 주석에는 삼중 슬래시(`///`) 및 XML 형식의 주석 본문이 사용됩니다. 예:

```csharp
/// <summary>
/// This class does something.
/// </summary>
public class SomeClass
{
}
```

## <a name="walkthrough"></a>연습

새로운 개발자가 이해/사용하고 타사 개발자가 사용하기 쉬운 매우 기본적인 수학 라이브러리를 문서화하는 방법을 살펴보겠습니다.

다음은 간단한 수학 라이브러리에 대한 코드입니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
public class Math
{
    // Adds two integers and returns the result
    public static int Add(int a, int b)
    {
        // If any parameter is equal to the max value of an integer
        // and the other is greater than zero
        if ((a == int.MaxValue && b > 0) || (b == int.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }

    // Adds two doubles and returns the result
    public static double Add(double a, double b)
    {
        if ((a == double.MaxValue && b > 0) || (b == double.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }

    // Subtracts an integer from another and returns the result
    public static int Subtract(int a, int b)
    {
        return a - b;
    }

    // Subtracts a double from another and returns the result
    public static double Subtract(double a, double b)
    {
        return a - b;
    }

    // Multiplies two integers and returns the result
    public static int Multiply(int a, int b)
    {
        return a * b;
    }

    // Multiplies two doubles and returns the result
    public static double Multiply(double a, double b)
    {
        return a * b;
    }

    // Divides an integer by another and returns the result
    public static int Divide(int a, int b)
    {
        return a / b;
    }

    // Divides a double by another and returns the result
    public static double Divide(double a, double b)
    {
        return a / b;
    }
}
```

샘플 라이브러리는 `int` 및 `double` 데이터 형식에서 네 가지 주요 산술 연산인 `add`, `subtract`, `multiply` 및 `divide`를 지원합니다.

이제 라이브러리를 사용하지만 소스 코드에 대한 액세스 권한이 없는 타사 개발자를 위해 코드에서 API 참조 문서를 만들 수 있습니다.
앞에서 설명한 대로 XML 문서 태그를 사용하여 이 작업을 수행할 수 있습니다. 이제 C# 컴파일러에서 지원하는 표준 XML 태그를 소개합니다.

### <a name="ltsummarygt"></a>&lt;요약&gt;

`<summary>` 태그는 형식 또는 멤버에 대한 간단한 정보를 추가합니다.
`Math` 클래스 정의 및 첫 번째 `Add` 메서드에 태그를 추가하여 사용하는 방법을 설명합니다. 나머지 코드에 자유롭게 적용하세요.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main Math class.
/// Contains all methods for performing basic math functions.
/// </summary>
public class Math
{
    // Adds two integers and returns the result
    /// <summary>
    /// Adds two integers and returns the result.
    /// </summary>
    public static int Add(int a, int b)
    {
        // If any parameter is equal to the max value of an integer
        // and the other is greater than zero
        if ((a == int.MaxValue && b > 0) || (b == int.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }
}
```

`<summary>` 태그는 매우 중요하고 태그 내용은 IntelliSense 또는 API 참조 문서에서 형식 또는 멤버 정보의 기본 소스이므로 포함하는 것이 좋습니다.

### <a name="ltremarksgt"></a>&lt;설명&gt;

`<remarks>` 태그는 `<summary>` 태그가 제공하는 형식 또는 멤버에 대한 정보를 보완합니다. 이 예제에서는 클래스에 태그를 추가합니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main Math class.
/// Contains all methods for performing basic math functions.
/// </summary>
/// <remarks>
/// This class can add, subtract, multiply and divide.
/// </remarks>
public class Math
{

}
```

### <a name="ltreturnsgt"></a>&lt;returns&gt;

`<returns>` 태그는 메서드 선언의 반환 값을 설명합니다.
이전과 같이 다음 예제에서는 첫 번째 `Add` 메서드에 대한 `<returns>` 태그를 보여 줍니다. 다른 메서드에 대해 같은 작업을 수행할 수 있습니다.

```csharp
// Adds two integers and returns the result
/// <summary>
/// Adds two integers and returns the result.
/// </summary>
/// <returns>
/// The sum of two integers.
/// </returns>
public static int Add(int a, int b)
{
    // If any parameter is equal to the max value of an integer
    // and the other is greater than zero
    if ((a == int.MaxValue && b > 0) || (b == int.MaxValue && a > 0))
        throw new System.OverflowException();

    return a + b;
}
```

### <a name="ltvaluegt"></a>&lt;value&gt;

`<value>` 태그는 속성에 사용한다는 점을 제외하고 `<returns>` 태그와 비슷합니다.
`Math` 라이브러리에 `PI`라는 정적 속성이 있다고 가정할 경우 이 태그를 사용하는 방법은 다음과 같습니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main Math class.
/// Contains all methods for performing basic math functions.
/// </summary>
/// <remarks>
/// This class can add, subtract, multiply and divide.
/// These operations can be performed on both integers and doubles
/// </remarks>
public class Math
{
    /// <value>Gets the value of PI.</value>
    public static double PI { get; }
}
```

### <a name="ltexamplegt"></a>&lt;example&gt;

`<example>` 태그를 사용하여 XML 문서에 예제를 포함합니다.
이 과정에는 자식 `<code>` 태그 사용이 포함됩니다.

```csharp
// Adds two integers and returns the result
/// <summary>
/// Adds two integers and returns the result.
/// </summary>
/// <returns>
/// The sum of two integers.
/// </returns>
/// <example>
/// <code>
/// int c = Math.Add(4, 5);
/// if (c > 10)
/// {
///     Console.WriteLine(c);
/// }
/// </code>
/// </example>
public static int Add(int a, int b)
{
    // If any parameter is equal to the max value of an integer
    // and the other is greater than zero
    if ((a == int.MaxValue && b > 0) || (b == int.MaxValue && a > 0))
        throw new System.OverflowException();

    return a + b;
}
```

`code` 태그는 더 긴 예제에 대한 줄 바꿈 및 들여쓰기를 보존합니다.

### <a name="ltparagt"></a>&lt;para&gt;

`<para>` 태그를 사용하여 부모 태그 내에서 내용의 서식을 지정합니다. `<para>`는 보통 `<remarks>` 또는 `<returns>`와 같은 태그 내부에서 텍스트를 단락으로 나누는 데 사용됩니다.
계속해서 클래스 정의에 대한 `<remarks>` 태그의 내용에 대한 서식을 지정할 수 있습니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main Math class.
/// Contains all methods for performing basic math functions.
/// </summary>
/// <remarks>
/// <para>This class can add, subtract, multiply and divide.</para>
/// <para>These operations can be performed on both integers and doubles.</para>
/// </remarks>
public class Math
{

}
```

### <a name="ltcgt"></a>&lt;c&gt;

서식 지정 항목에서 텍스트 부분을 코드로 표시하는 데 `<c>` 태그를 사용합니다.
`<code>` 태그와 비슷하지만 인라인입니다. 태그 내용의 일부로 빠른 코드 예제를 표시하려는 경우 유용합니다.
`Math` 클래스에 대한 문서를 업데이트해 보겠습니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main <c>Math</c> class.
/// Contains all methods for performing basic math functions.
/// </summary>
public class Math
{

}
```

### <a name="ltexceptiongt"></a>&lt;exception&gt;

`<exception>` 태그를 사용하여 메서드가 특정 예외를 throw할 수 있음을 개발자에게 알립니다.
`Math` 라이브러리를 살펴보면 특정 조건에 해당할 경우 두 `Add` 메서드가 모두 예외를 throw함을 알 수 있습니다. `b` 매개 변수가 0인 경우 정수 `Divide` 메서드도 throw하는지는 분명하지 않습니다. 이제 이 메서드에 예외 문서를 추가합니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main <c>Math</c> class.
/// Contains all methods for performing basic math functions.
/// </summary>
public class Math
{
    /// <summary>
    /// Adds two integers and returns the result.
    /// </summary>
    /// <returns>
    /// The sum of two integers.
    /// </returns>
    /// <example>
    /// <code>
    /// int c = Math.Add(4, 5);
    /// if (c > 10)
    /// {
    ///     Console.WriteLine(c);
    /// }
    /// </code>
    /// </example>
    /// <exception cref="System.OverflowException">Thrown when one parameter is max 
    /// and the other is greater than 0.</exception>
    public static int Add(int a, int b)
    {
        if ((a == int.MaxValue && b > 0) || (b == int.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }

    /// <summary>
    /// Adds two doubles and returns the result.
    /// </summary>
    /// <returns>
    /// The sum of two doubles.
    /// </returns>
    /// <exception cref="System.OverflowException">Thrown when one parameter is max 
    /// and the other is greater than zero.</exception>
    public static double Add(double a, double b)
    {
        if ((a == double.MaxValue && b > 0) || (b == double.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }

    /// <summary>
    /// Divides an integer by another and returns the result.
    /// </summary>
    /// <returns>
    /// The division of two integers.
    /// </returns>
    /// <exception cref="System.DivideByZeroException">Thrown when a division by zero occurs.</exception>
    public static int Divide(int a, int b)
    {
        return a / b;
    }

    /// <summary>
    /// Divides a double by another and returns the result.
    /// </summary>
    /// <returns>
    /// The division of two doubles.
    /// </returns>
    public static double Divide(double a, double b)
    {
        return a / b;
    }
}
```

`cref` 특성은 현재 컴파일 환경에서 사용할 수 있는 예외에 대한 참조를 나타냅니다.
이 특성은 프로젝트 또는 참조된 어셈블리에서 정의된 형식일 수 있습니다. 값을 확인할 수 없는 경우 컴파일러에서 경고를 표시합니다.

### <a name="ltseegt"></a>&lt;see&gt;

`<see>` 태그를 사용하여 다른 코드 요소에 대한 문서 페이지의 클릭 가능한 링크를 만들 수 있습니다. 다음 예제에서는 두 `Add` 메서드 간의 클릭 가능한 링크를 만듭니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main <c>Math</c> class.
/// Contains all methods for performing basic math functions.
/// </summary>
public class Math
{
    /// <summary>
    /// Adds two integers and returns the result.
    /// </summary>
    /// <returns>
    /// The sum of two integers.
    /// </returns>
    /// <example>
    /// <code>
    /// int c = Math.Add(4, 5);
    /// if (c > 10)
    /// {
    ///     Console.WriteLine(c);
    /// }
    /// </code>
    /// </example>
    /// <exception cref="System.OverflowException">Thrown when one parameter is max 
    /// and the other is greater than 0.</exception>
    /// See <see cref="Math.Add(double, double)"/> to add doubles.
    public static int Add(int a, int b)
    {
        if ((a == int.MaxValue && b > 0) || (b == int.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }

    /// <summary>
    /// Adds two doubles and returns the result.
    /// </summary>
    /// <returns>
    /// The sum of two doubles.
    /// </returns>
    /// <exception cref="System.OverflowException">Thrown when one parameter is max 
    /// and the other is greater than zero.</exception>
    /// See <see cref="Math.Add(int, int)"/> to add integers.
    public static double Add(double a, double b)
    {
        if ((a == double.MaxValue && b > 0) || (b == double.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }
}
```

`cref`는 현재 컴파일 환경에서 사용할 수 있는 형식 또는 멤버에 대한 참조를 나타내는 **required** 특성입니다. 이 특성은 프로젝트 또는 참조된 어셈블리에서 정의된 형식일 수 있습니다.

### <a name="ltseealsogt"></a>&lt;seealso&gt;

`<seealso>` 태그는 `<see>` 태그와 같은 방법으로 사용합니다. 유일한 차이점은 내용이 일반적으로 "참고 항목" 섹션에 배치된다는 것입니다. 이제 정수 `Add` 메서드에 대해 `seealso` 태그를 추가하여 클래스에서 정수 매개 변수를 허용하는 다른 메서드를 참조합니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main <c>Math</c> class.
/// Contains all methods for performing basic math functions.
/// </summary>
public class Math
{
    /// <summary>
    /// Adds two integers and returns the result.
    /// </summary>
    /// <returns>
    /// The sum of two integers.
    /// </returns>
    /// <example>
    /// <code>
    /// int c = Math.Add(4, 5);
    /// if (c > 10)
    /// {
    ///     Console.WriteLine(c);
    /// }
    /// </code>
    /// </example>
    /// <exception cref="System.OverflowException">Thrown when one parameter is max 
    /// and the other is greater than 0.</exception>
    /// See <see cref="Math.Add(double, double)"/> to add doubles.
    /// <seealso cref="Math.Subtract(int, int)"/>
    /// <seealso cref="Math.Multiply(int, int)"/>
    /// <seealso cref="Math.Divide(int, int)"/>
    public static int Add(int a, int b)
    {
        if ((a == int.MaxValue && b > 0) || (b == int.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }
}
```

`cref`는 현재 컴파일 환경에서 사용할 수 있는 형식 또는 멤버에 대한 참조를 나타냅니다.
이 특성은 프로젝트 또는 참조된 어셈블리에서 정의된 형식일 수 있습니다.

### <a name="ltparamgt"></a>&lt;param&gt;

`<param>` 태그를 사용하여 메서드의 매개 변수를 설명합니다. 다음은 double `Add` 메서드에 대한 예제입니다. 태그가 설명하는 매개 변수는 **required** `name` 특성에서 지정됩니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main <c>Math</c> class.
/// Contains all methods for performing basic math functions.
/// </summary>
public class Math
{
    /// <summary>
    /// Adds two doubles and returns the result.
    /// </summary>
    /// <returns>
    /// The sum of two doubles.
    /// </returns>
    /// <exception cref="System.OverflowException">Thrown when one parameter is max 
    /// and the other is greater than zero.</exception>
    /// See <see cref="Math.Add(int, int)"/> to add integers.
    /// <param name="a">A double precision number.</param>
    /// <param name="b">A double precision number.</param>
    public static double Add(double a, double b)
    {
        if ((a == double.MaxValue && b > 0) || (b == double.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }
}
```

### <a name="lttypeparamgt"></a>&lt;typeparam&gt;

`<typeparam>` 태그는 `<param>` 태그처럼 사용하지만 제네릭 매개 변수를 설명하는 제네릭 형식 또는 메서드 선언에 사용합니다.
계속해서 `Math` 클래스에 빠른 제네릭 메서드를 추가하여 한 수량이 다른 수량보다 큰지 확인합니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main <c>Math</c> class.
/// Contains all methods for performing basic math functions.
/// </summary>
public class Math
{
    /// <summary>
    /// Checks if an IComparable is greater than another.
    /// </summary>
    /// <typeparam name="T">A type that inherits from the IComparable interface.</typeparam>
    public static bool GreaterThan<T>(T a, T b) where T : IComparable
    {
        return a.CompareTo(b) > 0;
    }
}
```

### <a name="ltparamrefgt"></a>&lt;paramref&gt;

`<summary>` 태그와 같은 태그에서 메서드가 수행하는 작업을 설명하는 동안 매개 변수에 대한 참조를 만들려고 할 경우 `<paramref>` 태그를 사용하는 것이 좋습니다. double 기반 `Add` 메서드의 요약을 업데이트해 보겠습니다. `<param>` 태그처럼 매개 변수 이름은 **required** `name` 특성에서 지정됩니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main <c>Math</c> class.
/// Contains all methods for performing basic math functions.
/// </summary>
public class Math
{
    /// <summary>
    /// Adds two doubles <paramref name="a"/> and <paramref name="b"/> and returns the result.
    /// </summary>
    /// <returns>
    /// The sum of two doubles.
    /// </returns>
    /// <exception cref="System.OverflowException">Thrown when one parameter is max 
    /// and the other is greater than zero.</exception>
    /// See <see cref="Math.Add(int, int)"/> to add integers.
    /// <param name="a">A double precision number.</param>
    /// <param name="b">A double precision number.</param>
    public static double Add(double a, double b)
    {
        if ((a == double.MaxValue && b > 0) || (b == double.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }
}
```

### <a name="lttypeparamrefgt"></a>&lt;typeparamref&gt;

`<typeparamref>` 태그는 `<paramref>` 태그처럼 사용하지만 제네릭 매개 변수를 설명하는 제네릭 형식 또는 메서드 선언에 사용합니다.
이전에 만든 것과 같은 제네릭 메서드를 사용할 수 있습니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main <c>Math</c> class.
/// Contains all methods for performing basic math functions.
/// </summary>
public class Math
{
    /// <summary>
    /// Checks if an IComparable <typeparamref name="T"/> is greater than another.
    /// </summary>
    /// <typeparam name="T">A type that inherits from the IComparable interface.</typeparam>
    public static bool GreaterThan<T>(T a, T b) where T : IComparable
    {
        return a.CompareTo(b) > 0;
    }
}
```

### <a name="ltlistgt"></a>&lt;list&gt;

`<list>` 태그를 사용하여 문서 정보의 서식을 순서가 지정된 목록, 순서가 지정되지 않은 목록 또는 표로 지정합니다.
`Math` 라이브러리에서 지원하는 모든 수학 연산의 순서가 지정되지 않은 목록을 만듭니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main <c>Math</c> class.
/// Contains all methods for performing basic math functions.
/// <list type="bullet">
/// <item>
/// <term>Add</term>
/// <description>Addition Operation</description>
/// </item>
/// <item>
/// <term>Subtract</term>
/// <description>Subtraction Operation</description>
/// </item>
/// <item>
/// <term>Multiply</term>
/// <description>Multiplication Operation</description>
/// </item>
/// <item>
/// <term>Divide</term>
/// <description>Division Operation</description>
/// </item>
/// </list>
/// </summary>
public class Math
{

}
```

`type` 특성을 각각 `number` 또는 `table`로 변경하여 순서가 지정된 목록 또는 표를 만들 수 있습니다.

### <a name="putting-it-all-together"></a>전체 과정

이 자습서에 따라 필요한 경우 코드에 태그를 적용했습니다. 이제 코드는 다음과 같이 표시되어야 합니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <summary>
/// The main <c>Math</c> class.
/// Contains all methods for performing basic math functions.
/// <list type="bullet">
/// <item>
/// <term>Add</term>
/// <description>Addition Operation</description>
/// </item>
/// <item>
/// <term>Subtract</term>
/// <description>Subtraction Operation</description>
/// </item>
/// <item>
/// <term>Multiply</term>
/// <description>Multiplication Operation</description>
/// </item>
/// <item>
/// <term>Divide</term>
/// <description>Division Operation</description>
/// </item>
/// </list>
/// </summary>
/// <remarks>
/// <para>This class can add, subtract, multiply and divide.</para>
/// <para>These operations can be performed on both integers and doubles.</para>
/// </remarks>
public class Math
{
    // Adds two integers and returns the result
    /// <summary>
    /// Adds two integers <paramref name="a"/> and <paramref name="b"/> and returns the result.
    /// </summary>
    /// <returns>
    /// The sum of two integers.
    /// </returns>
    /// <example>
    /// <code>
    /// int c = Math.Add(4, 5);
    /// if (c > 10)
    /// {
    ///     Console.WriteLine(c);
    /// }
    /// </code>
    /// </example>
    /// <exception cref="System.OverflowException">Thrown when one parameter is max 
    /// and the other is greater than 0.</exception>
    /// See <see cref="Math.Add(double, double)"/> to add doubles.
    /// <seealso cref="Math.Subtract(int, int)"/>
    /// <seealso cref="Math.Multiply(int, int)"/>
    /// <seealso cref="Math.Divide(int, int)"/>
    /// <param name="a">An integer.</param>
    /// <param name="b">An integer.</param>
    public static int Add(int a, int b)
    {
        // If any parameter is equal to the max value of an integer
        // and the other is greater than zero
        if ((a == int.MaxValue && b > 0) || (b == int.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }

    // Adds two doubles and returns the result
    /// <summary>
    /// Adds two doubles <paramref name="a"/> and <paramref name="b"/> and returns the result.
    /// </summary>
    /// <returns>
    /// The sum of two doubles.
    /// </returns>
    /// <example>
    /// <code>
    /// double c = Math.Add(4.5, 5.4);
    /// if (c > 10)
    /// {
    ///     Console.WriteLine(c);
    /// }
    /// </code>
    /// </example>
    /// <exception cref="System.OverflowException">Thrown when one parameter is max 
    /// and the other is greater than 0.</exception>
    /// See <see cref="Math.Add(int, int)"/> to add integers.
    /// <seealso cref="Math.Subtract(double, double)"/>
    /// <seealso cref="Math.Multiply(double, double)"/>
    /// <seealso cref="Math.Divide(double, double)"/>
    /// <param name="a">A double precision number.</param>
    /// <param name="b">A double precision number.</param>
    public static double Add(double a, double b)
    {
        // If any parameter is equal to the max value of an integer
        // and the other is greater than zero
        if ((a == double.MaxValue && b > 0) || (b == double.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }

    // Subtracts an integer from another and returns the result
    /// <summary>
    /// Subtracts <paramref name="b"/> from <paramref name="a"/> and returns the result.
    /// </summary>
    /// <returns>
    /// The difference between two integers.
    /// </returns>
    /// <example>
    /// <code>
    /// int c = Math.Subtract(4, 5);
    /// if (c > 1)
    /// {
    ///     Console.WriteLine(c);
    /// }
    /// </code>
    /// </example>
    /// See <see cref="Math.Subtract(double, double)"/> to subtract doubles.
    /// <seealso cref="Math.Add(int, int)"/>
    /// <seealso cref="Math.Multiply(int, int)"/>
    /// <seealso cref="Math.Divide(int, int)"/>
    /// <param name="a">An integer.</param>
    /// <param name="b">An integer.</param>
    public static int Subtract(int a, int b)
    {
        return a - b;
    }

    // Subtracts a double from another and returns the result
    /// <summary>
    /// Subtracts a double <paramref name="b"/> from another double <paramref name="a"/> and returns the result.
    /// </summary>
    /// <returns>
    /// The difference between two doubles.
    /// </returns>
    /// <example>
    /// <code>
    /// double c = Math.Subtract(4.5, 5.4);
    /// if (c > 1)
    /// {
    ///     Console.WriteLine(c);
    /// }
    /// </code>
    /// </example>
    /// See <see cref="Math.Subtract(int, int)"/> to subtract integers.
    /// <seealso cref="Math.Add(double, double)"/>
    /// <seealso cref="Math.Multiply(double, double)"/>
    /// <seealso cref="Math.Divide(double, double)"/>
    /// <param name="a">A double precision number.</param>
    /// <param name="b">A double precision number.</param>
    public static double Subtract(double a, double b)
    {
        return a - b;
    }

    // Multiplies two integers and returns the result
    /// <summary>
    /// Multiplies two integers <paramref name="a"/> and <paramref name="b"/> and returns the result.
    /// </summary>
    /// <returns>
    /// The product of two integers.
    /// </returns>
    /// <example>
    /// <code>
    /// int c = Math.Multiply(4, 5);
    /// if (c > 100)
    /// {
    ///     Console.WriteLine(c);
    /// }
    /// </code>
    /// </example>
    /// See <see cref="Math.Multiply(double, double)"/> to multiply doubles.
    /// <seealso cref="Math.Add(int, int)"/>
    /// <seealso cref="Math.Subtract(int, int)"/>
    /// <seealso cref="Math.Divide(int, int)"/>
    /// <param name="a">An integer.</param>
    /// <param name="b">An integer.</param>
    public static int Multiply(int a, int b)
    {
        return a * b;
    }

    // Multiplies two doubles and returns the result
    /// <summary>
    /// Multiplies two doubles <paramref name="a"/> and <paramref name="b"/> and returns the result.
    /// </summary>
    /// <returns>
    /// The product of two doubles.
    /// </returns>
    /// <example>
    /// <code>
    /// double c = Math.Multiply(4.5, 5.4);
    /// if (c > 100.0)
    /// {
    ///     Console.WriteLine(c);
    /// }
    /// </code>
    /// </example>
    /// See <see cref="Math.Multiply(int, int)"/> to multiply integers.
    /// <seealso cref="Math.Add(double, double)"/>
    /// <seealso cref="Math.Subtract(double, double)"/>
    /// <seealso cref="Math.Divide(double, double)"/>
    /// <param name="a">A double precision number.</param>
    /// <param name="b">A double precision number.</param>
    public static double Multiply(double a, double b)
    {
        return a * b;
    }

    // Divides an integer by another and returns the result
    /// <summary>
    /// Divides an integer <paramref name="a"/> by another integer <paramref name="b"/> and returns the result.
    /// </summary>
    /// <returns>
    /// The quotient of two integers.
    /// </returns>
    /// <example>
    /// <code>
    /// int c = Math.Divide(4, 5);
    /// if (c > 1)
    /// {
    ///     Console.WriteLine(c);
    /// }
    /// </code>
    /// </example>
    /// <exception cref="System.DivideByZeroException">Thrown when <paramref name="b"/> is equal to 0.</exception>
    /// See <see cref="Math.Divide(double, double)"/> to divide doubles.
    /// <seealso cref="Math.Add(int, int)"/>
    /// <seealso cref="Math.Subtract(int, int)"/>
    /// <seealso cref="Math.Multiply(int, int)"/>
    /// <param name="a">An integer dividend.</param>
    /// <param name="b">An integer divisor.</param>
    public static int Divide(int a, int b)
    {
        return a / b;
    }

    // Divides a double by another and returns the result
    /// <summary>
    /// Divides a double <paramref name="a"/> by another double <paramref name="b"/> and returns the result.
    /// </summary>
    /// <returns>
    /// The quotient of two doubles.
    /// </returns>
    /// <example>
    /// <code>
    /// double c = Math.Divide(4.5, 5.4);
    /// if (c > 1.0)
    /// {
    ///     Console.WriteLine(c);
    /// }
    /// </code>
    /// </example>
    /// See <see cref="Math.Divide(int, int)"/> to divide integers.
    /// <seealso cref="Math.Add(double, double)"/>
    /// <seealso cref="Math.Subtract(double, double)"/>
    /// <seealso cref="Math.Multiply(double, double)"/>
    /// <param name="a">A double precision dividend.</param>
    /// <param name="b">A double precision divisor.</param>
    public static double Divide(double a, double b)
    {
        return a / b;
    }
}
```

코드에서 클릭 가능한 상호 참조가 함께 제공된 잘 설명된 문서 웹 사이트를 생성할 수 있지만 코드를 읽기 어렵게 되는 다른 문제에 직면할 수 있습니다.
자세히 살펴볼 정보가 너무 많으므로 이 코드에 참여하려는 개발자에게는 큰 문제일 수 있습니다. 다행히도 이 문제를 처리할 수 있는 XML 태그가 있습니다.

### <a name="ltincludegt"></a>&lt;include&gt;

소스 코드 파일에 직접 문서 주석을 배치하는 것과 달리 `<include>` 태그를 사용하면 소스 코드에서 형식과 멤버를 설명하는 주석을 개별 XML 파일에서 참조할 수 있습니다.

이제 모든 XML 태그를 `docs.xml`이라는 개별 XML 파일로 이동합니다. 원하는 대로 파일 이름을 지정합니다.

```xml
<docs>
    <members name="math">
        <Math>
            <summary>
            The main <c>Math</c> class.
            Contains all methods for performing basic math functions.
            </summary>
            <remarks>
            <para>This class can add, subtract, multiply and divide.</para>
            <para>These operations can be performed on both integers and doubles.</para>
            </remarks>
        </Math>
        <AddInt>
            <summary>
            Adds two integers <paramref name="a"/> and <paramref name="b"/> and returns the result.
            </summary>
            <returns>
            The sum of two integers.
            </returns>
            <example>
            <code>
            int c = Math.Add(4, 5);
            if (c > 10)
            {
                Console.WriteLine(c);
            }
            </code>
            </example>
            <exception cref="System.OverflowException">Thrown when one parameter is max 
            and the other is greater than 0.</exception>
            See <see cref="Math.Add(double, double)"/> to add doubles.
            <seealso cref="Math.Subtract(int, int)"/>
            <seealso cref="Math.Multiply(int, int)"/>
            <seealso cref="Math.Divide(int, int)"/>
            <param name="a">An integer.</param>
            <param name="b">An integer.</param>
        </AddInt>
        <AddDouble>
            <summary>
            Adds two doubles <paramref name="a"/> and <paramref name="b"/> and returns the result.
            </summary>
            <returns>
            The sum of two doubles.
            </returns>
            <example>
            <code>
            double c = Math.Add(4.5, 5.4);
            if (c > 10)
            {
                Console.WriteLine(c);
            }
            </code>
            </example>
            <exception cref="System.OverflowException">Thrown when one parameter is max 
            and the other is greater than 0.</exception>
            See <see cref="Math.Add(int, int)"/> to add integers.
            <seealso cref="Math.Subtract(double, double)"/>
            <seealso cref="Math.Multiply(double, double)"/>
            <seealso cref="Math.Divide(double, double)"/>
            <param name="a">A double precision number.</param>
            <param name="b">A double precision number.</param>
        </AddDouble>
        <SubtractInt>
            <summary>
            Subtracts <paramref name="b"/> from <paramref name="a"/> and returns the result.
            </summary>
            <returns>
            The difference between two integers.
            </returns>
            <example>
            <code>
            int c = Math.Subtract(4, 5);
            if (c > 1)
            {
                Console.WriteLine(c);
            }
            </code>
            </example>
            See <see cref="Math.Subtract(double, double)"/> to subtract doubles.
            <seealso cref="Math.Add(int, int)"/>
            <seealso cref="Math.Multiply(int, int)"/>
            <seealso cref="Math.Divide(int, int)"/>
            <param name="a">An integer.</param>
            <param name="b">An integer.</param>
        </SubtractInt>
        <SubtractDouble>
            <summary>
            Subtracts a double <paramref name="b"/> from another double <paramref name="a"/> and returns the result.
            </summary>
            <returns>
            The difference between two doubles.
            </returns>
            <example>
            <code>
            double c = Math.Subtract(4.5, 5.4);
            if (c > 1)
            {
                Console.WriteLine(c);
            }
            </code>
            </example>
            See <see cref="Math.Subtract(int, int)"/> to subtract integers.
            <seealso cref="Math.Add(double, double)"/>
            <seealso cref="Math.Multiply(double, double)"/>
            <seealso cref="Math.Divide(double, double)"/>
            <param name="a">A double precision number.</param>
            <param name="b">A double precision number.</param>
        </SubtractDouble>
        <MultiplyInt>
            <summary>
            Multiplies two integers <paramref name="a"/> and <paramref name="b"/> and returns the result.
            </summary>
            <returns>
            The product of two integers.
            </returns>
            <example>
            <code>
            int c = Math.Multiply(4, 5);
            if (c > 100)
            {
                Console.WriteLine(c);
            }
            </code>
            </example>
            See <see cref="Math.Multiply(double, double)"/> to multiply doubles.
            <seealso cref="Math.Add(int, int)"/>
            <seealso cref="Math.Subtract(int, int)"/>
            <seealso cref="Math.Divide(int, int)"/>
            <param name="a">An integer.</param>
            <param name="b">An integer.</param>
        </MultiplyInt>
        <MultiplyDouble>
            <summary>
            Multiplies two doubles <paramref name="a"/> and <paramref name="b"/> and returns the result.
            </summary>
            <returns>
            The product of two doubles.
            </returns>
            <example>
            <code>
            double c = Math.Multiply(4.5, 5.4);
            if (c > 100.0)
            {
                Console.WriteLine(c);
            }
            </code>
            </example>
            See <see cref="Math.Multiply(int, int)"/> to multiply integers.
            <seealso cref="Math.Add(double, double)"/>
            <seealso cref="Math.Subtract(double, double)"/>
            <seealso cref="Math.Divide(double, double)"/>
            <param name="a">A double precision number.</param>
            <param name="b">A double precision number.</param>
        </MultiplyDouble>
        <DivideInt>
            <summary>
            Divides an integer <paramref name="a"/> by another integer <paramref name="b"/> and returns the result.
            </summary>
            <returns>
            The quotient of two integers.
            </returns>
            <example>
            <code>
            int c = Math.Divide(4, 5);
            if (c > 1)
            {
                Console.WriteLine(c);
            }
            </code>
            </example>
            <exception cref="System.DivideByZeroException">Thrown when <paramref name="b"/> is equal to 0.</exception>
            See <see cref="Math.Divide(double, double)"/> to divide doubles.
            <seealso cref="Math.Add(int, int)"/>
            <seealso cref="Math.Subtract(int, int)"/>
            <seealso cref="Math.Multiply(int, int)"/>
            <param name="a">An integer dividend.</param>
            <param name="b">An integer divisor.</param>
        </DivideInt>
        <DivideDouble>
            <summary>
            Divides a double <paramref name="a"/> by another double <paramref name="b"/> and returns the result.
            </summary>
            <returns>
            The quotient of two doubles.
            </returns>
            <example>
            <code>
            double c = Math.Divide(4.5, 5.4);
            if (c > 1.0)
            {
                Console.WriteLine(c);
            }
            </code>
            </example>
            See <see cref="Math.Divide(int, int)"/> to divide integers.
            <seealso cref="Math.Add(double, double)"/>
            <seealso cref="Math.Subtract(double, double)"/>
            <seealso cref="Math.Multiply(double, double)"/>
            <param name="a">A double precision dividend.</param>
            <param name="b">A double precision divisor.</param>
        </DivideDouble>
    </members>
</docs>
```

위 XML에서 각 멤버의 문서 주석은 멤버가 수행하는 작업과 같은 이름이 지정된 태그 내부에 직접 나타납니다. 자신만의 전략을 선택할 수 있습니다. 이제 XML 주석이 개별 파일에 있으므로 `<include>` 태그를 사용하여 코드를 더 읽기 좋게 만드는 방법을 살펴봅니다.

```csharp
/*
    The main Math class
    Contains all methods for performing basic math functions
*/
/// <include file='docs.xml' path='docs/members[@name="math"]/Math/*'/>
public class Math
{
    // Adds two integers and returns the result
    /// <include file='docs.xml' path='docs/members[@name="math"]/AddInt/*'/>
    public static int Add(int a, int b)
    {
        // If any parameter is equal to the max value of an integer
        // and the other is greater than zero
        if ((a == int.MaxValue && b > 0) || (b == int.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }

    // Adds two doubles and returns the result
    /// <include file='docs.xml' path='docs/members[@name="math"]/AddDouble/*'/>
    public static double Add(double a, double b)
    {
        // If any parameter is equal to the max value of an integer
        // and the other is greater than zero
        if ((a == double.MaxValue && b > 0) || (b == double.MaxValue && a > 0))
            throw new System.OverflowException();

        return a + b;
    }

    // Subtracts an integer from another and returns the result
    /// <include file='docs.xml' path='docs/members[@name="math"]/SubtractInt/*'/>
    public static int Subtract(int a, int b)
    {
        return a - b;
    }

    // Subtracts a double from another and returns the result
    /// <include file='docs.xml' path='docs/members[@name="math"]/SubtractDouble/*'/>
    public static double Subtract(double a, double b)
    {
        return a - b;
    }

    // Multiplies two integers and returns the result
    /// <include file='docs.xml' path='docs/members[@name="math"]/MultiplyInt/*'/>
    public static int Multiply(int a, int b)
    {
        return a * b;
    }

    // Multiplies two doubles and returns the result
    /// <include file='docs.xml' path='docs/members[@name="math"]/MultiplyDouble/*'/>
    public static double Multiply(double a, double b)
    {
        return a * b;
    }

    // Divides an integer by another and returns the result
    /// <include file='docs.xml' path='docs/members[@name="math"]/DivideInt/*'/>
    public static int Divide(int a, int b)
    {
        return a / b;
    }

    // Divides a double by another and returns the result
    /// <include file='docs.xml' path='docs/members[@name="math"]/DivideDouble/*'/>
    public static double Divide(double a, double b)
    {
        return a / b;
    }
}
```

해냈습니다. 코드를 다시 읽을 수 있고 문서 정보가 손실되지 않았습니다. 

`filename` 특성은 문서가 포함된 XML 파일의 이름을 나타냅니다.

`path` 특성은 지정된 `filename`에 있는 `tag name`에 대한 [XPath](https://msdn.microsoft.com/library/ms256115.aspx) 쿼리를 나타냅니다.

`name` 특성은 주석 앞에 오는 태그의 이름 지정자를 나타냅니다.

`name` 대신 사용할 수 있는 `id` 특성은 주석 앞에 오는 태그의 ID를 나타냅니다.

### <a name="user-defined-tags"></a>사용자 정의 태그

위에서 설명한 모든 태그는 C# 컴파일러에서 인식되는 태그를 나타냅니다. 그러나 사용자가 자유롭게 태그를 정의할 수 있습니다.
Sandcastle 등의 도구는 [`<event>`](http://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm), [`<note>`](http://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) 같은 추가 태그를 지원하고 [네임스페이스 문서화](http://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm)도 지원합니다.
사용자 지정 또는 사내 문서 생성 도구는 표준 태그와 함께 사용할 수도 있고 HTML에서 PDF까지 다양한 출력 형식을 지원할 수 있습니다.

## <a name="recommendations"></a>권장 사항

여러 가지 이유로 코드를 문서화하는 것이 좋습니다. 이어서 일부 모범 사례, 일반적인 사용 사례 시나리오 및 C# 코드에서 XML 문서 태그를 사용할 때 알아야 하는 내용을 살펴봅니다.

* 일관성을 보장하기 위해 모든 공개 형식과 해당 멤버를 문서화해야 합니다. 문서화해야 한다면 모두 문서화하세요.
* Private 멤버는 XML 주석을 사용하여 문서화할 수도 있습니다. 그러나 이렇게 하면 라이브러리의 내부(잠재적으로 기밀) 작업이 표시됩니다.
* IntelliSense에는 `<summary>` 태그의 내용이 필요하므로 최소한 형식과 해당 멤버에 이 태그가 있어야 합니다.
* 문서 텍스트는 마침표로 끝나는 전체 문장을 사용하여 기록되어야 합니다.
* Partial 클래스는 완전히 지원되고 문서 정보는 해당 형식의 단일 항목에 연결됩니다.
* 컴파일러에서 `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` 및 `<typeparam>` 태그의 구문을 확인합니다.
- 컴파일러는 파일 경로와 코드의 다른 부분에 대한 참조가 포함된 매개 변수의 유효성을 검사합니다.

## <a name="see-also"></a>참고 항목
[XML 문서 주석(C# 프로그래밍 가이드)](programming-guide/xmldoc/xml-documentation-comments.md)

[문서 주석에 대한 권장 태그(C# 프로그래밍 가이드)](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

