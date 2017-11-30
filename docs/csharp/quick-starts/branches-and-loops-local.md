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
# <a name="branches-and-loops"></a><span data-ttu-id="b24c7-103">분기 및 루프</span><span class="sxs-lookup"><span data-stu-id="b24c7-103">Branches and loops</span></span>

<span data-ttu-id="b24c7-104">이 빠른 시작에서는 변수를 검사 하 고 해당 변수를 기반으로 실행 경로 변경 하는 코드를 작성 하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-104">This quick start teaches you how to write code that examines variables and changes the execution path based on those variables.</span></span> <span data-ttu-id="b24c7-105">C# 코드를 작성 하 고이 정보를 컴파일 및 실행 하는 결과 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="b24c7-106">빠른 시작에는 일련의 분기 구문과 루프 구문 C#에서 탐색 하는 단원 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-106">The quick start contains a series of lessons that explore branching and looping constructs in C#.</span></span> <span data-ttu-id="b24c7-107">이러한 단원에서는 C# 언어의 기본 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="b24c7-108">이 빠른 시작에서는 개발에 사용할 수 있습니다를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="b24c7-109">.NET 항목 [10 분 후에 시작](https://www.microsoft.com/net/core) Mac, PC 또는 Linux 로컬 개발 환경 설정에 대 한 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

## <a name="make-decisions-using-the-if-statement"></a><span data-ttu-id="b24c7-110">사용 하 여 결정을 내릴는 `if` 문</span><span class="sxs-lookup"><span data-stu-id="b24c7-110">Make decisions using the `if` statement</span></span>

<span data-ttu-id="b24c7-111">라는 디렉터리를 만들고 **분기가 quickstart**합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-111">Create a directory named **branches-quickstart**.</span></span> <span data-ttu-id="b24c7-112">현재 디렉터리로 지정하고 `dotnet new console -n BranchesAndLoops -o .`을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-112">Make that the current directory and run `dotnet new console -n BranchesAndLoops -o .`.</span></span> <span data-ttu-id="b24c7-113">이 명령은 현재 디렉터리에 새.NET Core 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-113">This command creates a new .NET Core console application in the current directory.</span></span> 

<span data-ttu-id="b24c7-114">열기 **Program.cs** 즐겨 찾는 편집기 및 바꾸기 줄에서 `Console.Writeline("Hello World!");` 를 다음 코드로:</span><span class="sxs-lookup"><span data-stu-id="b24c7-114">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following code:</span></span>

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

<span data-ttu-id="b24c7-115">이 코드를 입력 하 여 시도 `dotnet run` 에 콘솔 창입니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-115">Try this code by typing `dotnet run` in the your console window.</span></span> <span data-ttu-id="b24c7-116">"대 한 대답은 10 보다 큰." 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-116">You should see the message "The answer is greater than 10."</span></span> <span data-ttu-id="b24c7-117">콘솔로 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-117">printed to your console.</span></span>

<span data-ttu-id="b24c7-118">합계가 10보다 작도록 `b`의 선언을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-118">Modify the declaration of `b` so that the sum is less than 10:</span></span> 

```csharp
int b = 3;
```

<span data-ttu-id="b24c7-119">형식 `dotnet run` 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-119">Type `dotnet run` again.</span></span> <span data-ttu-id="b24c7-120">답이 10보다 작기 때문에 아무것도 출력되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-120">Because the answer is less than 10, nothing is printed.</span></span> <span data-ttu-id="b24c7-121">테스트하는 **조건**은 false입니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-121">The **condition** you're testing is false.</span></span> <span data-ttu-id="b24c7-122">`if` 문에 대해 가능한 분기 중 하나(true 분기)만 작성했기 때문에 실행할 코드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-122">You don't have any code to execute because you've only written one of the possible branches for an `if` statement: the true branch.</span></span>

> [!TIP]
> <span data-ttu-id="b24c7-123">C# (또는 다른 프로그래밍 언어)를 살펴보면서 코드를 작성할 때 실수를 하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-123">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="b24c7-124">컴파일러를 찾아서는 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-124">The compiler will find and report the errors.</span></span> <span data-ttu-id="b24c7-125">치중의 오류 출력 및 오류를 생성 하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-125">Look closely the the error output and the code that generated the error.</span></span> <span data-ttu-id="b24c7-126">Compler 오류 문제를 찾을 수 일반적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-126">The compler error can usually help you find the problem.</span></span> 

<span data-ttu-id="b24c7-127">이 첫 번째 샘플의 나와 `if` 및 Boolean 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-127">This first sample shows the power of `if` and Boolean types.</span></span> <span data-ttu-id="b24c7-128">A *부울* 는 두 값 중 하나를 가질 수 있는 변수: `true` 또는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-128">A *Boolean* is a variable that can have one of two values: `true` or `false`.</span></span> <span data-ttu-id="b24c7-129">C# 특별 한 형식 정의 `bool` 부울 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-129">C# defines a special type, `bool` for Boolean variables.</span></span> <span data-ttu-id="b24c7-130">`if` 문은 `bool`의 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-130">The `if` statement checks the value of a `bool`.</span></span> <span data-ttu-id="b24c7-131">값이 `true`인 경우 `if` 뒤의 문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-131">When the value is `true`, the statement following the `if` executes.</span></span> <span data-ttu-id="b24c7-132">그러하지 않으면 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-132">Otherwise, it is skipped.</span></span> 

<span data-ttu-id="b24c7-133">조건을 확인하고 해당 조건에 따라 문을 실행하는 이 프로세스는 아주 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-133">This process of checking conditions and executing statements based on those conditions is very powerful.</span></span>


## <a name="make-if-and-else-work-together"></a><span data-ttu-id="b24c7-134">if와 else를 함께 사용하기</span><span class="sxs-lookup"><span data-stu-id="b24c7-134">Make if and else work together</span></span>

<span data-ttu-id="b24c7-135">true 분기와 false 분기의 여러 코드를 실행하려면 조건이 false일 때 실행되는 `else` 분기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-135">To execute different code in both the true and false branches, you create an `else` branch that executes when the condition is false.</span></span> <span data-ttu-id="b24c7-136">이 작업을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-136">Try this.</span></span> <span data-ttu-id="b24c7-137">아래에 코드에서 두 줄을 추가 하면 `Main` 메서드 (이미 있어야 처음 4 개):</span><span class="sxs-lookup"><span data-stu-id="b24c7-137">Add the last two lines in the code below to your `Main` method (you should already have the first four):</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

<span data-ttu-id="b24c7-138">`else` 키워드 뒤의 문은 테스트하는 조건이 `false`인 경우에만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-138">The statement following the `else` keyword executes only when the condition being tested is `false`.</span></span> <span data-ttu-id="b24c7-139">결합 `if` 및 `else` 와 부울 조건 둘 다 처리 해야 하는 모든 기능을 제공 된 `true` 및 `false` 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-139">Combining `if` and `else` with Boolean conditions provides all the power you need to handle both a `true` and a `false` condition.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b24c7-140">`if` 및 `else` 문 아래의 들여쓰기는 사용자가 보기 편하도록 하기 위함입니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-140">The indentation under the `if` and `else` statements is for human readers.</span></span>
> <span data-ttu-id="b24c7-141">C# 언어는 들여쓰기 또는 공백을 중요하게 취급하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-141">The C# language doesn't treat indentation or whitespace as significant.</span></span> <span data-ttu-id="b24c7-142">`if` 또는 `else` 키워드 뒤의 문은 조건에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-142">The statement following the `if` or `else` keyword will be executed based on the condition.</span></span> <span data-ttu-id="b24c7-143">이 빠른 시작에 있는 모든 샘플의 문 제어 흐름에 따라 줄 들여쓰기로 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-143">All the samples in this quick start follow a common practice to indent lines based on the control flow of statements.</span></span>

<span data-ttu-id="b24c7-144">들여쓰기는 중요하지 않기 때문에 `{` 및 `}`를 사용하여 두 개 이상의 문이 조건부로 실행되는 블록의 일부가 되는 시기를 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-144">Because indentation is not significant, you need to use `{` and `}` to indicate when you want more than one statement to be part of the block that executes conditionally.</span></span> <span data-ttu-id="b24c7-145">C# 프로그래머는 일반적으로 모든 `if` 및 `else` 절에서 중괄호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-145">C# programmers typically use those braces on all `if` and `else` clauses.</span></span> <span data-ttu-id="b24c7-146">다음 예제에서는 방금 만든 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-146">The following example is the same as the one you just created.</span></span> <span data-ttu-id="b24c7-147">다음 코드와 일치 하도록 위의 코드를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-147">Modify your code above to match the following code:</span></span>

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
> <span data-ttu-id="b24c7-148">이 빠른 시작의 나머지 부분을 모든 코드 예제는 뒤에 중괄호를 포함 사례를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-148">Through the rest of this quick start, the code samples all include the braces, following accepted practices.</span></span>

<span data-ttu-id="b24c7-149">더 복잡 한 조건을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-149">You can test more complicated conditions.</span></span> <span data-ttu-id="b24c7-150">에 다음 코드를 추가 하면 `Main` 메서드 후 지금까지 작성 한 코드:</span><span class="sxs-lookup"><span data-stu-id="b24c7-150">Add the following code in your `Main` method after the code you've written so far:</span></span>

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

<span data-ttu-id="b24c7-151">`&&`는 “and”를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-151">The `&&` represents "and".</span></span> <span data-ttu-id="b24c7-152">true 분기에서 문을 실행하려면 두 조건이 모두 true여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-152">It means both conditions must be true to execute the statement in the true branch.</span></span>  <span data-ttu-id="b24c7-153">이러한 예제에서는 `{` 및 `}`로 문을 묶으면 각 조건부 분기에 여러 문을 가질 수 있음도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-153">These examples also show that you can have multiple statements in each conditional branch, provided you enclose them in `{` and `}`.</span></span>

<span data-ttu-id="b24c7-154">사용할 수도 있습니다 `||` 나타내기 위해 "또는".</span><span class="sxs-lookup"><span data-stu-id="b24c7-154">You can also use  `||` to represent "or".</span></span> <span data-ttu-id="b24c7-155">지금까지 작성 한 내용 뒤 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-155">Add the following code after what you've written so far:</span></span>

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

<span data-ttu-id="b24c7-156">첫 번째 단계 작업을 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-156">You've finished the first step.</span></span> <span data-ttu-id="b24c7-157">다음 섹션을 시작하기 전에 현재 코드를 별도의 메서드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-157">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="b24c7-158">이렇게 하면 새 예제 작업을 쉽게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-158">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="b24c7-159">`Main` 메서드의 이름을 `ExploreIf`로 바꾸고 `ExploreIf`를 호출하는 새 `Main` 메서드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-159">Rename your `Main` method to `ExploreIf` and write a new `Main` method that calls `ExploreIf`.</span></span> <span data-ttu-id="b24c7-160">작업을 마치면 코드가 다음과 같이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-160">When you have finished, your code should look like this:</span></span>

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

<span data-ttu-id="b24c7-161">에 대 한 호출을 주석 `ExploreIf()`합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-161">Comment out the call to `ExploreIf()`.</span></span> <span data-ttu-id="b24c7-162">이 섹션에서 작업할 때 덜 복잡 한 출력을 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-162">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//ExploreIf();
```

<span data-ttu-id="b24c7-163">`//` 시작 되는 **주석** C#입니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-163">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="b24c7-164">주석은 모든 텍스트를 소스 코드에 유지 되지만 코드로 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-164">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="b24c7-165">컴파일러는 주석에서 실행 코드를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-165">The compiler does not generate any executable code from comments.</span></span>

## <a name="use-loops-to-repeat-operations"></a><span data-ttu-id="b24c7-166">루프를 사용하여 작업 반복</span><span class="sxs-lookup"><span data-stu-id="b24c7-166">Use loops to repeat operations</span></span>

<span data-ttu-id="b24c7-167">이 섹션에서 사용 **루프** 문을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-167">In this section you use **loops** to repeat statements.</span></span> <span data-ttu-id="b24c7-168">이 코드를 시도 하면 `Main` 메서드:</span><span class="sxs-lookup"><span data-stu-id="b24c7-168">Try this code in your `Main` method:</span></span>

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

<span data-ttu-id="b24c7-169">`while` 문은 조건을 검사 하 고 문 또는 문 블록을 다음 실행에서 `while`합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-169">The `while` statement checks a condition and executes the statement or statement block following the `while`.</span></span> <span data-ttu-id="b24c7-170">반복 해 서 조건과 조건이 false가 될 때까지 해당 문 실행을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-170">It repeatedly checks the condition and executing those statements until the condition is false.</span></span>

<span data-ttu-id="b24c7-171">이 예제에서는 다른 새 연산자가 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-171">There's one other new operator in this example.</span></span> <span data-ttu-id="b24c7-172">`counter` 변수 뒤의 `++`는 **증가** 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-172">The `++` after the `counter` variable is the **increment** operator.</span></span> <span data-ttu-id="b24c7-173">값에 1이 더해집니다 `counter` 에 해당 값을 저장 하 고는 `counter` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-173">It adds 1 to the value of `counter` and stores that value in the `counter` variable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b24c7-174">다음 사항을 확인는 `while` 코드를 실행 하면서 루프를 false로 조건을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-174">Make sure that the `while` loop condition changes to false as you execute the code.</span></span> <span data-ttu-id="b24c7-175">그러하지 않으면 프로그램이 종료되지 않는 **무한 루프**를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-175">Otherwise, you create an **infinite loop** where your program never ends.</span></span> <span data-ttu-id="b24c7-176">설명 하지 않음이 샘플 사용을 중지 하려면 프로그램을 강제로 해야 하기 때문에 **Ctrl-c** 또는 다른 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-176">That is not demonstrated in this sample, because you have to force your program to quit using **CTRL-C** or other means.</span></span>

<span data-ttu-id="b24c7-177">`while` 루프는 `while` 뒤에 코드를 실행하기 전에 조건을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-177">The `while` loop tests the condition before executing the code following the `while`.</span></span> <span data-ttu-id="b24c7-178">`do` ... `while` 루프는 코드를 먼저 실행한 후 조건을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-178">The `do` ... `while` loop executes the code first, and then checks the condition.</span></span> <span data-ttu-id="b24c7-179">루프는 다음 코드에 표시 되는 방법:</span><span class="sxs-lookup"><span data-stu-id="b24c7-179">The do while loop is shown in the following code:</span></span>

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

<span data-ttu-id="b24c7-180">이 `do` 루프 및 이전 `while` 루프 같은 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-180">This `do` loop and the earlier `while` loop produce the same output.</span></span>

## <a name="work-with-the-for-loop"></a><span data-ttu-id="b24c7-181">for 루프 작업</span><span class="sxs-lookup"><span data-stu-id="b24c7-181">Work with the for loop</span></span>

<span data-ttu-id="b24c7-182">**에 대 한** 루프를 일반적으로 C#에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-182">The **for** loop is commonly used in C#.</span></span> <span data-ttu-id="b24c7-183">이 코드를 main () 메서드에서 사용해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="b24c7-183">Try this code in your Main() method:</span></span>

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

<span data-ttu-id="b24c7-184">`while` 루프 및 이미 사용한 `do` 루프와 동일한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-184">This does the same work as the `while` loop and the `do` loop you've already used.</span></span> <span data-ttu-id="b24c7-185">`for` 문에는 작동 방식을 제어하는 세 부분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-185">The `for` statement has three parts that control how it works.</span></span> 

<span data-ttu-id="b24c7-186">첫 번째 부분은 **for 이니셜라이저입니다**. `for index = 0;`은 `index`가 루프 변수임을 선언하고 첫 번째 값을 `0`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-186">The first part is the **for initializer**: `for index = 0;` declares that `index` is the loop variable, and sets its initial value to `0`.</span></span>

<span data-ttu-id="b24c7-187">중간 부분은 **for 조건입니다**. `index < 10`은 이 `for` 루프가 카운터 값이 10보다 작으면 계속 실행됨을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-187">The middle part is the **for condition**: `index < 10` declares that this `for` loop continues to execute as long as the value of counter is less than 10.</span></span>

<span data-ttu-id="b24c7-188">마지막 부분은 **for 반복기입니다**. `index++`는 `for` 문 다음의 블록을 실행한 후 루프 변수를 수정하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-188">The final part is the **for iterator**: `index++` specifies how to modify the loop variable after executing the block following the `for` statement.</span></span> <span data-ttu-id="b24c7-189">여기서 `index`는 블록이 실행될 때마다 1씩 증가하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-189">Here, it specifies that `index` should be incremented by 1 each time the block executes.</span></span>

<span data-ttu-id="b24c7-190">직접 실습해 보세요.</span><span class="sxs-lookup"><span data-stu-id="b24c7-190">Experiment with these yourself.</span></span> <span data-ttu-id="b24c7-191">다음 각각을 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="b24c7-191">Try each of the following:</span></span>

- <span data-ttu-id="b24c7-192">다른 값으로 시작하도록 이니셜라이저를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-192">Change the initializer to start at a different value.</span></span>
- <span data-ttu-id="b24c7-193">다른 값에서 중지하도록 조건을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-193">Change the condition to stop at a different value.</span></span>

<span data-ttu-id="b24c7-194">완료하면, 학습한 내용을 토대로 직접 코드를 작성해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-194">When you're done, let's move on to write some code yourself to use what you've learned.</span></span>

## <a name="combine-branches-and-loops"></a><span data-ttu-id="b24c7-195">분기와 루프를 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-195">Combine branches and loops</span></span>

<span data-ttu-id="b24c7-196">이제 C# 언어로 된 `if` 문과 루프 구조를 확인했습니다. C# 코드를 작성하여 3으로 나눌 수 있는, 1에서 20까지의 모든 정수의 합계를 찾을 수 있는지 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="b24c7-196">Now that you've seen the `if` statement and the looping constructs in the C# language, see if you can write C# code to find the sum of all integers 1 through 20 that are divisible by 3.</span></span>  <span data-ttu-id="b24c7-197">다음은 몇 가지 힌트입니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-197">Here are a few hints:</span></span>

- <span data-ttu-id="b24c7-198">`%` 연산자는 나누기 연산의 나머지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-198">The `%` operator gives you the remainder of a division operation.</span></span>
- <span data-ttu-id="b24c7-199">`if` 문을 숫자 합계의 일부 여야 하는 경우 참조 하는 조건을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-199">The `if` statement gives you the condition to see if a number should be part of the sum.</span></span>
- <span data-ttu-id="b24c7-200">`for` 루프는 1에서 20까지의 모든 숫자에 대해 일련의 단계를 반복하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-200">The `for` loop can help you repeat a series of steps for all the numbers 1 through 20.</span></span>

<span data-ttu-id="b24c7-201">직접 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="b24c7-201">Try it yourself.</span></span> <span data-ttu-id="b24c7-202">그런 다음 어떻게 했는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b24c7-202">Then check how you did.</span></span> <span data-ttu-id="b24c7-203">한 가지 가능한 대답을 확인할 수 있습니다 [GitHub에서 완성 된 코드를 보는](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54)합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-203">You can see one possible answer by [viewing the completed code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span></span>

<span data-ttu-id="b24c7-204">빠른 시작 "분기 및 루프"를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-204">You've completed the "branches and loops" quick start.</span></span>

<span data-ttu-id="b24c7-205">계속 진행할 수 있습니다는 [배열 및 컬렉션](arrays-and-collections.md) 사용자 고유의 개발 환경에서 빠른 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-205">You can continue with the [Arrays and collections](arrays-and-collections.md) quick start in your own development environment.</span></span>

<span data-ttu-id="b24c7-206">다음 항목에서는 해당 개념에 대해 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24c7-206">You can learn more about these concepts in these topics:</span></span>

<span data-ttu-id="b24c7-207">[If 및 else 문](../language-reference/keywords/if-else.md) </span><span class="sxs-lookup"><span data-stu-id="b24c7-207">[If and else statement](../language-reference/keywords/if-else.md) </span></span>  
<span data-ttu-id="b24c7-208">[While 문](../language-reference/keywords/while.md) </span><span class="sxs-lookup"><span data-stu-id="b24c7-208">[While statement](../language-reference/keywords/while.md) </span></span>  
<span data-ttu-id="b24c7-209">[Do 문](../language-reference/keywords/do.md) </span><span class="sxs-lookup"><span data-stu-id="b24c7-209">[Do statement](../language-reference/keywords/do.md) </span></span>  
[<span data-ttu-id="b24c7-210">For 문</span><span class="sxs-lookup"><span data-stu-id="b24c7-210">For statement</span></span>](../language-reference/keywords/for.md)   
