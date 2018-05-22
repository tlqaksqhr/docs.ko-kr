---
title: 문자열 보간 자습서 - C# 로컬 빠른 시작
description: 이 빠른 시작에서는 C# 문자열 보간 기능을 사용하여 더 큰 문자열에 형식이 지정된 식을 포함시키는 방법을 보여줍니다.
author: rpetrusha
ms.author: ronpet
ms.date: 04/14/2018
ms.custom: mvc
ms.openlocfilehash: 314626e276f50178e2855b8c8a1edc104546d574
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
---
# <a name="string-interpolation"></a><span data-ttu-id="f3837-103">문자열 보간</span><span class="sxs-lookup"><span data-stu-id="f3837-103">String interpolation</span></span>

<span data-ttu-id="f3837-104">이 빠른 시작에서는 C# [문자열 보간](../language-reference/tokens/interpolated.md)을 사용하여 단일 결과 문자열에 값을 삽입하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-104">This quickstart teaches you how to use C# [string interpolation](../language-reference/tokens/interpolated.md) to insert values into a single result string.</span></span> <span data-ttu-id="f3837-105">C# 코드를 작성하고 컴파일 및 실행 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="f3837-106">이 빠른 시작은 문자열에 값을 삽입하고, 이러한 값을 다양한 방식으로 형식화하는 방법을 보여주는 일련의 단원으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-106">The quickstart contains a series of lessons that show you how to insert values into a string and format those values in different ways.</span></span>

<span data-ttu-id="f3837-107">이 빠른 시작에서는 개발에 사용할 수 있는 컴퓨터가 있다고 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-107">This quickstart expects that you have a machine you can use for development.</span></span> <span data-ttu-id="f3837-108">.NET 항목 [Get Started in 10 minutes](https://www.microsoft.com/net/core)(10분 안에 시작)에는 Mac, PC 또는 Linux의 로컬 개발 환경 설정에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-108">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="f3837-109">사용할 명령에 대한 간단한 개요는 [로컬 빠른 시작 소개](local-environment.md)에 나와 있으며, 이 소개에는 자세한 정보에 대한 링크도 함께 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-109">A quick overview of the commands you'll use is in the [introduction to the local quickstarts](local-environment.md) with links to more details.</span></span> <span data-ttu-id="f3837-110">브라우저에서 빠른 시작의 [대화형 버전](interpolated-strings.yml)을 완료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-110">You also can complete the [interactive version](interpolated-strings.yml) of this quickstart in your browser.</span></span>

## <a name="create-an-interpolated-string"></a><span data-ttu-id="f3837-111">보간된 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="f3837-111">Create an interpolated string</span></span>

<span data-ttu-id="f3837-112">**interpolated**라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-112">Create a directory named **interpolated**.</span></span> <span data-ttu-id="f3837-113">현재 디렉터리로 만들고 콘솔 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-113">Make it the current directory and run the following command from a console window:</span></span>

```console
dotnet new console
```

<span data-ttu-id="f3837-114">이 명령은 현재 디렉터리에 새 .NET Core 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-114">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="f3837-115">원하는 편집기에서 **Program.cs**를 열고 `Console.WriteLine("Hello World!");` 줄을 다음 코드로 바꿉니다. 여기서 `<name>`을 사용자 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-115">Open **Program.cs** in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```

<span data-ttu-id="f3837-116">콘솔 창에 `dotnet run`을 입력하여 이 코드를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-116">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="f3837-117">프로그램을 실행하면 인사말에 사용자 이름이 포함된 단일 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-117">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="f3837-118"><xref:System.Console.WriteLine%2A> 메서드 호출에 포함된 문자열은 *보간된 문자열*입니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-118">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string*.</span></span> <span data-ttu-id="f3837-119">이는 포함 코드가 들어있는 문자열에서 단일 문자열(*결과 문자열*이라고 함)을 생성할 수 있게 해주는 일종의 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-119">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="f3837-120">보간된 문자열은 문자열에 값을 삽입하거나 문자열을 연결(함께 조인)하는 데 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-120">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span>

<span data-ttu-id="f3837-121">다음 간단한 예제에서는 모든 보간된 문자열이 포함해야 하는 두 가지 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-121">This simple example contains the two elements that every interpolated string must have:</span></span>

- <span data-ttu-id="f3837-122">`$` 문자로 시작한 후 여는 따옴표 문자가 다음에 나오는 문자열 리터럴.</span><span class="sxs-lookup"><span data-stu-id="f3837-122">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="f3837-123">`$` 기호와 따옴표 문자 사이에는 공백이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-123">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="f3837-124">(공백을 포함하면 어떻게 되는지 확인하려면 `$` 문자 뒤에 공백을 삽입하고 파일을 저장한 후 콘솔 창에 `dotnet run`을 입력하여 프로그램을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-124">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="f3837-125">C# 컴파일러가 "오류 CS1056: 예기치 않은 문자 '$'"라는 오류 메시지를 표시합니다.)</span><span class="sxs-lookup"><span data-stu-id="f3837-125">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span>

- <span data-ttu-id="f3837-126">하나 이상의 *보간된 식*.</span><span class="sxs-lookup"><span data-stu-id="f3837-126">One or more *interpolated expressions*.</span></span> <span data-ttu-id="f3837-127">보간된 식은 열기 및 닫기 중괄호(`{` 및 `}`)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-127">An interpolated expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="f3837-128">중괄호 안에 값을 반환(`null` 포함)하는 C# 식을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-128">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span>

<span data-ttu-id="f3837-129">몇 가지 다른 데이터 형식을 포함하는 문자열 보간 예제를 더 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-129">Let's try a few more string interpolation examples with some other data types.</span></span>

## <a name="include-different-data-types"></a><span data-ttu-id="f3837-130">다양한 데이터 형식 포함</span><span class="sxs-lookup"><span data-stu-id="f3837-130">Include different data types</span></span>

<span data-ttu-id="f3837-131">이전 섹션에서는 한 문자열을 다른 문자열 내에 삽입하는 데 문자열 보간을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-131">In the previous section, you used string interpolation to insert one string inside of another.</span></span> <span data-ttu-id="f3837-132">보간된 식의 결과는 모든 데이터 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-132">The result of an interpolated expression can be of any data type, though.</span></span> <span data-ttu-id="f3837-133">보간된 문자열에 다양한 데이터 형식의 값을 포함시켜 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-133">Let's include values of various data types in an interpolated string.</span></span>

<span data-ttu-id="f3837-134">다음 예제에서는 먼저 `Name` [속성](../properties.md) 및 `ToString` 메서드가 있는 사용자 지정 데이터 형식 `Vegetable`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-134">In the following example, first, we define a custom data type `Vegetable` that has the `Name` [property](../properties.md) and the `ToString` method.</span></span> <span data-ttu-id="f3837-135">클라이언트 코드는 해당 메서드를 사용하여 `Vegetable` 인스턴스의 문자열 표현을 구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-135">The client code can use that method to get the string representation of a `Vegetable` instance.</span></span> <span data-ttu-id="f3837-136">예제에서 `Vegetable.ToString` 메서드는 `Vegetable` 생성자에서 초기화된 `Name` 속성의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-136">In the example the `Vegetable.ToString` method returns the value of the `Name` property that is initialized at the `Vegetable` constructor:</span></span>

```csharp
public Vegetable(string name) => Name = name;
```

<span data-ttu-id="f3837-137">`new` 키워드를 사용하고 생성자 `Vegetable`에 대한 name 매개 변수를 제공하여 `Vegetable` 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-137">We create an instance of the `Vegetable` type by using `new` keyword and providing a name parameter for the constructor `Vegetable`:</span></span>

```csharp
var item = new Vegetable("eggplant");
```

<span data-ttu-id="f3837-138">마지막으로 <xref:System.DateTime> 값, <xref:System.Decimal> 값 및 `Unit` [열거형](../programming-guide/enumeration-types.md) 값을 포함하는 보간된 문자열에 `item` 변수를 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-138">Finally, we include the `item` variable into an interpolated string that also contains a <xref:System.DateTime> value, a <xref:System.Decimal> value, and a `Unit` [enumeration](../programming-guide/enumeration-types.md) value.</span></span> <span data-ttu-id="f3837-139">편집기에서 모든 C# 코드를 다음 코드로 바꾼 후 `dotnet run` 명령을 사용하여 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-139">Replace all of the C# code in your editor with the following code, and then use the `dotnet run` command to run it:</span></span>

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Program
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

<span data-ttu-id="f3837-140">보간된 문자열의 보간된 식 `item`은 결과 문자열에 "eggplant"라는 텍스트로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-140">Note that the interpolated expression `item` in the interpolated string resolves to the text "eggplant" in the result string.</span></span> <span data-ttu-id="f3837-141">이것은 식 결과의 형식이 문자열이 아닌 경우 다음과 같은 방식으로 결과가 문자열로 확인되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-141">That's because, when the type of the expression result is not a string, the result is resolved to a string in the following way:</span></span>

- <span data-ttu-id="f3837-142">보간된 식이 `null`로 계산되고 빈 문자열("" 또는 <xref:System.String.Empty?displayProperty=nameWithType>)이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-142">If the interpolated expression evaluates to `null`, an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>) is used.</span></span>

- <span data-ttu-id="f3837-143">보간된 식이 `null`로 계산되지 않고 결과 형식의 `ToString` 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-143">If the interpolated expression doesn't evaluate to `null`, typically the `ToString` method of the result type is called.</span></span> <span data-ttu-id="f3837-144">이것은 `Vegetable.ToString` 메서드의 구현을 업데이트하여 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-144">You can test this by updating the implementation of the `Vegetable.ToString` method.</span></span> <span data-ttu-id="f3837-145">모든 C# 데이터 형식에는 이 메서드가 구현되어 있기 때문에 `ToString` 메서드를 구현하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-145">You might even not implement `ToString` method since every C# data type has some implementation of this method.</span></span> <span data-ttu-id="f3837-146">이것을 테스트하려면 예제에서 `Vegetable.ToString` 메서드 정의를 주석으로 처리합니다. (이렇게 하려면, 그 앞에 주석 기호 즉, `//`를 추가합니다.)</span><span class="sxs-lookup"><span data-stu-id="f3837-146">To test that, comment out the definition of the `Vegetable.ToString` method in the example (to do that, put a comment symbol `//` in front of it).</span></span> <span data-ttu-id="f3837-147">출력에서 "eggplant" 문자열은 정규화된 형식 이름(이 예제의 경우 "Vegetable")으로 바뀌며 이것이 <xref:System.Object.ToString?displayProperty=nameWithType> 메서드의 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-147">In the output, the string "eggplant" is replaced by the fully qualified type name ("Vegetable" in this example), which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f3837-148">열거형 형식에 대한 `ToString` 메서드의 기본 동작은 열거형을 정의하는 데 사용된 값의 문자열 표현을 반환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-148">Default behavior of the `ToString` method for an enumeration type is to return the string representation of a value used at the definition of the enumeration.</span></span>

<span data-ttu-id="f3837-149">이 예제의 출력에서 날짜는 매우 정확하며(eggplant 가격은 초마다 변경되지 않음), 가격 값은 통화 단위를 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-149">In the output from this example, the date is too precise (the price of eggplant doesn't change every second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="f3837-150">다음 섹션에서는 식 결과에 대한 문자열 표현의 형식을 제어하여 해당 문제를 해결하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-150">In the next section, you'll learn how to fix those issues by controlling the format of string representations of the expression results.</span></span>

## <a name="control-the-formatting-of-interpolated-expressions"></a><span data-ttu-id="f3837-151">보간된 식의 서식 제어</span><span class="sxs-lookup"><span data-stu-id="f3837-151">Control the formatting of interpolated expressions</span></span>

<span data-ttu-id="f3837-152">이전 섹션에서는 형식이 잘못 지정된 두 개의 문자열을 결과 문자열에 삽입했습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-152">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="f3837-153">하나는 날짜만 적절한 날짜 및 시간 값이었습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-153">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="f3837-154">두 번째는 통화 단위를 나타내지 않는 가격이었습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-154">The second was a price that didn't indicate its unit of currency.</span></span> <span data-ttu-id="f3837-155">두 가지 문제는 쉽게 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-155">Both issues are easy to address.</span></span> <span data-ttu-id="f3837-156">문자열 보간을 통해 특정 유형의 형식을 제어하는 *형식 문자열*을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-156">String interpolation lets you specify *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="f3837-157">다음 줄에 표시된 것처럼 이전 예제의 `Console.WriteLine`에 대한 호출을 수정하여 날짜 및 가격 식의 형식 문자열을 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-157">Modify the call to `Console.WriteLine` from the previous example to include the format strings for the date and price expressions as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```

<span data-ttu-id="f3837-158">콜론(":")과 형식 문자열을 사용하여 보간된 식에 따라 형식 문자열을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-158">You specify a format string by following the interpolated expression with a colon (":") and the format string.</span></span> <span data-ttu-id="f3837-159">"d"는 간단한 날짜 형식을 나타내는 [표준 날짜 및 시간 형식 문자열](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-159">"d" is a [standard date and time format string](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="f3837-160">"C2"는 소수점 뒤 두 자릿수를 포함하는 통화 값으로 숫자를 나타내는 [표준 숫자 형식 문자열](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-160">"C2" is a  [standard numeric format string](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="f3837-161">.NET 라이브러리의 많은 형식은 미리 정의된 형식 문자열 집합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-161">A number of types in the .NET libraries support a predefined set of format strings.</span></span> <span data-ttu-id="f3837-162">여기에는 모든 숫자 형식과 날짜 및 시간 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-162">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="f3837-163">형식 문자열을 지원하는 형식의 전체 목록을 보려면 [.NET의 서식 지정 형식](../../standard/base-types/formatting-types.md) 문서의 [형식 문자열 및 .NET 클래스 라이브러리 형식](../../standard/base-types/formatting-types.md#stringRef)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3837-163">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../standard/base-types/formatting-types.md#stringRef) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="f3837-164">텍스트 편집기에서 형식 문자열을 수정하고, 변경할 때마다 프로그램을 다시 실행하여 날짜 및 시간의 서식과 숫자 값에 미치는 영향을 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="f3837-164">Try modifying the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="f3837-165">`{date:d}`의 "d"를 "t"(짧은 시간 형식 표시), "y"(연도 및 월 표시) 및 "yyyy"(연도를 4자리 숫자로 표시)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-165">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="f3837-166">`{price:C2}`의 "C2"를 "e"(지수 표기) 및 "F3"(소수점 뒤 세 자릿수의 숫자 값)으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-166">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="f3837-167">형식을 제어하는 것 외에도, 결과 문자열에 포함된 형식이 지정된 문자열의 필드 너비와 맞춤을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-167">In addition to controlling formatting, you can also control the field width and alignment of the formatted strings that are included in the result string.</span></span> <span data-ttu-id="f3837-168">다음 섹션에서 이 작업을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-168">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a><span data-ttu-id="f3837-169">필드 너비와 보간된 식의 맞춤을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-169">Control the field width and alignment of interpolated expressions</span></span>

<span data-ttu-id="f3837-170">일반적으로 보간된 식의 결과가 문자열로 형식이 지정되면 해당 문자열은 결과 문자열에 선행 또는 후행 공백 없이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-170">Ordinarily, when the result of an interpolated expression is formatted to string, that string is included in a result string without leading or trailing spaces.</span></span> <span data-ttu-id="f3837-171">특히 데이터 집합을 가지고 작업하는 경우 필드 너비와 텍스트 맞춤을 제어할 수 있으면 보다 읽기 쉬운 출력을 생성하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-171">Particularly when you work with a set of data, being able to control a field width and text alignment helps to produce a more readable output.</span></span> <span data-ttu-id="f3837-172">이것을 확인하려면 텍스트 편집기에서 모든 코드를 다음 코드로 바꾼 후 `dotnet run`을 입력하여 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-172">To see this, replace all the code in your text editor with the following code, then type `dotnet run` to execute the program:</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>()
      {
          ["Doyle, Arthur Conan"] = "Hound of the Baskervilles, The",
          ["London, Jack"] = "Call of the Wild, The",
          ["Shakespeare, William"] = "Tempest, The"
      };

      Console.WriteLine("Author and Title List");
      Console.WriteLine();
      Console.WriteLine($"|{"Author",-25}|{"Title",30}|");
      foreach (var title in titles)
         Console.WriteLine($"|{title.Key,-25}|{title.Value,30}|");
   }
}
```

<span data-ttu-id="f3837-173">작성자의 이름은 왼쪽 맞춤되며 이들이 작성한 제목은 오른쪽 맞춤됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-173">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="f3837-174">보간된 식 뒤에 쉼표(",")를 추가하고 *최소* 필드 너비를 지정하여 맞춤을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-174">You specify the alignment by adding a comma (",") after an interpolated expression and designating the *minimum* field width.</span></span> <span data-ttu-id="f3837-175">지정한 값이 양수이면 필드는 오른쪽 맞춤입니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-175">If the specified value is a positive number, the field is right-aligned.</span></span> <span data-ttu-id="f3837-176">음수이면 필드는 왼쪽 맞춤입니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-176">If it is a negative number, the field is left-aligned.</span></span>

<span data-ttu-id="f3837-177">다음 코드처럼 `{"Author",-25}` 및 `{title.Key,-25}` 코드에서 음수 기호를 제거하고 예제를 다시 실행해 보세요.</span><span class="sxs-lookup"><span data-stu-id="f3837-177">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` code and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"|{"Author",25}|{"Title",30}|");
foreach (var title in titles)
   Console.WriteLine($"|{title.Key,25}|{title.Value,30}|");
```

<span data-ttu-id="f3837-178">이때 작성자 정보는 오른쪽 맞춤입니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-178">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="f3837-179">하나의 보간된 식에 대해 맞춤 지정자 및 형식 문자열을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-179">You can combine an alignment specifier and a format string for a single interpolated expression.</span></span> <span data-ttu-id="f3837-180">이렇게 하려면 먼저 맞춤을 지정하고 콜론과 형식 문자열을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-180">To do that, specify the alignment first, followed by a colon and the format string.</span></span> <span data-ttu-id="f3837-181">`Main` 메서드 내에 있는 모든 코드를 다음 코드로 바꾸면, 필드 너비가 정의된 세 가지 형식 지정된 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-181">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="f3837-182">그런 다음 `dotnet run` 명령을 입력하여 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-182">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"[{DateTime.Now,-20:d}] Hour [{DateTime.Now,-10:HH}] [{1063.342,15:N2}] feet");
```

<span data-ttu-id="f3837-183">다음과 같은 출력을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-183">The output looks something like the following:</span></span>

```console
[04/14/2018          ] Hour [16        ] [       1,063.34] feet
```

<span data-ttu-id="f3837-184">문자 보간 빠른 시작을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-184">You've completed the string interpolation quickstart.</span></span>

<span data-ttu-id="f3837-185">자체 개발 환경에서 [목록 컬렉션](arrays-and-collections.md) 빠른 시작을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3837-185">You can continue with the [List collection](arrays-and-collections.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="f3837-186">자세한 내용은 [문자열 보간](../language-reference/tokens/interpolated.md) 항목 및 [C#에서 문자열 보간](../tutorials/string-interpolation.md) 자습서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3837-186">For more information, see the [String interpolation](../language-reference/tokens/interpolated.md) topic and the [String interpolation in C#](../tutorials/string-interpolation.md) tutorial.</span></span>
