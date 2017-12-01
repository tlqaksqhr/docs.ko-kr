---
title: "빠른 시작-분기 및 lops-C# 가이드"
description: "분기, 루프에 대 한이 빠른 시작 조건부 분기 및 문을 반복적으로 실행 하는 루프를 지 원하는 언어 구문을 탐색 하는 C# 코드를 작성 합니다."
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 4b077a29cf42072a93b054f50a13a4580ad54304
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2017
---
# <a name="branches-and-loops"></a>분기 및 루프

이 빠른 시작에서는 변수를 검사 하 고 해당 변수를 기반으로 실행 경로 변경 하는 코드를 작성 하는 방법을 배웁니다. C# 코드를 작성 하 고이 정보를 컴파일 및 실행 하는 결과 확인 합니다. 빠른 시작에는 일련의 분기 구문과 루프 구문 C#에서 탐색 하는 단원 포함 되어 있습니다. 이러한 단원에서는 C# 언어의 기본 사항을 설명합니다.

이 빠른 시작에서는 개발에 사용할 수 있습니다를 가질 수 있습니다. .NET 항목 [10 분 후에 시작](https://www.microsoft.com/net/core) Mac, PC 또는 Linux 로컬 개발 환경 설정에 대 한 지침이 있습니다.

## <a name="make-decisions-using-the-if-statement"></a>사용 하 여 결정을 내릴는 `if` 문

라는 디렉터리를 만들고 **분기가 quickstart**합니다. 현재 디렉터리로 지정하고 `dotnet new console -n BranchesAndLoops -o .`을 실행합니다. 이 명령은 현재 디렉터리에 새.NET Core 콘솔 응용 프로그램을 만듭니다. 

열기 **Program.cs** 즐겨 찾는 편집기 및 바꾸기 줄에서 `Console.Writeline("Hello World!");` 를 다음 코드로:

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

이 코드를 입력 하 여 시도 `dotnet run` 에 콘솔 창입니다. "대 한 대답은 10 보다 큰." 메시지가 나타납니다. 콘솔로 인쇄 합니다.

합계가 10보다 작도록 `b`의 선언을 수정합니다. 

```csharp
int b = 3;
```

형식 `dotnet run` 다시 합니다. 답이 10보다 작기 때문에 아무것도 출력되지 않습니다. 테스트하는 **조건**은 false입니다. `if` 문에 대해 가능한 분기 중 하나(true 분기)만 작성했기 때문에 실행할 코드가 없습니다.

> [!TIP]
> C# (또는 다른 프로그래밍 언어)를 살펴보면서 코드를 작성할 때 실수를 하게 될 것입니다. 컴파일러를 찾아서는 오류를 보고 합니다. 치중의 오류 출력 및 오류를 생성 하는 코드입니다. Compler 오류 문제를 찾을 수 일반적으로 합니다. 

이 첫 번째 샘플의 나와 `if` 및 Boolean 형식입니다. A *부울* 는 두 값 중 하나를 가질 수 있는 변수: `true` 또는 `false`합니다. C# 특별 한 형식 정의 `bool` 부울 변수입니다. `if` 문은 `bool`의 값을 확인합니다. 값이 `true`인 경우 `if` 뒤의 문이 실행됩니다. 그러하지 않으면 건너뜁니다. 

조건을 확인하고 해당 조건에 따라 문을 실행하는 이 프로세스는 아주 강력합니다.


## <a name="make-if-and-else-work-together"></a>if와 else를 함께 사용하기

true 분기와 false 분기의 여러 코드를 실행하려면 조건이 false일 때 실행되는 `else` 분기를 생성합니다. 이 작업을 시도 합니다. 아래에 코드에서 두 줄을 추가 하면 `Main` 메서드 (이미 있어야 처음 4 개):

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

`else` 키워드 뒤의 문은 테스트하는 조건이 `false`인 경우에만 실행됩니다. 결합 `if` 및 `else` 와 부울 조건 둘 다 처리 해야 하는 모든 기능을 제공 된 `true` 및 `false` 조건입니다.

> [!IMPORTANT]
> `if` 및 `else` 문 아래의 들여쓰기는 사용자가 보기 편하도록 하기 위함입니다.
> C# 언어는 들여쓰기 또는 공백을 중요하게 취급하지 않습니다. `if` 또는 `else` 키워드 뒤의 문은 조건에 따라 실행됩니다. 이 빠른 시작에 있는 모든 샘플의 문 제어 흐름에 따라 줄 들여쓰기로 따릅니다.

들여쓰기는 중요하지 않기 때문에 `{` 및 `}`를 사용하여 두 개 이상의 문이 조건부로 실행되는 블록의 일부가 되는 시기를 나타내야 합니다. C# 프로그래머는 일반적으로 모든 `if` 및 `else` 절에서 중괄호를 사용합니다. 다음 예제에서는 방금 만든 것과 같습니다. 다음 코드와 일치 하도록 위의 코드를 수정 합니다.

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
{
    Console.WriteLine("The answer is greater than 10");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
}
```

> [!TIP]
> 이 빠른 시작의 나머지 부분을 모든 코드 예제는 뒤에 중괄호를 포함 사례를 허용 합니다.

더 복잡 한 조건을 테스트할 수 있습니다. 에 다음 코드를 추가 하면 `Main` 메서드 후 지금까지 작성 한 코드:

```csharp
    int c = 4;
    if ((a + b + c > 10) && (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not greater than the second");
}
```

`&&`는 “and”를 나타냅니다. true 분기에서 문을 실행하려면 두 조건이 모두 true여야 합니다.  이러한 예제에서는 `{` 및 `}`로 문을 묶으면 각 조건부 분기에 여러 문을 가질 수 있음도 보여 줍니다.

사용할 수도 있습니다 `||` 나타내기 위해 "또는". 지금까지 작성 한 내용 뒤 다음 코드를 추가 합니다.

```csharp
if ((a + b + c > 10) || (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not greater than the second");
}
```

첫 번째 단계 작업을 완료 했습니다. 다음 섹션을 시작하기 전에 현재 코드를 별도의 메서드로 이동합니다. 이렇게 하면 새 예제 작업을 쉽게 시작할 수 있습니다. `Main` 메서드의 이름을 `ExploreIf`로 바꾸고 `ExploreIf`를 호출하는 새 `Main` 메서드를 작성합니다. 작업을 마치면 코드가 다음과 같이 됩니다.

```csharp
using System;

namespace BranchesAndLoops
{
    class Program
    {
        static void ExploreIf()
        {
            int a = 5;
            int b = 3;
            if (a + b > 10)
            {
                Console.WriteLine("The answer is greater than 10");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
            }

            if ((a + b + c > 10) && (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("And the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("Or the first number is not greater than the second");
            }

            if ((a + b + c > 10) || (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("Or the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("And the first number is not greater than the second");
            }            
        }

        static void Main(string[] args)
        {
            ExploreIf();
        }
    }
}
```

에 대 한 호출을 주석 `ExploreIf()`합니다. 이 섹션에서 작업할 때 덜 복잡 한 출력을 구성 됩니다.

```csharp
//ExploreIf();
```

`//` 시작 되는 **주석** C#입니다. 주석은 모든 텍스트를 소스 코드에 유지 되지만 코드로 실행 되지 않습니다. 컴파일러는 주석에서 실행 코드를 생성 하지 않습니다.

## <a name="use-loops-to-repeat-operations"></a>루프를 사용하여 작업 반복

이 섹션에서 사용 **루프** 문을 반복 합니다. 이 코드를 시도 하면 `Main` 메서드:

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

`while` 문은 조건을 검사 하 고 문 또는 문 블록을 다음 실행에서 `while`합니다. 반복 해 서 조건과 조건이 false가 될 때까지 해당 문 실행을 확인 합니다.

이 예제에서는 다른 새 연산자가 하나 있습니다. `counter` 변수 뒤의 `++`는 **증가** 연산자입니다. 값에 1이 더해집니다 `counter` 에 해당 값을 저장 하 고는 `counter` 변수입니다.

> [!IMPORTANT]
> 다음 사항을 확인는 `while` 코드를 실행 하면서 루프를 false로 조건을 변경 합니다. 그러하지 않으면 프로그램이 종료되지 않는 **무한 루프**를 생성합니다. 설명 하지 않음이 샘플 사용을 중지 하려면 프로그램을 강제로 해야 하기 때문에 **Ctrl-c** 또는 다른 수단입니다.

`while` 루프는 `while` 뒤에 코드를 실행하기 전에 조건을 테스트합니다. `do` ... `while` 루프는 코드를 먼저 실행한 후 조건을 확인합니다. 루프는 다음 코드에 표시 되는 방법:

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

이 `do` 루프 및 이전 `while` 루프 같은 출력을 생성 합니다.

## <a name="work-with-the-for-loop"></a>for 루프 작업

**에 대 한** 루프를 일반적으로 C#에서 사용 됩니다. 이 코드를 main () 메서드에서 사용해 보십시오.

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

`while` 루프 및 이미 사용한 `do` 루프와 동일한 작업을 수행합니다. `for` 문에는 작동 방식을 제어하는 세 부분이 있습니다. 

첫 번째 부분은 **for 이니셜라이저입니다**. `for index = 0;`은 `index`가 루프 변수임을 선언하고 첫 번째 값을 `0`으로 설정합니다.

중간 부분은 **for 조건입니다**. `index < 10`은 이 `for` 루프가 카운터 값이 10보다 작으면 계속 실행됨을 선언합니다.

마지막 부분은 **for 반복기입니다**. `index++`는 `for` 문 다음의 블록을 실행한 후 루프 변수를 수정하는 방법을 지정합니다. 여기서 `index`는 블록이 실행될 때마다 1씩 증가하도록 지정합니다.

직접 실습해 보세요. 다음 각각을 시도해 보세요.

- 다른 값으로 시작하도록 이니셜라이저를 변경합니다.
- 다른 값에서 중지하도록 조건을 변경합니다.

완료하면, 학습한 내용을 토대로 직접 코드를 작성해 보겠습니다.

## <a name="combine-branches-and-loops"></a>분기와 루프를 결합 합니다.

이제 C# 언어로 된 `if` 문과 루프 구조를 확인했습니다. C# 코드를 작성하여 3으로 나눌 수 있는, 1에서 20까지의 모든 정수의 합계를 찾을 수 있는지 확인해 보세요.  다음은 몇 가지 힌트입니다.

- `%` 연산자는 나누기 연산의 나머지를 제공합니다.
- `if` 문을 숫자 합계의 일부 여야 하는 경우 참조 하는 조건을 제공 합니다.
- `for` 루프는 1에서 20까지의 모든 숫자에 대해 일련의 단계를 반복하는 데 도움이 됩니다.

직접 시도해 보세요. 그런 다음 어떻게 했는지 확인하세요. 한 가지 가능한 대답을 확인할 수 있습니다 [GitHub에서 완성 된 코드를 보는](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54)합니다.

빠른 시작 "분기 및 루프"를 완료 합니다.

계속 진행할 수 있습니다는 [배열 및 컬렉션](arrays-and-collections.md) 사용자 고유의 개발 환경에서 빠른 시작 합니다.

다음 항목에서는 해당 개념에 대해 더 자세히 알아볼 수 있습니다.

[If 및 else 문](../language-reference/keywords/if-else.md)   
[While 문](../language-reference/keywords/while.md)   
[Do 문](../language-reference/keywords/do.md)   
[For 문](../language-reference/keywords/for.md)   
