---
title: "빠른 시작 - 분기 및 루프 - C# 가이드"
description: "분기 및 루프에 관한 이 빠른 시작에서는 C# 코드를 작성하여 문을 반복적으로 실행하기 위한 조건부 분기 및 루프를 지원하는 언어 구문을 살펴봅니다."
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 7954475616b122f8bb96ad00d05b476b3beeb52c
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2017
---
# <a name="branches-and-loops"></a><span data-ttu-id="60611-103">분기 및 루프</span><span class="sxs-lookup"><span data-stu-id="60611-103">Branches and loops</span></span>

<span data-ttu-id="60611-104">이 빠른 시작에서는 변수를 검사하고 해당 변수에 따라 실행 경로를 변경하는 코드를 작성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-104">This quick start teaches you how to write code that examines variables and changes the execution path based on those variables.</span></span> <span data-ttu-id="60611-105">C# 코드를 작성하고 컴파일 및 실행 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="60611-106">이 빠른 시작에는 C#에서 분기 및 루프 구문을 살펴보는 일련의 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-106">The quick start contains a series of lessons that explore branching and looping constructs in C#.</span></span> <span data-ttu-id="60611-107">이러한 단원에서는 C# 언어의 기본 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="60611-108">이 빠른 시작에서는 개발에 사용할 수 있는 컴퓨터가 있다고 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="60611-109">.NET 항목 [Get Started in 10 minutes](https://www.microsoft.com/net/core)(10분 안에 시작)에는 Mac, PC 또는 Linux의 로컬 개발 환경 설정에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="60611-110">사용할 명령에 대한 간단한 개요는 [로컬 빠른 시작 소개](local-environment.md)에 자세한 정보에 대한 링크와 함께 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-110">A quick overview of the commands you'll use is in the [introduction to the local quick starts](local-environment.md) with links to more details.</span></span>

## <a name="make-decisions-using-the-if-statement"></a><span data-ttu-id="60611-111">`if` 문을 사용하여 결정하기</span><span class="sxs-lookup"><span data-stu-id="60611-111">Make decisions using the `if` statement</span></span>

<span data-ttu-id="60611-112">**branches-quickstart**라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="60611-112">Create a directory named **branches-quickstart**.</span></span> <span data-ttu-id="60611-113">현재 디렉터리로 지정하고 `dotnet new console -n BranchesAndLoops -o .`을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-113">Make that the current directory and run `dotnet new console -n BranchesAndLoops -o .`.</span></span> <span data-ttu-id="60611-114">이 명령은 현재 디렉터리에 새 .NET Core 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="60611-114">This command creates a new .NET Core console application in the current directory.</span></span> 

<span data-ttu-id="60611-115">원하는 편집기에서 **Program.cs**를 열고 `Console.Writeline("Hello World!");` 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="60611-115">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following code:</span></span>

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

<span data-ttu-id="60611-116">콘솔 창에 `dotnet run`을 입력하여 이 코드를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="60611-116">Try this code by typing `dotnet run` in the your console window.</span></span> <span data-ttu-id="60611-117">“The answer is greater than 10.”(답은 10보다 큽니다.)이라는 메시지가</span><span class="sxs-lookup"><span data-stu-id="60611-117">You should see the message "The answer is greater than 10."</span></span> <span data-ttu-id="60611-118">콘솔에 출력되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-118">printed to your console.</span></span>

<span data-ttu-id="60611-119">합계가 10보다 작도록 `b`의 선언을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-119">Modify the declaration of `b` so that the sum is less than 10:</span></span> 

```csharp
int b = 3;
```

<span data-ttu-id="60611-120">`dotnet run`을 다시 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-120">Type `dotnet run` again.</span></span> <span data-ttu-id="60611-121">답이 10보다 작기 때문에 아무것도 출력되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-121">Because the answer is less than 10, nothing is printed.</span></span> <span data-ttu-id="60611-122">테스트하는 **조건**은 false입니다.</span><span class="sxs-lookup"><span data-stu-id="60611-122">The **condition** you're testing is false.</span></span> <span data-ttu-id="60611-123">`if` 문에 대해 가능한 분기 중 하나(true 분기)만 작성했기 때문에 실행할 코드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-123">You don't have any code to execute because you've only written one of the possible branches for an `if` statement: the true branch.</span></span>

> [!TIP]
> <span data-ttu-id="60611-124">C# (또는 다른 프로그래밍 언어)를 살펴보면서 코드를 작성할 때 실수를 하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60611-124">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="60611-125">컴파일러가 오류를 찾아 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-125">The compiler will find and report the errors.</span></span> <span data-ttu-id="60611-126">오류 출력 및 오류를 생성한 코드를 자세히 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="60611-126">Look closely at the error output and the code that generated the error.</span></span> <span data-ttu-id="60611-127">일반적으로 컴파일러 오류는 문제를 찾는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-127">The compler error can usually help you find the problem.</span></span> 

<span data-ttu-id="60611-128">이 첫 번째 샘플에서는 `if`의 기능과 부울 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="60611-128">This first sample shows the power of `if` and Boolean types.</span></span> <span data-ttu-id="60611-129">*부울*은 `true` 또는 `false`의 두 값 중 하나를 가질 수 있는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="60611-129">A *Boolean* is a variable that can have one of two values: `true` or `false`.</span></span> <span data-ttu-id="60611-130">C#은 부울 변수에 대한 특수 형식 `bool`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-130">C# defines a special type, `bool` for Boolean variables.</span></span> <span data-ttu-id="60611-131">`if` 문은 `bool`의 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-131">The `if` statement checks the value of a `bool`.</span></span> <span data-ttu-id="60611-132">값이 `true`인 경우 `if` 뒤의 문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="60611-132">When the value is `true`, the statement following the `if` executes.</span></span> <span data-ttu-id="60611-133">그러하지 않으면 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="60611-133">Otherwise, it is skipped.</span></span> 

<span data-ttu-id="60611-134">조건을 확인하고 해당 조건에 따라 문을 실행하는 이 프로세스는 아주 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-134">This process of checking conditions and executing statements based on those conditions is very powerful.</span></span>


## <a name="make-if-and-else-work-together"></a><span data-ttu-id="60611-135">if와 else를 함께 사용하기</span><span class="sxs-lookup"><span data-stu-id="60611-135">Make if and else work together</span></span>

<span data-ttu-id="60611-136">true 분기와 false 분기의 여러 코드를 실행하려면 조건이 false일 때 실행되는 `else` 분기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-136">To execute different code in both the true and false branches, you create an `else` branch that executes when the condition is false.</span></span> <span data-ttu-id="60611-137">다음과 같이 해보세요.</span><span class="sxs-lookup"><span data-stu-id="60611-137">Try this.</span></span> <span data-ttu-id="60611-138">아래 코드의 마지막 두 줄을 `Main` 메서드에 추가합니다(이미 처음 네 줄은 있음).</span><span class="sxs-lookup"><span data-stu-id="60611-138">Add the last two lines in the code below to your `Main` method (you should already have the first four):</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

<span data-ttu-id="60611-139">`else` 키워드 뒤의 문은 테스트하는 조건이 `false`인 경우에만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="60611-139">The statement following the `else` keyword executes only when the condition being tested is `false`.</span></span> <span data-ttu-id="60611-140">`if` 및 `else`를 부울 조건과 결합하면 `true`와 `false` 조건을 모두 처리하는 데 필요한 모든 기능이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="60611-140">Combining `if` and `else` with Boolean conditions provides all the power you need to handle both a `true` and a `false` condition.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60611-141">`if` 및 `else` 문 아래의 들여쓰기는 사용자가 보기 편하도록 하기 위함입니다.</span><span class="sxs-lookup"><span data-stu-id="60611-141">The indentation under the `if` and `else` statements is for human readers.</span></span>
> <span data-ttu-id="60611-142">C# 언어는 들여쓰기 또는 공백을 중요하게 취급하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-142">The C# language doesn't treat indentation or whitespace as significant.</span></span> <span data-ttu-id="60611-143">`if` 또는 `else` 키워드 뒤의 문은 조건에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="60611-143">The statement following the `if` or `else` keyword will be executed based on the condition.</span></span> <span data-ttu-id="60611-144">이 빠른 시작의 모든 샘플에서는 문의 제어 흐름을 기준으로 줄을 들여쓰는 일반적인 방법을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="60611-144">All the samples in this quick start follow a common practice to indent lines based on the control flow of statements.</span></span>

<span data-ttu-id="60611-145">들여쓰기는 중요하지 않기 때문에 `{` 및 `}`를 사용하여 두 개 이상의 문이 조건부로 실행되는 블록의 일부가 되는 시기를 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-145">Because indentation is not significant, you need to use `{` and `}` to indicate when you want more than one statement to be part of the block that executes conditionally.</span></span> <span data-ttu-id="60611-146">C# 프로그래머는 일반적으로 모든 `if` 및 `else` 절에서 중괄호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-146">C# programmers typically use those braces on all `if` and `else` clauses.</span></span> <span data-ttu-id="60611-147">다음 예제는 방금 작성한 코드와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-147">The following example is the same as the one you just created.</span></span> <span data-ttu-id="60611-148">다음 코드와 일치하도록 위의 코드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-148">Modify your code above to match the following code:</span></span>

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
> <span data-ttu-id="60611-149">이 빠른 시작의 나머지 부분에서 코드 샘플에는 일반적인 방법에 따라 모두 중괄호가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-149">Through the rest of this quick start, the code samples all include the braces, following accepted practices.</span></span>

<span data-ttu-id="60611-150">더 복잡한 조건을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-150">You can test more complicated conditions.</span></span> <span data-ttu-id="60611-151">`Main` 메서드에서 지금까지 작성한 코드 뒤에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-151">Add the following code in your `Main` method after the code you've written so far:</span></span>

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

<span data-ttu-id="60611-152">`&&`는 “and”를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="60611-152">The `&&` represents "and".</span></span> <span data-ttu-id="60611-153">true 분기에서 문을 실행하려면 두 조건이 모두 true여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-153">It means both conditions must be true to execute the statement in the true branch.</span></span>  <span data-ttu-id="60611-154">이러한 예제에서는 `{` 및 `}`로 문을 묶으면 각 조건부 분기에 여러 문을 가질 수 있음도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="60611-154">These examples also show that you can have multiple statements in each conditional branch, provided you enclose them in `{` and `}`.</span></span>

<span data-ttu-id="60611-155">`||`을 사용하여 “or”를 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-155">You can also use  `||` to represent "or".</span></span> <span data-ttu-id="60611-156">지금까지 작성한 코드 뒤에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-156">Add the following code after what you've written so far:</span></span>

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

<span data-ttu-id="60611-157">첫 번째 단계를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-157">You've finished the first step.</span></span> <span data-ttu-id="60611-158">다음 섹션을 시작하기 전에 현재 코드를 별도의 메서드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-158">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="60611-159">이렇게 하면 새 예제 작업을 쉽게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-159">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="60611-160">`Main` 메서드의 이름을 `ExploreIf`로 바꾸고 `ExploreIf`를 호출하는 새 `Main` 메서드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-160">Rename your `Main` method to `ExploreIf` and write a new `Main` method that calls `ExploreIf`.</span></span> <span data-ttu-id="60611-161">작업을 마치면 코드가 다음과 같이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60611-161">When you have finished, your code should look like this:</span></span>

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

<span data-ttu-id="60611-162">`ExploreIf()`에 대한 호출을 주석으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-162">Comment out the call to `ExploreIf()`.</span></span> <span data-ttu-id="60611-163">그러면 이 섹션에서 작업할 때 출력이 덜 복잡해집니다.</span><span class="sxs-lookup"><span data-stu-id="60611-163">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//ExploreIf();
```

<span data-ttu-id="60611-164">`//`는 C#에서 **주석**을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-164">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="60611-165">주석은 소스 코드에 유지하되 코드로 실행하지는 않으려는 모든 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="60611-165">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="60611-166">컴파일러는 주석에서 실행 코드를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-166">The compiler does not generate any executable code from comments.</span></span>

## <a name="use-loops-to-repeat-operations"></a><span data-ttu-id="60611-167">루프를 사용하여 작업 반복</span><span class="sxs-lookup"><span data-stu-id="60611-167">Use loops to repeat operations</span></span>

<span data-ttu-id="60611-168">이 섹션에서는 **루프**를 사용하여 문을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-168">In this section you use **loops** to repeat statements.</span></span> <span data-ttu-id="60611-169">`Main` 메서드에 다음 코드를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="60611-169">Try this code in your `Main` method:</span></span>

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

<span data-ttu-id="60611-170">`while` 문은 조건을 검사하고 `while` 뒤에 있는 문 또는 문 블록을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-170">The `while` statement checks a condition and executes the statement or statement block following the `while`.</span></span> <span data-ttu-id="60611-171">조건이 false가 될 때까지 반복적으로 조건을 확인하고 해당 문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-171">It repeatedly checks the condition and executing those statements until the condition is false.</span></span>

<span data-ttu-id="60611-172">이 예제에서는 다른 새 연산자가 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-172">There's one other new operator in this example.</span></span> <span data-ttu-id="60611-173">`counter` 변수 뒤의 `++`는 **증가** 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="60611-173">The `++` after the `counter` variable is the **increment** operator.</span></span> <span data-ttu-id="60611-174">이 연산자는 `counter`의 값에 1을 더하고 해당 값을 `counter` 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-174">It adds 1 to the value of `counter` and stores that value in the `counter` variable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60611-175">코드를 실행할 때 `while` 루프 조건이 false로 바뀌는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-175">Make sure that the `while` loop condition changes to false as you execute the code.</span></span> <span data-ttu-id="60611-176">그러하지 않으면 프로그램이 종료되지 않는 **무한 루프**를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-176">Otherwise, you create an **infinite loop** where your program never ends.</span></span> <span data-ttu-id="60611-177">이러한 내용이 이 샘플에 설명되어 있지는 않은데, **CTRL-C** 또는 다른 방법을 사용하여 프로그램을 강제 종료해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="60611-177">That is not demonstrated in this sample, because you have to force your program to quit using **CTRL-C** or other means.</span></span>

<span data-ttu-id="60611-178">`while` 루프는 `while` 뒤에 코드를 실행하기 전에 조건을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-178">The `while` loop tests the condition before executing the code following the `while`.</span></span> <span data-ttu-id="60611-179">`do` ... `while` 루프는 코드를 먼저 실행한 후 조건을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-179">The `do` ... `while` loop executes the code first, and then checks the condition.</span></span> <span data-ttu-id="60611-180">do while 루프는 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-180">The do while loop is shown in the following code:</span></span>

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

<span data-ttu-id="60611-181">이 `do` 루프 및 이전 `while` 루프는 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-181">This `do` loop and the earlier `while` loop produce the same output.</span></span>

## <a name="work-with-the-for-loop"></a><span data-ttu-id="60611-182">for 루프 작업</span><span class="sxs-lookup"><span data-stu-id="60611-182">Work with the for loop</span></span>

<span data-ttu-id="60611-183">C#에서는 일반적으로 **for** 루프가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="60611-183">The **for** loop is commonly used in C#.</span></span> <span data-ttu-id="60611-184">Main() 메서드에 다음 코드를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="60611-184">Try this code in your Main() method:</span></span>

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

<span data-ttu-id="60611-185">`while` 루프 및 이미 사용한 `do` 루프와 동일한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-185">This does the same work as the `while` loop and the `do` loop you've already used.</span></span> <span data-ttu-id="60611-186">`for` 문에는 작동 방식을 제어하는 세 부분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-186">The `for` statement has three parts that control how it works.</span></span> 

<span data-ttu-id="60611-187">첫 번째 부분은 **for 이니셜라이저입니다**. `for index = 0;`은 `index`가 루프 변수임을 선언하고 첫 번째 값을 `0`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-187">The first part is the **for initializer**: `for index = 0;` declares that `index` is the loop variable, and sets its initial value to `0`.</span></span>

<span data-ttu-id="60611-188">중간 부분은 **for 조건입니다**. `index < 10`은 이 `for` 루프가 카운터 값이 10보다 작으면 계속 실행됨을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-188">The middle part is the **for condition**: `index < 10` declares that this `for` loop continues to execute as long as the value of counter is less than 10.</span></span>

<span data-ttu-id="60611-189">마지막 부분은 **for 반복기입니다**. `index++`는 `for` 문 다음의 블록을 실행한 후 루프 변수를 수정하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-189">The final part is the **for iterator**: `index++` specifies how to modify the loop variable after executing the block following the `for` statement.</span></span> <span data-ttu-id="60611-190">여기서 `index`는 블록이 실행될 때마다 1씩 증가하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-190">Here, it specifies that `index` should be incremented by 1 each time the block executes.</span></span>

<span data-ttu-id="60611-191">직접 실습해 보세요.</span><span class="sxs-lookup"><span data-stu-id="60611-191">Experiment with these yourself.</span></span> <span data-ttu-id="60611-192">다음 각각을 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="60611-192">Try each of the following:</span></span>

- <span data-ttu-id="60611-193">다른 값으로 시작하도록 이니셜라이저를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-193">Change the initializer to start at a different value.</span></span>
- <span data-ttu-id="60611-194">다른 값에서 중지하도록 조건을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-194">Change the condition to stop at a different value.</span></span>

<span data-ttu-id="60611-195">완료하면, 학습한 내용을 토대로 직접 코드를 작성해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-195">When you're done, let's move on to write some code yourself to use what you've learned.</span></span>

## <a name="combine-branches-and-loops"></a><span data-ttu-id="60611-196">분기 및 루프 결합</span><span class="sxs-lookup"><span data-stu-id="60611-196">Combine branches and loops</span></span>

<span data-ttu-id="60611-197">이제 C# 언어로 된 `if` 문과 루프 구조를 확인했습니다. C# 코드를 작성하여 3으로 나눌 수 있는, 1에서 20까지의 모든 정수의 합계를 찾을 수 있는지 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="60611-197">Now that you've seen the `if` statement and the looping constructs in the C# language, see if you can write C# code to find the sum of all integers 1 through 20 that are divisible by 3.</span></span>  <span data-ttu-id="60611-198">다음은 몇 가지 힌트입니다.</span><span class="sxs-lookup"><span data-stu-id="60611-198">Here are a few hints:</span></span>

- <span data-ttu-id="60611-199">`%` 연산자는 나누기 연산의 나머지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-199">The `%` operator gives you the remainder of a division operation.</span></span>
- <span data-ttu-id="60611-200">`if` 문은 숫자가 합계의 일부여야 하는지를 확인하는 조건을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-200">The `if` statement gives you the condition to see if a number should be part of the sum.</span></span>
- <span data-ttu-id="60611-201">`for` 루프는 1에서 20까지의 모든 숫자에 대해 일련의 단계를 반복하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60611-201">The `for` loop can help you repeat a series of steps for all the numbers 1 through 20.</span></span>

<span data-ttu-id="60611-202">직접 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="60611-202">Try it yourself.</span></span> <span data-ttu-id="60611-203">그런 다음 어떻게 했는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="60611-203">Then check how you did.</span></span> <span data-ttu-id="60611-204">답으로 63을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60611-204">You should get 63 for an answer.</span></span> <span data-ttu-id="60611-205">[GitHub에서 완성된 코드를 보고](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54) 가능한 한 가지 답을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-205">You can see one possible answer by [viewing the completed code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span></span>

<span data-ttu-id="60611-206">“분기 및 루프” 빠른 시작을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-206">You've completed the "branches and loops" quick start.</span></span>

<span data-ttu-id="60611-207">사용자의 개발 환경에서 [배열 및 컬렉션](arrays-and-collections.md) 빠른 시작을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-207">You can continue with the [Arrays and collections](arrays-and-collections.md) quick start in your own development environment.</span></span>

<span data-ttu-id="60611-208">다음 항목에서는 해당 개념에 대해 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60611-208">You can learn more about these concepts in these topics:</span></span>

<span data-ttu-id="60611-209">[If 및 else 문](../language-reference/keywords/if-else.md) </span><span class="sxs-lookup"><span data-stu-id="60611-209">[If and else statement](../language-reference/keywords/if-else.md) </span></span>  
<span data-ttu-id="60611-210">[While 문](../language-reference/keywords/while.md) </span><span class="sxs-lookup"><span data-stu-id="60611-210">[While statement](../language-reference/keywords/while.md) </span></span>  
<span data-ttu-id="60611-211">[Do 문](../language-reference/keywords/do.md) </span><span class="sxs-lookup"><span data-stu-id="60611-211">[Do statement](../language-reference/keywords/do.md) </span></span>  
[<span data-ttu-id="60611-212">For 문</span><span class="sxs-lookup"><span data-stu-id="60611-212">For statement</span></span>](../language-reference/keywords/for.md)   
