---
title: C#의 숫자 자습서 - C# 로컬 빠른 시작
description: 숫자 형식, 해당 속성 및 메서드를 살펴보면서 C#을 학습합니다.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: cf8f00193b4fa66ff444fe8e40942c39e99d10b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="numbers-in-c-quickstart"></a><span data-ttu-id="573a2-103">C#의 숫자 빠른 시작</span><span class="sxs-lookup"><span data-stu-id="573a2-103">Numbers in C# quickstart</span></span>

<span data-ttu-id="573a2-104">이 빠른 시작에서는 C#의 숫자 형식을 대화형으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-104">This quickstart teaches you about the number types in C# interactively.</span></span> <span data-ttu-id="573a2-105">작은 양의 코드를 작성한 다음 해당 코드를 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="573a2-106">이 빠른 시작에는 C#의 숫자 및 수학 연산을 살펴보는 일련의 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-106">The quickstart contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="573a2-107">이러한 단원에서는 C# 언어의 기본 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="573a2-108">이 빠른 시작에서는 개발에 사용할 수 있는 컴퓨터가 있다고 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-108">This quickstart expects you to have a machine you can use for development.</span></span> <span data-ttu-id="573a2-109">.NET 항목 [Get Started in 10 minutes](https://www.microsoft.com/net/core)(10분 안에 시작)에는 Mac, PC 또는 Linux의 로컬 개발 환경 설정에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="573a2-110">사용할 명령에 대한 간단한 개요는 [로컬 빠른 시작 소개](local-environment.md)에 나와 있으며, 이 소개에는 자세한 정보에 대한 링크도 함께 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-110">A quick overview of the commands you'll use is in the [introduction to the local quickstarts](local-environment.md) with links to more details.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="573a2-111">정수 계산 살펴보기</span><span class="sxs-lookup"><span data-stu-id="573a2-111">Explore integer math</span></span>

<span data-ttu-id="573a2-112">**numbers-quickstart**라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-112">Create a directory named **numbers-quickstart**.</span></span> <span data-ttu-id="573a2-113">현재 디렉터리로 지정하고 `dotnet new console -n NumbersInCSharp -o .`을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-113">Make that the current directory and run `dotnet new console -n NumbersInCSharp -o .`.</span></span>

<span data-ttu-id="573a2-114">원하는 편집기에서 **Program.cs**를 열고 `Console.Writeline("Hello World!");` 줄을 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-114">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="573a2-115">명령 창에 `dotnet run`을 입력하여 이 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-115">Run this code by typing `dotnet run` in your command window.</span></span> 

<span data-ttu-id="573a2-116">정수를 사용하는 기본 수학 연산 중 하나를 방금 살펴봤습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-116">You've just seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="573a2-117">`int` 형식은 **정수**(양의 정수 또는 음의 정수)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-117">The `int` type represents an **integer**, a positive or negative whole number.</span></span> <span data-ttu-id="573a2-118">더하기의 경우 `+` 기호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-118">You use the `+` symbol for addition.</span></span> <span data-ttu-id="573a2-119">정수에 대해 다른 일반적인 수학 연산은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-119">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="573a2-120">빼기의 경우 `-`</span><span class="sxs-lookup"><span data-stu-id="573a2-120">`-` for subtraction</span></span>
- <span data-ttu-id="573a2-121">곱하기의 경우 `*`</span><span class="sxs-lookup"><span data-stu-id="573a2-121">`*` for multiplication</span></span>
- <span data-ttu-id="573a2-122">나누기의 경우 `/`</span><span class="sxs-lookup"><span data-stu-id="573a2-122">`/` for division</span></span>

<span data-ttu-id="573a2-123">다른 연산을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="573a2-123">Start by exploring those different operations.</span></span> <span data-ttu-id="573a2-124">`c`의 값을 쓰는 줄 뒤에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-124">Add these lines after the line that writes the value of `c`:</span></span>

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="573a2-125">명령 창에 `dotnet run`을 입력하여 이 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-125">Run this code by typing `dotnet run` in your command window.</span></span> 
    
<span data-ttu-id="573a2-126">원하는 경우 동일한 줄에서 여러 수학 연산을 수행하여 실험할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-126">You can also experiment by performing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="573a2-127">예를 들어 `c = a + b - 12 * 17;`을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="573a2-127">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="573a2-128">변수와 상수를 혼합해서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-128">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="573a2-129">C# (또는 다른 프로그래밍 언어)를 살펴보면서 코드를 작성할 때 실수를 하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-129">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="573a2-130">**컴파일러**는 그러한 오류를 찾아 사용자에게 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-130">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="573a2-131">출력에 오류 메시지가 포함되어 있으면 예제 코드와 창의 코드를 자세히 살펴보고 수정 사항을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="573a2-131">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="573a2-132">이 연습은 C# 코드의 구조를 학습하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-132">That exercise will help you learn the structure of C# code.</span></span>     

<span data-ttu-id="573a2-133">첫 번째 단계를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-133">You've finished the first step.</span></span> <span data-ttu-id="573a2-134">다음 섹션을 시작하기 전에 현재 코드를 별도의 메서드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-134">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="573a2-135">이렇게 하면 새 예제 작업을 쉽게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-135">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="573a2-136">`Main` 메서드의 이름을 `WorkingWithIntegers`로 바꾸고 `WorkingWithIntegers`를 호출하는 새 `Main` 메서드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-136">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="573a2-137">작업을 마치면 코드가 다음과 같이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-137">When you have finished, your code should look like this:</span></span>

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

## <a name="explore-order-of-operations"></a><span data-ttu-id="573a2-138">연산 순서 알아보기</span><span class="sxs-lookup"><span data-stu-id="573a2-138">Explore order of operations</span></span>

<span data-ttu-id="573a2-139">`WorkingWithIntegers()`에 대한 호출을 주석으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-139">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="573a2-140">그러면 이 섹션에서 작업할 때 출력이 덜 복잡해집니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-140">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="573a2-141">`//`는 C#에서 **주석**을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-141">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="573a2-142">주석은 소스 코드에 유지하되 코드로 실행하지는 않으려는 모든 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-142">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="573a2-143">컴파일러는 주석에서 실행 코드를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-143">The compiler does not generate any executable code from comments.</span></span>

<span data-ttu-id="573a2-144">C# 언어는 수학에서 배운 규칙과 일치하는 규칙으로 여러 가지 수학 연산의 우선 순위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-144">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="573a2-145">곱하기와 나누기는 더하기와 빼기보다 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-145">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="573a2-146">다음 코드를 `Main` 메서드에 추가하고 `dotnet run`을 실행하여 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-146">Explore that by adding the following code to your `Main` method, and execuing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="573a2-147">출력에서는 곱하기가 수행된 후 더하기가 수행되었음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-147">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="573a2-148">먼저 수행하려는 연산 주위에 괄호를 추가하여 다른 연산 순서를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-148">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="573a2-149">다음 줄을 추가하고 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-149">Add the following lines and run again:</span></span>

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="573a2-150">여러 다른 연산을 결합하여 자세히 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="573a2-150">Explore more by combining many different operations.</span></span> <span data-ttu-id="573a2-151">`Main` 메서드의 아래쪽에 다음과 같은 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-151">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="573a2-152">`dotnet run`을 다시 시도해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-152">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="573a2-153">정수에 대해 흥미로운 동작을 이미 알고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-153">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="573a2-154">정수 나누기는 결과에 소수 또는 소수 부분이 포함될 것으로 예상되는 경우에도 항상 정수 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-154">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="573a2-155">이 동작을 못 봤다면 `Main` 메서드의 끝에 다음 코드를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-155">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="573a2-156">`dotnet run`을 다시 입력하여 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-156">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="573a2-157">넘어가기 전에 이 섹션에서 작성한 모든 코드를 새 메서드에 배치해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-157">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="573a2-158">이러한 새 메서드의 이름을 `OrderPrecedence`라고 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-158">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="573a2-159">다음과 같은 코드가 만들어질 것입니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-159">You should end up with something like this:</span></span>

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

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="573a2-160">정수 전체 자릿수 및 한도 살펴보기</span><span class="sxs-lookup"><span data-stu-id="573a2-160">Explore integer precision and limits</span></span>
<span data-ttu-id="573a2-161">마지막 샘플에서는 정수 나누기가 결과를 자르는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-161">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="573a2-162">**modulo** 연산자(`%` 문자)를 사용하여 **나머지**를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-162">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="573a2-163">`Main` 메서드에 다음 코드를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-163">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="573a2-164">C# 정수 형식은 한 가지 다른 면에서 수학의 정수와 다릅니다. 즉 `int` 형식에는 최소 한도와 최대 한도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-164">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="573a2-165">이 코드를 `Main` 메서드에 추가하여 해당 한도를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-165">Add this code to your `Main` method to see those limits:</span></span>
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="573a2-166">계산이 해당 한도를 초과하는 값을 생성하는 경우 **언더플로** 또는 **오버플로** 조건이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-166">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="573a2-167">답은 한 한도에서 다른 한도로 래핑하는 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-167">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="573a2-168">다음 두 줄을 `Main` 메서드에 추가하여 예제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-168">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
<span data-ttu-id="573a2-169">답은 최소 (음의) 정수와 아주 가깝습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-169">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="573a2-170">`min + 2`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-170">It's the same as `min + 2`.</span></span> <span data-ttu-id="573a2-171">더하기 연산은 정수에 대해 허용된 값을 **오버플로했습니다**.</span><span class="sxs-lookup"><span data-stu-id="573a2-171">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="573a2-172">오버플로가 가능한 가장 큰 정수에서 가장 작은 정수로 “래핑”하기 때문에 답은 아주 큰 음수입니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-172">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="573a2-173">`int` 형식이 요구 사항을 충족하지 않을 때 사용하는 여러 한도와 전체 자릿수가 있는 다른 숫자 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-173">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="573a2-174">이에 대해 다음에 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-174">Let's explore those next.</span></span>

<span data-ttu-id="573a2-175">다시 한번, 이 섹션에서 작성한 코드를 별도의 메서드로 이동해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-175">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="573a2-176">이 EventHandler의 이름을 `TestLimits`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-176">Name it `TestLimits`.</span></span> 

## <a name="work-with-the-double-type"></a><span data-ttu-id="573a2-177">double 형식 작업</span><span class="sxs-lookup"><span data-stu-id="573a2-177">Work with the double type</span></span>

<span data-ttu-id="573a2-178">`double` 숫자 형식은 배정밀도 부동 소수점 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-178">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="573a2-179">이러한 용어는 생소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-179">Those terms may be new to you.</span></span> <span data-ttu-id="573a2-180">**부동 소수점** 수는 아주 크거나 작은 정수가 아닌 수를 나타낼 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-180">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="573a2-181">**배정밀도**란 이러한 숫자가 **단정밀도**보다 큰 전체 자릿수를 사용하여 저장됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-181">**Double-precision** means that these numbers are stored using greater precision than **single-precision**.</span></span> <span data-ttu-id="573a2-182">최신 컴퓨터에서는 단정밀도 숫자보다 배정밀도를 더 많이 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-182">On modern computers, it is more common to use double precision than single precision numbers.</span></span>
<span data-ttu-id="573a2-183">지금 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="573a2-183">Let's explore.</span></span> <span data-ttu-id="573a2-184">다음 코드를 추가하고 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-184">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="573a2-185">답에 몫의 소수 부분이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-185">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="573a2-186">double을 사용하여 약간 더 복잡한 식을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="573a2-186">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="573a2-187">double 값의 범위는 정수 값보다 훨씬 큽니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-187">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="573a2-188">지금까지 작성한 코드 아래에 다음 코드를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-188">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="573a2-189">이러한 값은 과학적 표기법으로 인쇄됩니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-189">These values are printed out in scientific notation.</span></span> <span data-ttu-id="573a2-190">`E`의 왼쪽에 있는 숫자는 유효 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-190">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="573a2-191">오른쪽의 숫자는 지수이며 10의 배수입니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-191">The number to the right is the exponent, as a power of 10.</span></span> 

<span data-ttu-id="573a2-192">수학의 10진수 숫자와 마찬가지로, C#에서 double에는 반올림 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-192">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="573a2-193">다음 코드를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="573a2-193">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="573a2-194">`0.3` 반복은 `1/3`과 정확하게 동일하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-194">You know that `0.3` repeating is not exactly the same as `1/3`.</span></span>

<span data-ttu-id="573a2-195">***과제***</span><span class="sxs-lookup"><span data-stu-id="573a2-195">***Challenge***</span></span>

<span data-ttu-id="573a2-196">`double` 형식을 사용하여 큰 숫자, 작은 숫자, 곱하기 및 나누기로 다른 계산을 수행해 보세요.</span><span class="sxs-lookup"><span data-stu-id="573a2-196">Try other calculations with large numbers, small numbers, multiplication and division using the `double` type.</span></span>  <span data-ttu-id="573a2-197">더 복잡한 계산을 수행해 보세요.</span><span class="sxs-lookup"><span data-stu-id="573a2-197">Try more complicated calculations.</span></span>

<span data-ttu-id="573a2-198">과제를 하느라 약간의 시간을 보낸 후 작성한 코드를 새 메서드에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-198">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="573a2-199">이러한 새 메서드의 이름을 `WorkWithDoubles`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-199">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-fixed-point-types"></a><span data-ttu-id="573a2-200">고정 소수점 형식 작업</span><span class="sxs-lookup"><span data-stu-id="573a2-200">Work with fixed point types</span></span>

<span data-ttu-id="573a2-201">C#의 기본적인 숫자 형식인 정수 형식과 double 형식을 살펴봤습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-201">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="573a2-202">학습할 또 다른 형식이 있습니다. 바로 `decimal` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-202">There is one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="573a2-203">`decimal` 형식은 범위가 작지만 `double`보다 전체 자릿수가 큽니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-203">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="573a2-204">**고정 소수점**이라는 용어는 소수점(또는 이진 소수점)이 이동하지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-204">The term **fixed point** means that the decimal point (or binary point) doesn't move.</span></span> <span data-ttu-id="573a2-205">이 형식에 대해 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-205">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="573a2-206">범위가 `double` 형식보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-206">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="573a2-207">다음 코드를 사용하여 소수점이 있는 더 큰 전체 자릿수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-207">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="573a2-208">숫자의 `M` 접미사는 상수가 `decimal` 형식을 사용해야 함을 나타내는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-208">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span>

<span data-ttu-id="573a2-209">소수점 형식을 사용하는 수학에는 소수점 오른쪽에 더 많은 숫자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-209">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span> 

<span data-ttu-id="573a2-210">***과제***</span><span class="sxs-lookup"><span data-stu-id="573a2-210">***Challenge***</span></span>

<span data-ttu-id="573a2-211">이제 여러 가지 숫자 형식을 살펴봤으므로 반지름이 2.50센티미터인 원의 면적을 계산하는 코드를 작성하세요.</span><span class="sxs-lookup"><span data-stu-id="573a2-211">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 centimeters.</span></span> <span data-ttu-id="573a2-212">원의 면적은 반지름 제곱 곱하기 PI입니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-212">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="573a2-213">힌트: .NET에는 PI의 상수가 포함되어 있습니다. 즉 해당 값에 사용할 수 있는 <xref:System.Math.PI?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-213">One hint: .NET contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> 

<span data-ttu-id="573a2-214">19에서 20 사이의 답을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-214">You should get an answer between 19 and 20.</span></span>
<span data-ttu-id="573a2-215">[GitHub에서 완성된 샘플 코드를 보고](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106) 답을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-215">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106)</span></span>

<span data-ttu-id="573a2-216">원하는 경우 다른 수식을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="573a2-216">Try some other formulas if you'd like.</span></span> 

<span data-ttu-id="573a2-217">“C#의 숫자” 빠른 시작을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-217">You've completed the "Numbers in C#" quickstart.</span></span> <span data-ttu-id="573a2-218">자체 개발 환경에서 [분기 및 루프](branches-and-loops-local.md) 빠른 시작을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-218">You can continue with the [Branches and loops](branches-and-loops-local.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="573a2-219">다음 항목에서는 C#의 숫자에 대해 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="573a2-219">You can learn more about numbers in C# in the following topics:</span></span>

<span data-ttu-id="573a2-220">[정수 형식 표](../language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="573a2-220">[Integral Types Table](../language-reference/keywords/integral-types-table.md) </span></span>  
<span data-ttu-id="573a2-221">[부동 소수점 형식 표](../language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="573a2-221">[Floating-Point Types Table](../language-reference/keywords/floating-point-types-table.md) </span></span>  
<span data-ttu-id="573a2-222">[기본 제공 형식 표](../language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="573a2-222">[Built-In Types Table](../language-reference/keywords/built-in-types-table.md) </span></span>  
<span data-ttu-id="573a2-223">[암시적 숫자 변환 표](../language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="573a2-223">[Implicit Numeric Conversions Table](../language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
[<span data-ttu-id="573a2-224">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="573a2-224">Explicit Numeric Conversions Table</span></span>](../language-reference/keywords/explicit-numeric-conversions-table.md)

