---
title: "빠른 시작-C#에서 번호-C# 가이드"
description: "숫자 형식, 속성 및 메서드를 조사 하 여 C# 학습 합니다."
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 821cca4ea6d6148410e9b179f05d5b74c4844628
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2017
---
# <a name="numbers-in-c-quick-start"></a>C# 빠른 시작의 숫자 #

이 빠른 시작에 설명 C#의 숫자 형식에 대 한 대화형으로 합니다. 적은 양의 코드를 작성 한 후 컴파일 및 코드를 실행 합니다. 빠른 시작에는 일련의 수치 연산 및 숫자를 탐색 하는 단원 포함 되어 있습니다. 이러한 단원에서는 C# 언어의 기본 사항을 설명합니다.

이 빠른 시작에서는 개발에 사용할 수 있습니다를 가질 수 있습니다. .NET 항목 [10 분 후에 시작](https://www.microsoft.com/net/core) Mac, PC 또는 Linux 로컬 개발 환경 설정에 대 한 지침이 있습니다.

## <a name="explore-integer-math"></a>정수 계산 살펴보기

라는 디렉터리를 만들고 **숫자 퀵 스타트**합니다. 현재 디렉터리로 지정하고 `dotnet new console -n NumbersInCSharp -o .`을 실행합니다.

열기 **Program.cs** 즐겨 찾는 편집기 및 바꾸기 줄에서 `Console.Writeline("Hello World!");` 다음:

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

이 코드를 입력 하 여 실행 `dotnet run` 명령 창에서. 

정수를 사용하는 기본 수학 연산 중 하나를 방금 살펴봤습니다. `int` 형식은 **정수**(양의 정수 또는 음의 정수)를 나타냅니다. 더하기의 경우 `+` 기호를 사용합니다. 정수에 대해 다른 일반적인 수학 연산은 다음과 같습니다.

- 빼기의 경우 `-`
- 곱하기의 경우 `*`
- 나누기의 경우 `/`

다른 연산을 살펴보세요. 값을 작성 하는 줄 뒤에 다음이 줄을 추가 `c`:

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

이 코드를 입력 하 여 실행 `dotnet run` 명령 창에서. 
    
원하는 경우 동일한 줄에서 여러 수학 연산을 수행하여 실험할 수도 있습니다. 시도 `c = a + b - 12 * 17;` 예입니다. 변수 및 상수 번호 혼합 허용 됩니다.

> [!TIP]
> C# (또는 다른 프로그래밍 언어)를 살펴보면서 코드를 작성할 때 실수를 하게 될 것입니다. **컴파일러**는 그러한 오류를 찾아 사용자에게 보고합니다. 오류 메시지를 포함 하는 출력을 창에서 문제를 해결 하는 기능을 코드 및 예제 코드에 치중 합니다.
> 이 연습은 C# 코드의 구조를 학습하는 데 도움이 됩니다.     

첫 번째 단계 작업을 완료 했습니다. 다음 섹션을 시작하기 전에 현재 코드를 별도의 메서드로 이동합니다. 이렇게 하면 새 예제 작업을 쉽게 시작할 수 있습니다. `Main` 메서드의 이름을 `WorkingWithIntegers`로 바꾸고 `WorkingWithIntegers`를 호출하는 새 `Main` 메서드를 작성합니다. 작업을 마치면 코드가 다음과 같이 됩니다.

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
            c = a / b;
            Console.WriteLine(c);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();
        }
    }
}
```

## <a name="explore-order-of-operations"></a>연산 순서 알아보기

에 대 한 호출을 주석 `WorkingWithIntegers()`합니다. 이 섹션에서 작업할 때 덜 복잡 한 출력을 구성 됩니다.

```csharp
//WorkingWithIntegers();
```

`//` 시작 되는 **주석** C#입니다. 주석은 모든 텍스트를 소스 코드에 유지 되지만 코드로 실행 되지 않습니다. 컴파일러는 주석에서 실행 코드를 생성 하지 않습니다.

C# 언어는 수학에서 배운 규칙과 일치하는 규칙으로 여러 가지 수학 연산의 우선 순위를 정의합니다.
곱하기와 나누기는 더하기와 빼기보다 우선 순위가 높습니다.
다음 코드를 추가 하 여 탐색 하 여 `Main` 메서드와 execuing `dotnet run`:

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

출력에서는 곱하기가 수행된 후 더하기가 수행되었음을 보여 줍니다.

작업 주위에 괄호를 추가 하 여 작업의 순서를 강제로 수 또는 원하는 작업을 먼저 수행 합니다. 다음 줄을 추가 하 고 다시 실행 합니다.

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

여러 다른 연산을 결합하여 자세히 살펴보세요. 맨 아래에 다음 줄와 같은 추가 사용자 `Main` 메서드. 시도 `dotnet run` 다시 합니다.

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

정수에 대해 흥미로운 동작을 이미 알고 있을 수 있습니다. 정수 나누기를 항상 10 진수 또는 소수 부분을 포함 하도록 결과 기대 하는 경우에 정수 결과 생성 합니다.

이 문제를 보지 못했다면의 끝에 다음 코드를 사용해 보십시오. 프로그램 `Main` 메서드:

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

형식 `dotnet run` 다시 결과 볼 수 있습니다.

이동 하기 전에이 섹션에 작성 되었으며 새로운 방법에 넣을 코드 모든 보겠습니다. 이 새 메서드를 호출 `OrderPrecedence`합니다.
결과를 다음과 같이 사용 합니다.

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
            c = a / b;
            Console.WriteLine(c);
        }

        static void OrderPrecedence()
        {   
            int a = 5;
            int b = 4;
            int c = 2;
            int d = a + b * c;
            Console.WriteLine(d);

            d = (a  + b) * c;
            Console.WriteLine(d);

            d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
            Console.WriteLine(d);

            int e = 7;
            int f = 4;
            int g = 3;
            int h = (e  + f) / g;
            Console.WriteLine(h);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();

            OrderPrecedence();

        }
    }
}
```

## <a name="explore-integer-precision-and-limits"></a>정수 전체 자릿수 및 한도 살펴보기
마지막 샘플에서는 정수 나누기가 결과를 자르는 것을 보여 줍니다.
가져올 수 있습니다는 **나머지** 를 사용 하 여는 **모듈로** 연산자는 `%` 문자입니다. 다음 코드를 시도 하면 `Main` 메서드:

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

C# 정수 형식은 한 가지 다른 면에서 수학의 정수와 다릅니다. 즉 `int` 형식에는 최소 한도와 최대 한도가 있습니다. 이 코드를 추가 하 여 `Main` 메서드를 이러한 제한을 참조:
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

계산이 해당 한도를 초과하는 값을 생성하는 경우 **언더플로** 또는 **오버플로** 조건이 발생합니다. 답은 한 한도에서 다른 한도로 래핑하는 것으로 나타납니다. 다음 두 줄을 추가 하면 `Main` 메서드 예제를 보려면:

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
답은 최소 (음의) 정수와 아주 가깝습니다. `min + 2`와 같습니다. 더하기 연산은 정수에 대해 허용된 값을 **오버플로했습니다**.
오버플로가 가능한 가장 큰 정수에서 가장 작은 정수로 “래핑”하기 때문에 답은 아주 큰 음수입니다.

`int` 형식이 요구 사항을 충족하지 않을 때 사용하는 여러 한도와 전체 자릿수가 있는 다른 숫자 형식이 있습니다. 이에 대해 다음에 살펴보겠습니다.

다시 한 번를 별도 메서드로이 섹션에서 작성 한 코드를 넘어가겠습니다. 이 EventHandler의 이름을 `TestLimits`로 지정합니다. 

## <a name="work-with-the-double-type"></a>double 형식 작업

`double` 숫자 형식은 배정밀도 부동 소수점 수를 나타냅니다. 이러한 용어는 생소할 수 있습니다. A **부동 소수점** 수는 매우 크거나 작은 크기에 정수가 아닌 숫자를 나타내는 데 유용 합니다. **배정밀도**란 이러한 숫자가 **단정밀도**보다 큰 전체 자릿수를 사용하여 저장됨을 의미합니다. 최신 컴퓨터에서는 단정밀도 숫자보다 배정밀도를 더 많이 사용합니다.
지금 살펴보세요. 다음 코드를 추가 하 고 결과 참조 하십시오.

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

답에 몫의 소수 부분이 포함되어 있습니다. double을 사용하여 약간 더 복잡한 식을 사용해 보세요.

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

double 값의 범위는 정수 값보다 훨씬 큽니다. 지금까지 작성 한 내용 아래에 다음 코드를 시도해 보십시오.

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

이러한 값은 과학적 표기법에 인쇄 됩니다. 왼쪽의 숫자는 `E` 는 significand 됩니다. 오른쪽의 숫자는 지수이며 10의 배수입니다. 

수학의 10진수 숫자와 마찬가지로, C#에서 double에는 반올림 오류가 발생할 수 있습니다. 다음 코드를 사용해 보세요.

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

`0.3` 반복은 `1/3`과 정확하게 동일하지는 않습니다.

***과제***

`double` 형식을 사용하여 큰 숫자, 작은 숫자, 곱하기 및 나누기로 다른 계산을 수행해 보세요.  더 복잡한 계산을 수행해 보세요.

하는 데 약간의 시간이 챌린지와, 사용할 코드를 작성 한 새로운 방법에 배치 합니다. 새 메서드 이름을 `WorkWithDoubles`합니다.

## <a name="work-with-fixed-point-types"></a>고정 소수점 형식 작업

C#의 기본적인 숫자 형식인 정수 형식과 double 형식을 살펴봤습니다.  학습할 또 다른 형식이 있습니다. 바로 `decimal` 형식입니다. `decimal` 형식 보다 더 정확 하지만 작은 범위에 `double`합니다. **고정 소수점**이라는 용어는 소수점(또는 이진 소수점)이 이동하지 않음을 의미합니다. 이 형식에 대해 살펴보겠습니다.

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

범위가 `double` 형식보다 작습니다. 다음 코드를 사용하여 소수점이 있는 더 큰 전체 자릿수를 확인할 수 있습니다.

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

숫자의 `M` 접미사는 상수가 `decimal` 형식을 사용해야 함을 나타내는 방법입니다.

소수점 형식을 사용하는 수학에는 소수점 오른쪽에 더 많은 숫자가 있습니다. 

***과제***

이제 여러 가지 숫자 형식을 살펴봤으므로 반지름이 2.50인치인 원의 면적을 계산하는 코드를 작성하세요. 원의 면적은 반지름 제곱 곱하기 PI입니다. 하나의 힌트: C# PI에 대 한 상수를 포함 합니다. <xref:System.Math.PI?displayProperty=nameWithType> 해당 값에 사용할 수 있습니다. 

답변을 확인할 수 있습니다 [GitHub에서 완성 된 샘플 코드를 살펴보면](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)

원하는 경우 다른 수식을 시도 하십시오. 

"숫자 C#에서" 퀵 스타트를 완료 합니다. 계속 진행할 수 있습니다는 [분기, 루프](branches-and-loops-local.md) 사용자 고유의 개발 환경에서 빠른 시작 합니다.

다음 항목에서는 C#의 숫자에 대해 더 자세히 알아볼 수 있습니다.

[정수 형식 표](../language-reference/keywords/integral-types-table.md)   
[부동 소수점 형식 표](../language-reference/keywords/floating-point-types-table.md)   
[기본 제공 형식 표](../language-reference/keywords/built-in-types-table.md)   
[암시적 숫자 변환 표](../language-reference/keywords/implicit-numeric-conversions-table.md)   
[명시적 숫자 변환 표](../language-reference/keywords/explicit-numeric-conversions-table.md)

