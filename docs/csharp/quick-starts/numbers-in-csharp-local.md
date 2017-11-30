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
# <a name="numbers-in-c-quick-start"></a><span data-ttu-id="92875-103">C# 빠른 시작의 숫자</span><span class="sxs-lookup"><span data-stu-id="92875-103">Numbers in C# quick start</span></span> #

<span data-ttu-id="92875-104">이 빠른 시작에 설명 C#의 숫자 형식에 대 한 대화형으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-104">This quick start teaches you about the number types in C# interactively.</span></span> <span data-ttu-id="92875-105">적은 양의 코드를 작성 한 후 컴파일 및 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="92875-106">빠른 시작에는 일련의 수치 연산 및 숫자를 탐색 하는 단원 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-106">The quick start contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="92875-107">이러한 단원에서는 C# 언어의 기본 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="92875-108">이 빠른 시작에서는 개발에 사용할 수 있습니다를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="92875-109">.NET 항목 [10 분 후에 시작](https://www.microsoft.com/net/core) Mac, PC 또는 Linux 로컬 개발 환경 설정에 대 한 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="92875-110">정수 계산 살펴보기</span><span class="sxs-lookup"><span data-stu-id="92875-110">Explore integer math</span></span>

<span data-ttu-id="92875-111">라는 디렉터리를 만들고 **숫자 퀵 스타트**합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-111">Create a directory named **numbers-quickstart**.</span></span> <span data-ttu-id="92875-112">현재 디렉터리로 지정하고 `dotnet new console -n NumbersInCSharp -o .`을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-112">Make that the current directory and run `dotnet new console -n NumbersInCSharp -o .`.</span></span>

<span data-ttu-id="92875-113">열기 **Program.cs** 즐겨 찾는 편집기 및 바꾸기 줄에서 `Console.Writeline("Hello World!");` 다음:</span><span class="sxs-lookup"><span data-stu-id="92875-113">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="92875-114">이 코드를 입력 하 여 실행 `dotnet run` 명령 창에서.</span><span class="sxs-lookup"><span data-stu-id="92875-114">Run this code by typing `dotnet run` in your command window.</span></span> 

<span data-ttu-id="92875-115">정수를 사용하는 기본 수학 연산 중 하나를 방금 살펴봤습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-115">You've just seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="92875-116">`int` 형식은 **정수**(양의 정수 또는 음의 정수)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="92875-116">The `int` type represents an **integer**, a positive or negative whole number.</span></span> <span data-ttu-id="92875-117">더하기의 경우 `+` 기호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-117">You use the `+` symbol for addition.</span></span> <span data-ttu-id="92875-118">정수에 대해 다른 일반적인 수학 연산은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-118">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="92875-119">빼기의 경우 `-`</span><span class="sxs-lookup"><span data-stu-id="92875-119">`-` for subtraction</span></span>
- <span data-ttu-id="92875-120">곱하기의 경우 `*`</span><span class="sxs-lookup"><span data-stu-id="92875-120">`*` for multiplication</span></span>
- <span data-ttu-id="92875-121">나누기의 경우 `/`</span><span class="sxs-lookup"><span data-stu-id="92875-121">`/` for division</span></span>

<span data-ttu-id="92875-122">다른 연산을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="92875-122">Start by exploring those different operations.</span></span> <span data-ttu-id="92875-123">값을 작성 하는 줄 뒤에 다음이 줄을 추가 `c`:</span><span class="sxs-lookup"><span data-stu-id="92875-123">Add these lines after the line that writes the value of `c`:</span></span>

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="92875-124">이 코드를 입력 하 여 실행 `dotnet run` 명령 창에서.</span><span class="sxs-lookup"><span data-stu-id="92875-124">Run this code by typing `dotnet run` in your command window.</span></span> 
    
<span data-ttu-id="92875-125">원하는 경우 동일한 줄에서 여러 수학 연산을 수행하여 실험할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-125">You can also experiment by performing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="92875-126">시도 `c = a + b - 12 * 17;` 예입니다.</span><span class="sxs-lookup"><span data-stu-id="92875-126">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="92875-127">변수 및 상수 번호 혼합 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92875-127">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="92875-128">C# (또는 다른 프로그래밍 언어)를 살펴보면서 코드를 작성할 때 실수를 하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="92875-128">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="92875-129">**컴파일러**는 그러한 오류를 찾아 사용자에게 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-129">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="92875-130">오류 메시지를 포함 하는 출력을 창에서 문제를 해결 하는 기능을 코드 및 예제 코드에 치중 합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-130">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="92875-131">이 연습은 C# 코드의 구조를 학습하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92875-131">That exercise will help you learn the structure of C# code.</span></span>     

<span data-ttu-id="92875-132">첫 번째 단계 작업을 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-132">You've finished the first step.</span></span> <span data-ttu-id="92875-133">다음 섹션을 시작하기 전에 현재 코드를 별도의 메서드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-133">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="92875-134">이렇게 하면 새 예제 작업을 쉽게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-134">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="92875-135">`Main` 메서드의 이름을 `WorkingWithIntegers`로 바꾸고 `WorkingWithIntegers`를 호출하는 새 `Main` 메서드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-135">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="92875-136">작업을 마치면 코드가 다음과 같이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92875-136">When you have finished, your code should look like this:</span></span>

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

## <a name="explore-order-of-operations"></a><span data-ttu-id="92875-137">연산 순서 알아보기</span><span class="sxs-lookup"><span data-stu-id="92875-137">Explore order of operations</span></span>

<span data-ttu-id="92875-138">에 대 한 호출을 주석 `WorkingWithIntegers()`합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-138">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="92875-139">이 섹션에서 작업할 때 덜 복잡 한 출력을 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92875-139">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="92875-140">`//` 시작 되는 **주석** C#입니다.</span><span class="sxs-lookup"><span data-stu-id="92875-140">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="92875-141">주석은 모든 텍스트를 소스 코드에 유지 되지만 코드로 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-141">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="92875-142">컴파일러는 주석에서 실행 코드를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-142">The compiler does not generate any executable code from comments.</span></span>

<span data-ttu-id="92875-143">C# 언어는 수학에서 배운 규칙과 일치하는 규칙으로 여러 가지 수학 연산의 우선 순위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-143">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="92875-144">곱하기와 나누기는 더하기와 빼기보다 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-144">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="92875-145">다음 코드를 추가 하 여 탐색 하 여 `Main` 메서드와 execuing `dotnet run`:</span><span class="sxs-lookup"><span data-stu-id="92875-145">Explore that by adding the following code to your `Main` method, and execuing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="92875-146">출력에서는 곱하기가 수행된 후 더하기가 수행되었음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92875-146">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="92875-147">작업 주위에 괄호를 추가 하 여 작업의 순서를 강제로 수 또는 원하는 작업을 먼저 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-147">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="92875-148">다음 줄을 추가 하 고 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-148">Add the following lines and run again:</span></span>

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="92875-149">여러 다른 연산을 결합하여 자세히 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="92875-149">Explore more by combining many different operations.</span></span> <span data-ttu-id="92875-150">맨 아래에 다음 줄와 같은 추가 사용자 `Main` 메서드.</span><span class="sxs-lookup"><span data-stu-id="92875-150">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="92875-151">시도 `dotnet run` 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-151">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="92875-152">정수에 대해 흥미로운 동작을 이미 알고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-152">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="92875-153">정수 나누기를 항상 10 진수 또는 소수 부분을 포함 하도록 결과 기대 하는 경우에 정수 결과 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-153">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="92875-154">이 문제를 보지 못했다면의 끝에 다음 코드를 사용해 보십시오. 프로그램 `Main` 메서드:</span><span class="sxs-lookup"><span data-stu-id="92875-154">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="92875-155">형식 `dotnet run` 다시 결과 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-155">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="92875-156">이동 하기 전에이 섹션에 작성 되었으며 새로운 방법에 넣을 코드 모든 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-156">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="92875-157">이 새 메서드를 호출 `OrderPrecedence`합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-157">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="92875-158">결과를 다음과 같이 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-158">You should end up with something like this:</span></span>

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

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="92875-159">정수 전체 자릿수 및 한도 살펴보기</span><span class="sxs-lookup"><span data-stu-id="92875-159">Explore integer precision and limits</span></span>
<span data-ttu-id="92875-160">마지막 샘플에서는 정수 나누기가 결과를 자르는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92875-160">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="92875-161">가져올 수 있습니다는 **나머지** 를 사용 하 여는 **모듈로** 연산자는 `%` 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="92875-161">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="92875-162">다음 코드를 시도 하면 `Main` 메서드:</span><span class="sxs-lookup"><span data-stu-id="92875-162">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="92875-163">C# 정수 형식은 한 가지 다른 면에서 수학의 정수와 다릅니다. 즉 `int` 형식에는 최소 한도와 최대 한도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-163">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="92875-164">이 코드를 추가 하 여 `Main` 메서드를 이러한 제한을 참조:</span><span class="sxs-lookup"><span data-stu-id="92875-164">Add this code to your `Main` method to see those limits:</span></span>
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="92875-165">계산이 해당 한도를 초과하는 값을 생성하는 경우 **언더플로** 또는 **오버플로** 조건이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-165">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="92875-166">답은 한 한도에서 다른 한도로 래핑하는 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="92875-166">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="92875-167">다음 두 줄을 추가 하면 `Main` 메서드 예제를 보려면:</span><span class="sxs-lookup"><span data-stu-id="92875-167">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
<span data-ttu-id="92875-168">답은 최소 (음의) 정수와 아주 가깝습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-168">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="92875-169">`min + 2`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-169">It's the same as `min + 2`.</span></span> <span data-ttu-id="92875-170">더하기 연산은 정수에 대해 허용된 값을 **오버플로했습니다**.</span><span class="sxs-lookup"><span data-stu-id="92875-170">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="92875-171">오버플로가 가능한 가장 큰 정수에서 가장 작은 정수로 “래핑”하기 때문에 답은 아주 큰 음수입니다.</span><span class="sxs-lookup"><span data-stu-id="92875-171">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="92875-172">`int` 형식이 요구 사항을 충족하지 않을 때 사용하는 여러 한도와 전체 자릿수가 있는 다른 숫자 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-172">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="92875-173">이에 대해 다음에 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-173">Let's explore those next.</span></span>

<span data-ttu-id="92875-174">다시 한 번를 별도 메서드로이 섹션에서 작성 한 코드를 넘어가겠습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-174">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="92875-175">이 EventHandler의 이름을 `TestLimits`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-175">Name it `TestLimits`.</span></span> 

## <a name="work-with-the-double-type"></a><span data-ttu-id="92875-176">double 형식 작업</span><span class="sxs-lookup"><span data-stu-id="92875-176">Work with the double type</span></span>

<span data-ttu-id="92875-177">`double` 숫자 형식은 배정밀도 부동 소수점 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="92875-177">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="92875-178">이러한 용어는 생소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-178">Those terms may be new to you.</span></span> <span data-ttu-id="92875-179">A **부동 소수점** 수는 매우 크거나 작은 크기에 정수가 아닌 숫자를 나타내는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-179">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="92875-180">**배정밀도**란 이러한 숫자가 **단정밀도**보다 큰 전체 자릿수를 사용하여 저장됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-180">**Double-precision** means that these numbers are stored using greater precision than **single-precision**.</span></span> <span data-ttu-id="92875-181">최신 컴퓨터에서는 단정밀도 숫자보다 배정밀도를 더 많이 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-181">On modern computers, it is more common to use double precision than single precision numbers.</span></span>
<span data-ttu-id="92875-182">지금 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="92875-182">Let's explore.</span></span> <span data-ttu-id="92875-183">다음 코드를 추가 하 고 결과 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="92875-183">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="92875-184">답에 몫의 소수 부분이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-184">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="92875-185">double을 사용하여 약간 더 복잡한 식을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="92875-185">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="92875-186">double 값의 범위는 정수 값보다 훨씬 큽니다.</span><span class="sxs-lookup"><span data-stu-id="92875-186">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="92875-187">지금까지 작성 한 내용 아래에 다음 코드를 시도해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="92875-187">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="92875-188">이러한 값은 과학적 표기법에 인쇄 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92875-188">These values are printed out in scientific notation.</span></span> <span data-ttu-id="92875-189">왼쪽의 숫자는 `E` 는 significand 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92875-189">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="92875-190">오른쪽의 숫자는 지수이며 10의 배수입니다.</span><span class="sxs-lookup"><span data-stu-id="92875-190">The number to the right is the exponent, as a power of 10.</span></span> 

<span data-ttu-id="92875-191">수학의 10진수 숫자와 마찬가지로, C#에서 double에는 반올림 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-191">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="92875-192">다음 코드를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="92875-192">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="92875-193">`0.3` 반복은 `1/3`과 정확하게 동일하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-193">You know that `0.3` repeating is not exactly the same as `1/3`.</span></span>

<span data-ttu-id="92875-194">***과제***</span><span class="sxs-lookup"><span data-stu-id="92875-194">***Challenge***</span></span>

<span data-ttu-id="92875-195">`double` 형식을 사용하여 큰 숫자, 작은 숫자, 곱하기 및 나누기로 다른 계산을 수행해 보세요.</span><span class="sxs-lookup"><span data-stu-id="92875-195">Try other calculations with large numbers, small numbers, multiplication and division using the `double` type.</span></span>  <span data-ttu-id="92875-196">더 복잡한 계산을 수행해 보세요.</span><span class="sxs-lookup"><span data-stu-id="92875-196">Try more complicated calculations.</span></span>

<span data-ttu-id="92875-197">하는 데 약간의 시간이 챌린지와, 사용할 코드를 작성 한 새로운 방법에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-197">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="92875-198">새 메서드 이름을 `WorkWithDoubles`합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-198">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-fixed-point-types"></a><span data-ttu-id="92875-199">고정 소수점 형식 작업</span><span class="sxs-lookup"><span data-stu-id="92875-199">Work with fixed point types</span></span>

<span data-ttu-id="92875-200">C#의 기본적인 숫자 형식인 정수 형식과 double 형식을 살펴봤습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-200">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="92875-201">학습할 또 다른 형식이 있습니다. 바로 `decimal` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="92875-201">There is one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="92875-202">`decimal` 형식 보다 더 정확 하지만 작은 범위에 `double`합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-202">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="92875-203">**고정 소수점**이라는 용어는 소수점(또는 이진 소수점)이 이동하지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-203">The term **fixed point** means that the decimal point (or binary point) doesn't move.</span></span> <span data-ttu-id="92875-204">이 형식에 대해 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-204">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="92875-205">범위가 `double` 형식보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-205">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="92875-206">다음 코드를 사용하여 소수점이 있는 더 큰 전체 자릿수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-206">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="92875-207">숫자의 `M` 접미사는 상수가 `decimal` 형식을 사용해야 함을 나타내는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="92875-207">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span>

<span data-ttu-id="92875-208">소수점 형식을 사용하는 수학에는 소수점 오른쪽에 더 많은 숫자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-208">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span> 

<span data-ttu-id="92875-209">***과제***</span><span class="sxs-lookup"><span data-stu-id="92875-209">***Challenge***</span></span>

<span data-ttu-id="92875-210">이제 여러 가지 숫자 형식을 살펴봤으므로 반지름이 2.50인치인 원의 면적을 계산하는 코드를 작성하세요.</span><span class="sxs-lookup"><span data-stu-id="92875-210">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 inches.</span></span> <span data-ttu-id="92875-211">원의 면적은 반지름 제곱 곱하기 PI입니다.</span><span class="sxs-lookup"><span data-stu-id="92875-211">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="92875-212">하나의 힌트: C# PI에 대 한 상수를 포함 합니다. <xref:System.Math.PI?displayProperty=nameWithType> 해당 값에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-212">One hint: C# contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> 

<span data-ttu-id="92875-213">답변을 확인할 수 있습니다 [GitHub에서 완성 된 샘플 코드를 살펴보면](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span><span class="sxs-lookup"><span data-stu-id="92875-213">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span></span>

<span data-ttu-id="92875-214">원하는 경우 다른 수식을 시도 하십시오.</span><span class="sxs-lookup"><span data-stu-id="92875-214">Try some other formulas if you'd like.</span></span> 

<span data-ttu-id="92875-215">"숫자 C#에서" 퀵 스타트를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-215">You've completed the "Numbers in C#" quick start.</span></span> <span data-ttu-id="92875-216">계속 진행할 수 있습니다는 [분기, 루프](branches-and-loops-local.md) 사용자 고유의 개발 환경에서 빠른 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="92875-216">You can continue with the [Branches and loops](branches-and-loops-local.md) quick start in your own development environment.</span></span>

<span data-ttu-id="92875-217">다음 항목에서는 C#의 숫자에 대해 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92875-217">You can learn more about numbers in C# in the following topics:</span></span>

<span data-ttu-id="92875-218">[정수 형식 표](../language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="92875-218">[Integral Types Table](../language-reference/keywords/integral-types-table.md) </span></span>  
<span data-ttu-id="92875-219">[부동 소수점 형식 표](../language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="92875-219">[Floating-Point Types Table](../language-reference/keywords/floating-point-types-table.md) </span></span>  
<span data-ttu-id="92875-220">[기본 제공 형식 표](../language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="92875-220">[Built-In Types Table](../language-reference/keywords/built-in-types-table.md) </span></span>  
<span data-ttu-id="92875-221">[암시적 숫자 변환 표](../language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="92875-221">[Implicit Numeric Conversions Table](../language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
[<span data-ttu-id="92875-222">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="92875-222">Explicit Numeric Conversions Table</span></span>](../language-reference/keywords/explicit-numeric-conversions-table.md)

