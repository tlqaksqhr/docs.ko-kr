---
title: "보간된 문자열 자습서 - C# 로컬 빠른 시작"
description: "보간된 문자열에 관한 이 빠른 시작에서는 더 큰 문자열에 식의 결과를 포함하는 C# 코드를 작성합니다."
author: rpetrusha
ms.author: ronpet
ms.date: 01/11/2018
ms.topic: get-started-article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: b6089b69eb350fce29f86f19f5abeb44acb4b6b4
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2018
---
# <a name="interpolated-strings"></a><span data-ttu-id="63e3e-103">보간된 문자열</span><span class="sxs-lookup"><span data-stu-id="63e3e-103">Interpolated strings</span></span>

<span data-ttu-id="63e3e-104">이 빠른 시작에서는 C#에서 보간된 문자열을 사용하여 단일 출력 문자열에 값을 삽입하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-104">This quickstart teaches you how to use interpolated strings in C# to insert values into a single ouput string.</span></span> <span data-ttu-id="63e3e-105">C# 코드를 작성하고 컴파일 및 실행 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="63e3e-106">이 빠른 시작은 문자열에 값을 삽입하고, 이러한 값을 다양한 방식으로 서식화하는 일련의 단원으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-106">The quickstart contains a series of lessons that insert values into strings, and format those values in different ways.</span></span>

<span data-ttu-id="63e3e-107">이 빠른 시작에서는 개발에 사용할 수 있는 컴퓨터가 있다고 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-107">This quickstart expects that you have a machine you can use for development.</span></span> <span data-ttu-id="63e3e-108">.NET 항목 [Get Started in 10 minutes](https://www.microsoft.com/net/core)(10분 안에 시작)에는 Mac, PC 또는 Linux의 로컬 개발 환경 설정에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-108">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="63e3e-109">사용할 명령에 대한 간단한 개요는 [로컬 빠른 시작 소개](local-environment.md)에 나와 있으며, 이 소개에는 자세한 정보에 대한 링크도 함께 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-109">A quick overview of the commands you'll use is in the [introduction to the local quickstarts](local-environment.md) with links to more details.</span></span> 

## <a name="create-an-interpolated-string"></a><span data-ttu-id="63e3e-110">보간된 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="63e3e-110">Create an interpolated string</span></span>

<span data-ttu-id="63e3e-111">**interpolated-quickstart**라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-111">Create a directory named **interpolated-quickstart**.</span></span> <span data-ttu-id="63e3e-112">현재 디렉터리로 만들고 콘솔 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-112">Make it the current directory and run the following command from a console window:</span></span>

```console
dotnet new console -n interpolated -o .
```

<span data-ttu-id="63e3e-113">이 명령은 현재 디렉터리에 새 .NET Core 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-113">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="63e3e-114">원하는 편집기에서 **Program.cs**를 열고 `Console.WriteLine("Hello World!");` 줄을 다음 코드로 바꿉니다. 여기서 `<name>`을 사용자 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-114">Open **Program.cs** in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```
<span data-ttu-id="63e3e-115">콘솔 창에 `dotnet run`을 입력하여 이 코드를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-115">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="63e3e-116">프로그램을 실행하면 인사말에 사용자 이름이 포함된 단일 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-116">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="63e3e-117"><xref:System.Console.WriteLine%2A> 메서드 호출에 포함된 문자열은 *보간된 문자열*입니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-117">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string*.</span></span> <span data-ttu-id="63e3e-118">이는 포함 코드가 들어있는 문자열에서 단일 문자열(*결과 문자열*이라고 함)을 생성할 수 있게 해주는 일종의 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-118">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="63e3e-119">보간된 문자열은 문자열에 값을 삽입하거나 문자열을 연결(함께 조인)하는 데 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-119">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span> 
    
<span data-ttu-id="63e3e-120">다음 간단한 예제에서는 모든 보간된 문자열이 포함해야 하는 두 가지 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-120">This simple example contains the two elements that every interpolated string must have:</span></span> 

- <span data-ttu-id="63e3e-121">`$` 문자로 시작한 후 여는 따옴표 문자가 다음에 나오는 문자열 리터럴.</span><span class="sxs-lookup"><span data-stu-id="63e3e-121">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="63e3e-122">`$` 기호와 따옴표 문자 사이에는 공백이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-122">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="63e3e-123">(공백을 포함하면 어떻게 되는지 확인하려면 `$` 문자 뒤에 공백을 삽입하고 파일을 저장한 후 콘솔 창에 `dotnet run`을 입력하여 프로그램을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-123">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="63e3e-124">C# 컴파일러가 "오류 CS1056: 예기치 않은 문자 '$'"라는 오류 메시지를 표시합니다.)</span><span class="sxs-lookup"><span data-stu-id="63e3e-124">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span> 

- <span data-ttu-id="63e3e-125">하나 이상의 *보간된 식*.</span><span class="sxs-lookup"><span data-stu-id="63e3e-125">One or more *interpolated expressions*.</span></span> <span data-ttu-id="63e3e-126">보간된 식은 열기 및 닫기 중괄호(`{` 및 `}`)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-126">An interpolated expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="63e3e-127">중괄호 안에 값을 반환(`null` 포함)하는 C# 식을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-127">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span> 

<span data-ttu-id="63e3e-128">몇 가지 다른 데이터 형식을 포함하는 보간된 문자열 예제를 더 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-128">Let's try a few more interpolated string examples with some other data types.</span></span>
    
## <a name="include-different-data-types"></a><span data-ttu-id="63e3e-129">다양한 데이터 형식 포함</span><span class="sxs-lookup"><span data-stu-id="63e3e-129">Include different data types</span></span>

<span data-ttu-id="63e3e-130">이전 섹션에서는 한 문자열을 다른 문자열 내에 삽입하는 데 보간된 문자열을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-130">In the previous section, you used an interpolated string to insert one string inside of another.</span></span> <span data-ttu-id="63e3e-131">하지만 보간된 문자열 식은 모든 데이터 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-131">An interpolated string expression can be any data type, though.</span></span> <span data-ttu-id="63e3e-132">여러 데이터 형식의 값을 포함하는 보간된 문자열을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-132">Let's try an interpolated string that has values of multiple data types.</span></span> 
    
<span data-ttu-id="63e3e-133">다음 예제에서는 `Vegetable` 개체, `Unit` 열거형의 멤버, <xref:System.DateTime> 값 및 <xref:System.Decimal> 값이 있는 보간된 식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-133">The following example includes interpolated expressions with a `Vegetable` object, a member of the `Unit` enumeration, a <xref:System.DateTime> value, and a <xref:System.Decimal> value.</span></span> <span data-ttu-id="63e3e-134">편집기에서 모든 C# 코드를 다음 코드로 바꾼 후 `console run` 명령을 사용하여 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-134">Replace all of the C# code in your editor with the following code, and then use the `console run` command to run it:</span></span>

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Example
{
   public enum Unit { item, pound, ounce, dozen };
   
   public static void Main()
   {
      var item = new Vegetable("eggplant");
      var date = DateTime.Now;
      var price = 1.99m;
      var unit = Unit.item;
      Console.WriteLine($"On {date}, the price of {item} was {price} per {unit}.");
   }
}
```
    
<span data-ttu-id="63e3e-135">두 번째 보간된 식에는 콘솔에 표시되는 결과 문자열의 `item` 개체가 포함되며, 이 경우 "eggplant"가 결과 문자열에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-135">Note that the second interpolated expression includes the `item` object in the result string that's displayed to the console, and in this case the string "eggplant" is inserted into the result string.</span></span> <span data-ttu-id="63e3e-136">보간된 식의 형식이 문자열이 아닌 경우 C# 컴파일러가 다음을 수행하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-136">That's because, when the type of an interpolated expression is not a string, the C# compiler does the following:</span></span>

- <span data-ttu-id="63e3e-137">보간된 식이 `null`이면 보간된 식은 빈 문자열("" 또는 <xref:System.String.Empty?displayProperty=nameWithType>)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-137">If the interpolated expression is `null`, the interpolated expression returns an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>).</span></span>

- <span data-ttu-id="63e3e-138">보간된 식이 `null`이 아닌 경우, 보간된 식 형식의 `ToString` 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-138">If the interpolated expression is not `null`, the `ToString` method of the type of the interpolated expression is called.</span></span> <span data-ttu-id="63e3e-139">`Vegetable.ToString` 메서드 정의 앞에 주석 기호(`//`)를 넣어 정의를 주석 처리하여 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-139">You can test this by commenting out the definition of the `Vegetable.ToString` method in the example by putting a comment symbol (`//`) in front of it.</span></span> <span data-ttu-id="63e3e-140">출력에서 "eggplant" 문자열은 형식 이름 "Vegetable"로 바뀌며 이것이 <xref:System.Object.ToString?displayProperty=nameWithType> 메서드의 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-140">In the output, the string "eggplant" is replaced by the type name, "Vegetable", which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span>   

<span data-ttu-id="63e3e-141">이 예제의 출력에서 날짜는 매우 정확하며(eggplant 가격은 초마다 달라지지 않음), 가격 값은 통화 단위를 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-141">In the output from this example, the date is too precise (the price of eggplant does not vary by the second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="63e3e-142">다음 섹션에서는 보간된 식에서 반환된 문자열 형식을 제어하여 해당 문제를 해결하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-142">In the next section, you'll learn how to fix those issues by controlling the format of strings returned by interpolated expressions.</span></span>

## <a name="control-the-formatting-of-interpolated-expressions"></a><span data-ttu-id="63e3e-143">보간된 식의 서식 제어</span><span class="sxs-lookup"><span data-stu-id="63e3e-143">Control the formatting of interpolated expressions</span></span>

<span data-ttu-id="63e3e-144">이전 섹션에서는 형식이 잘못 지정된 두 개의 문자열을 결과 문자열에 삽입했습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-144">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="63e3e-145">하나는 날짜만 적절한 날짜 및 시간 값이었습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-145">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="63e3e-146">두 번째는 통화 단위를 나타내지 않는 가격이었습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-146">The second was a price that did not indicate its unit of currency.</span></span> <span data-ttu-id="63e3e-147">두 가지 문제는 쉽게 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-147">Both issues are easy to address.</span></span> <span data-ttu-id="63e3e-148">보간된 식은 특정 형식의 서식을 제어하는 *형식 문자열*을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-148">Interpolated expressions can include *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="63e3e-149">다음 줄에 표시된 것처럼 이전 예제의 `Console.WriteLine`에 대한 호출을 수정하여 날짜 및 가격 필드의 형식 지정자를 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-149">Modify the call to `Console.WriteLine` from the previous example to include the format specifier for the date and price fields as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```
    
<span data-ttu-id="63e3e-150">콜론과 형식 문자열을 사용하여 보간된 식에 따라 형식 문자열을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-150">You specify a format string by following the interpolated expression with a colon and the format string.</span></span> <span data-ttu-id="63e3e-151">"d"는 간단한 날짜 형식을 나타내는 [표준 날짜 및 시간 형식 문자열](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-151">"d" is a [standard date and time format string](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="63e3e-152">"C2"는 소수점 뒤 두 자릿수를 포함하는 통화 값으로 숫자를 나타내는 [표준 숫자 형식 문자열](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-152">"C2" is a  [standard numeric format string](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="63e3e-153">.NET 표준 라이브러리의 많은 형식은 미리 정의된 형식 문자열 집합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-153">A number of types in the .NET Standard libraries support a predefined set of format strings.</span></span> <span data-ttu-id="63e3e-154">여기에는 모든 숫자 형식과 날짜 및 시간 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-154">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="63e3e-155">형식 문자열을 지원하는 형식의 전체 목록을 보려면 [.NET의 서식 지정 형식](../../standard/base-types/formatting-types.md) 문서의 [형식 문자열 및 .NET 클래스 라이브러리 형식](../../standard/base-types/formatting-types.md#stringRef)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63e3e-155">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../standard/base-types/formatting-types.md#stringRef) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span> <span data-ttu-id="63e3e-156">모든 형식에서 형식 문자열 집합을 지원할 수 있으며, 기존 형식에 대한 사용자 지정 서식을 제공하는 사용자 지정 서식 확장을 개발할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-156">Any type can support a set of format strings, and you can also develop custom formatting extensions that provide custom formatting for existing types.</span></span> <span data-ttu-id="63e3e-157"><xref:System.ICustomFormatter> 구현을 제공한 사용자 지정 서식에 대한 자세한 내용은 [.NET의 서식 지정 형식](../../standard/base-types/formatting-types.md) 문서의 [ICustomFormatter를 사용한 사용자 지정 서식 지정](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63e3e-157">For information on custom formatting by providing an <xref:System.ICustomFormatter> implementation, see [Custom Formatting with ICustomFormatter](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="63e3e-158">텍스트 편집기에서 형식 문자열을 수정하고, 변경할 때마다 프로그램을 다시 실행하여 날짜 및 시간의 서식과 숫자 값에 미치는 영향을 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="63e3e-158">Try modifying the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="63e3e-159">`{date:d}`의 "d"를 "t"(짧은 시간 형식 표시), "y"(연도 및 월 표시) 및 "yyyy"(연도를 4자리 숫자로 표시)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-159">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="63e3e-160">`{price:C2}`의 "C2"를 "e"(지수 표기) 및 "F3"(소수점 뒤 세 자릿수의 숫자 값)으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-160">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="63e3e-161">서식을 제어하는 것 외에도, 보간된 식에서 반환된 문자열의 필드 너비와 문자열 맞춤을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-161">In addition to controlling formatting, you can also control the field width and alignment of the strings returned by an interpolated expression.</span></span> <span data-ttu-id="63e3e-162">다음 섹션에서 이 작업을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-162">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a><span data-ttu-id="63e3e-163">필드 너비와 보간된 식의 맞춤을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-163">Control the field width and alignment of interpolated expressions</span></span>

<span data-ttu-id="63e3e-164">일반적으로 보간된 식에서 반환된 문자열은 결과 문자열에 포함되며 선행 또는 후행 공백이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-164">Ordinarily, when the string returned by an interpolated expression is included in a result string, it has no leading or trailing spaces.</span></span> <span data-ttu-id="63e3e-165">특히 데이터 집합을 사용하여 작업하는 경우에는 보간된 식을 사용하여 필드 너비와 해당 맞춤을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-165">Particularly for instances in which you are working with a set of data, interpolated expressions let you specify a field width and its alignment.</span></span> <span data-ttu-id="63e3e-166">이것을 확인하려면 텍스트 편집기에서 모든 코드를 다음 코드로 바꾼 후 `console run`을 입력하여 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-166">To see this, replace all the code in your text editor with the following code, then type `console run` to execute the program:</span></span>
    
```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>();
      titles.Add("Doyle, Arthur Conan", "Hound of the Baskervilles, The");
      titles.Add("London, Jack", "Call of the Wild, The");
      titles.Add("Shakespeare, William", "Tempest, The");

      Console.WriteLine("Author and Title List");
      Console.WriteLine($"\n{"Author",-25}    {"Title",30}\n");
      foreach (var title in titles)
         Console.WriteLine($"{title.Key,-25}     {title.Value,30}");
   }
}
```
    
<span data-ttu-id="63e3e-167">작성자의 이름은 왼쪽 맞춤되며 이들이 작성한 제목은 오른쪽 맞춤됩니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-167">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="63e3e-168">식 뒤에 쉼표(",")를 추가하고 필더 너비를 지정하여 맞춤을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-168">You specify the alignment by adding a comma (",") after the expression and designating the field width.</span></span> <span data-ttu-id="63e3e-169">필드 너비가 양수이면 필드는 오른쪽 맞춤입니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-169">If the field width is a positive number, the field is right-aligned:</span></span>

```text
{expression, width}
```

<span data-ttu-id="63e3e-170">필드 너비가 음수이면 필드는 왼쪽 맞춤입니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-170">If the field width is a negative number, the field is left-aligned:</span></span>

```text
{expression, -width}
```

<span data-ttu-id="63e3e-171">다음 코드처럼 `{"Author",-25}` 및 `{title.Key,-25}` 보간된 식에서 음수 기호를 제거하고 예제를 다시 실행해 보세요.</span><span class="sxs-lookup"><span data-stu-id="63e3e-171">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` interpolated expressions and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"\n{"Author",25}    {"Title",30}\n");
foreach (var title in titles)
   Console.WriteLine($"{title.Key,25}     {title.Value,30}");
```

<span data-ttu-id="63e3e-172">이때 작성자 정보는 오른쪽 맞춤입니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-172">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="63e3e-173">필드 너비 및 형식 문자열을 단일 보간된 식으로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-173">You can combine a field width and a format string in a single interpolated expression.</span></span> <span data-ttu-id="63e3e-174">필드 너비가 먼저 나오고 그 다음으로, 콜론 및 형식 문자열이 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-174">The field width comes first, followed by a colon and the format string.</span></span> <span data-ttu-id="63e3e-175">`Main` 메서드 내에 있는 모든 코드를 다음 코드로 바꾸면, 필드 너비가 정의된 세 가지 형식 지정된 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-175">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="63e3e-176">그런 다음 `dotnet run` 명령을 입력하여 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-176">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"{DateTime.Now,-20:d} Hour {DateTime.Now,-10:HH} {1063.342,15:N2} feet");
```
<span data-ttu-id="63e3e-177">다음과 같은 출력을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-177">The output looks something like the following:</span></span>

```console
1/11/2018            Hour 09                1,063.34 feet
```

<span data-ttu-id="63e3e-178">보간된 문자열 빠른 시작을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-178">You've completed the interpolated strings quickstart.</span></span> 
    
<span data-ttu-id="63e3e-179">자체 개발 환경에서 [배열 및 컬렉션](arrays-and-collections.md) 빠른 시작을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-179">You can continue with the [Arrays and collections](arrays-and-collections.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="63e3e-180">C# 참조의 [보간된 문자열](../language-reference/keywords/interpolated-strings.md) 항목에서 보간된 문자열로 작업하는 방법에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e3e-180">You can learn more about working with interpolated strings in the [Interpolated Strings](../language-reference/keywords/interpolated-strings.md) topic in the C# Reference.</span></span>

