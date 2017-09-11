---
title: "서식 지정 형식"
description: "서식 지정 형식"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: cf497639-9f91-45cb-836f-998d1cea2f43
ms.translationtype: Human Translation
ms.sourcegitcommit: b967d8e55347f44a012e4ad8e916440ae228c8ec
ms.openlocfilehash: e9b8ad13a48dd43236769b130d6f8a75b7b023ca
ms.contentlocale: ko-kr
ms.lasthandoff: 03/10/2017

---

# <a name="formatting-types"></a><span data-ttu-id="96132-104">서식 지정 형식</span><span class="sxs-lookup"><span data-stu-id="96132-104">Formatting types</span></span>

<span data-ttu-id="96132-105">형식 지정은 대개 결과 문자열을 사용자에게 표시하거나 deserialize하여 원본 데이터 형식으로 복원하기 위해 클래스, 구조체 또는 열거형 값의 인스턴스를 해당 문자열 표현으로 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="96132-105">Formatting is the process of converting an instance of a class, structure, or enumeration value to its string representation, often so that the resulting string can be displayed to users or deserialized to restore the original data type.</span></span> <span data-ttu-id="96132-106">이 변환 프로세스에는 다음과 같은 여러 가지 문제점이 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-106">This conversion can pose a number of challenges:</span></span>

* <span data-ttu-id="96132-107">내부적으로 값을 저장하는 방식에 사용자가 원하는 표시 방식이 반영되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-107">The way that values are stored internally does not necessarily reflect the way that users want to view them.</span></span> <span data-ttu-id="96132-108">예를 들어 전화 번호가 사용자에게 친숙하지 않은 **8009999999** 형식으로 저장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-108">For example, a telephone number might be stored in the form **8009999999**, which is not user-friendly.</span></span> <span data-ttu-id="96132-109">이 전화 번호는 **800-999-9999**로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-109">It should instead be displayed as **800-999-9999**.</span></span> <span data-ttu-id="96132-110">이러한 방식으로 숫자의 서식을 지정하는 예제는 [사용자 지정 서식 문자열](#custom-format-strings) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-110">See the [Custom format strings](#custom-format-strings) section for an example that formats a number in this way.</span></span> 

* <span data-ttu-id="96132-111">개체를 문자열 표현으로 변환하는 과정이 명확하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-111">Sometimes the conversion of an object to its string representation is not intuitive.</span></span> <span data-ttu-id="96132-112">예를 들어 **Temperature** 또는 **Person** 개체의 문자열 표현이 어떻게 표시될지 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-112">For example, it is not clear how the string representation of a **Temperature** object or a **Person** object should appear.</span></span> <span data-ttu-id="96132-113">다양한 방식으로 **Temperature** 개체의 서식을 지정하는 예제는 [표준 서식 문자열](#standard-format-strings) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-113">For an example that formats a **Temperature** object in a variety of ways, see the [Standard format strings](#standard-format-strings) section.</span></span>

* <span data-ttu-id="96132-114">값에 문화권별 형식 지정이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-114">Values often require culture-sensitive formatting.</span></span> <span data-ttu-id="96132-115">예를 들어, 숫자를 사용하여 통화 값을 나타내는 응용 프로그램에서는 숫자 문자열에 현재 문화권의 통화 기호, 그룹 구분 기호(대부분의 경우 1000 단위 구분 기호임) 및 소수점 기호가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-115">For example, in an application that uses numbers to reflect monetary values, numeric strings should include the current culture’s currency symbol, group separator (which, in most cultures, is the thousands separator), and decimal symbol.</span></span> <span data-ttu-id="96132-116">예제는 [서식 공급자 및 IFormatProvider 인터페이스를 사용하여 문화권 구분 서식 지정](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-116">For an example, see the [Culture-sensitive formatting with format providers and the IFormatProvider interface](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface) section.</span></span> 

* <span data-ttu-id="96132-117">응용 프로그램에서 같은 값을 여러 가지 방법으로 표시해야 하는 경우도 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-117">An application may have to display the same value in different ways.</span></span> <span data-ttu-id="96132-118">예를 들어, 응용 프로그램에서 해당 이름의 문자열 표현을 표시하거나 해당 내부 값을 표시하여 열거형 멤버를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-118">For example, an application may represent an enumeration member by displaying a string representation of its name or by displaying its underlying value.</span></span> <span data-ttu-id="96132-119">다양한 방식으로 [DayOfWeek](xref:System.DayOfWeek) 열거형 멤버의 형식을 지정하는 예제는 [표준 서식 문자열](#standard-format-strings) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-119">For an example that formats a member of the [DayOfWeek](xref:System.DayOfWeek) enumeration in different ways, see the [Standard format strings](#standard-format-strings) section.</span></span>

<span data-ttu-id="96132-120">.NET에서는 개발자가 이러한 요구 사항을 처리할 수 있는 다양한 형식 지정을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-120">.NET provides rich formatting support that enables developers to address these requirements.</span></span> 

> [!NOTE]
> <span data-ttu-id="96132-121">형식 지정은 형식의 값을 문자열 표현으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-121">Formatting converts the value of a type into a string representation.</span></span> <span data-ttu-id="96132-122">구문 분석은 형식 지정과 반대 과정으로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-122">Parsing is the inverse of formatting.</span></span> <span data-ttu-id="96132-123">구문 분석 작업은 해당 문자열 표현에서 데이터 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96132-123">A parsing operation creates an instance of a data type from its string representation.</span></span> <span data-ttu-id="96132-124">문자열을 다른 데이터 형식으로 변환하는 방법에 대한 자세한 내용은 [문자열 구문 분석](parsing-strings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-124">For information about converting strings to other data types, see [Parsing strings](parsing-strings.md).</span></span>

<span data-ttu-id="96132-125">이 개요는 다음과 같은 단원으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-125">This overview contains the following sections:</span></span>

* [<span data-ttu-id="96132-126">.NET의 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-126">Formatting in .NET</span></span>](#formatting-in-net)

* [<span data-ttu-id="96132-127">ToString 메서드를 사용한 기본 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-127">Default formatting using the ToString method</span></span>](#default-formatting-using-the-tostring-method)

* [<span data-ttu-id="96132-128">ToString 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="96132-128">Overriding the ToString method</span></span>](#overriding-the-tostring-method)

* [<span data-ttu-id="96132-129">ToString 메서드 및 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-129">The ToString method and format strings</span></span>](#the-tostring-method-and-format-strings)

    * [<span data-ttu-id="96132-130">표준 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-130">Standard format strings</span></span>](#standard-format-strings)
    
    * [<span data-ttu-id="96132-131">사용자 지정 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-131">Custom format strings</span></span>](#custom-format-strings)
    
    * [<span data-ttu-id="96132-132">서식 문자열 및 .NET 형식</span><span class="sxs-lookup"><span data-stu-id="96132-132">Format strings and .NET types</span></span>](#format-strings-and-net-types)
    
* [<span data-ttu-id="96132-133">서식 공급자 및 IFormatProvider 인터페이스를 사용하여 문화권 구분 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-133">Culture-sensitive formatting with format providers and the IFormatProvider interface</span></span>](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface)

    * [<span data-ttu-id="96132-134">숫자 값의 문화권 구분 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-134">Culture-sensitive formatting of numeric values</span></span>](#culture-sensitive-formatting-of-numeric-values)
    
    * [<span data-ttu-id="96132-135">날짜 및 시간 값의 문화권 구분 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-135">Culture-sensitive formatting of date and time values</span></span>](#culture-sensitive-formatting-of-date-and-time-values)
    
* [<span data-ttu-id="96132-136">IFormattable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="96132-136">The IFormattable interface</span></span>](#the-iformattable-interface)

* [<span data-ttu-id="96132-137">복합 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-137">Composite formatting</span></span>](#composite-formatting)

* [<span data-ttu-id="96132-138">ICustomFormatter를 사용한 사용자 지정 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-138">Custom formatting with ICustomFormatter</span></span>](#custom-formatting-with-icustomformatter)

* [<span data-ttu-id="96132-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="96132-139">Related topics</span></span>](#related-topics)

* [<span data-ttu-id="96132-140">참조</span><span class="sxs-lookup"><span data-stu-id="96132-140">Reference</span></span>](#reference)

## <a name="formatting-in-net"></a><span data-ttu-id="96132-141">.NET의 형식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-141">Formatting in .NET</span></span>

<span data-ttu-id="96132-142">서식 지정의 기본 메커니즘은 [Object.ToString](xref:System.Object.ToString) 메서드의 기본 구현으로, 이 항목의 뒷부분에 있는 [ToString 메서드를 사용한 기본 서식 지정](#default-formatting-using-the-tostring-method) 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-142">The basic mechanism for formatting is the default implementation of the [Object.ToString](xref:System.Object.ToString) method, which is discussed in the [Default formatting using the ToString method](#default-formatting-using-the-tostring-method) section later in this topic.</span></span> <span data-ttu-id="96132-143">그러나 .NET에서는 기본 형식 지정 지원을 수정하고 확장할 수 있는 여러 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-143">However, .NET provides several ways to modify and extend its default formatting support.</span></span> <span data-ttu-id="96132-144">이러한 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-144">These include the following:</span></span>

* <span data-ttu-id="96132-145">[Object.ToString](xref:System.Object.ToString) 메서드를 재정의하여 개체 값의 사용자 지정 문자열 표현을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-145">Overriding the [Object.ToString](xref:System.Object.ToString) method to define a custom string representation of an object’s value.</span></span> <span data-ttu-id="96132-146">자세한 내용은 이 항목의 뒷부분에 있는 [ToString 메서드 재정의](#overriding-the-tostring-method) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-146">For more information, see the [Overriding the ToString method](#overriding-the-tostring-method) section later in this topic.</span></span>

* <span data-ttu-id="96132-147">개체의 값에 대한 문자열 표현에서 여러 형식을 사용할 수 있도록 형식 지정자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-147">Defining format specifiers that enable the string representation of an object’s value to take multiple forms.</span></span> <span data-ttu-id="96132-148">예를 들어, 다음 문의 "X" 형식 지정자는 정수를 16진수 값의 문자열 표현으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-148">For example, the "X" format specifier in the following statement converts an integer to the string representation of a hexadecimal value.</span></span>

  ```csharp
  int integerValue = 60312;
  Console.WriteLine(integerValue.ToString("X"));   // Displays EB98.
  ```

  ```vb
  Dim integerValue As Integer = 60312
  Console.WriteLine(integerValue.ToString("X"))   ' Displays EB98.
  ```
  
  <span data-ttu-id="96132-149">서식 지정자에 대한 자세한 내용은 [ToString 메서드 및 서식 문자열](#the-tostring-method-and-format-strings) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-149">For more information about format specifiers, see the [The ToString method and format strings](#the-tostring-method-and-format-strings) section.</span></span>
  
* <span data-ttu-id="96132-150">형식 공급자를 사용하여 특정 문화권의 형식 지정 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-150">Using format providers to take advantage of the formatting conventions of a specific culture.</span></span> <span data-ttu-id="96132-151">예를 들어, 다음 문은 en-US 문화권의 형식 지정 규칙을 사용하여 통화 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-151">For example, the following statement displays a currency value by using the formatting conventions of the en-US culture.</span></span> 

  ```csharp
  double cost = 1632.54; 
  Console.WriteLine(cost.ToString("C", 
                  new System.Globalization.CultureInfo("en-US")));   
  // The example displays the following output:
  //       $1,632.54
  ```

  ```vb
  Dim cost As Double = 1632.54
  Console.WriteLine(cost.ToString("C", New System.Globalization.CultureInfo("en-US")))
  ' The example displays the following output:
  '       $1,632.54
  ```
  
  <span data-ttu-id="96132-152">서식 공급자를 사용하여 서식을 지정하는 방법에 대한 자세한 내용은 [서식 공급자 및 IFormatProvider 인터페이스를 사용하여 문화권 구분 서식 지정](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-152">For more information about formatting with format providers, see the [Culture-sensitive formatting with format providers and the IFormatProvider interface](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface) section.</span></span>  
  
* <span data-ttu-id="96132-153">[IFormattable](xref:System.IFormattable) 인터페이스를 구현하여 [Convert](xref:System.Convert) 클래스를 사용한 문자열 변환과 복합 형식 지정을 둘 다 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-153">Implementing the [IFormattable](xref:System.IFormattable) interface to support both string conversion with the [Convert](xref:System.Convert) class and composite formatting.</span></span> <span data-ttu-id="96132-154">자세한 내용은 [IFormattable 인터페이스](#the-iformattable-interface) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-154">For more information, see the [The IFormattable interface](#the-iformattable-interface) section.</span></span>

* <span data-ttu-id="96132-155">복합 형식 지정을 사용하여 값의 문자열 표현을 더 큰 문자열에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-155">Using composite formatting to embed the string representation of a value in a larger string.</span></span> <span data-ttu-id="96132-156">자세한 내용은 [복합 서식 지정](#composite-formatting) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-156">For more information, see the [Composite formatting](#composite-formatting) section.</span></span>

* <span data-ttu-id="96132-157">[ICustomFormatter](xref:System.ICustomFormatter) 및 [IFormatProvider](xref:System.IFormatProvider)를 구현하여 완벽한 사용자 지정 형식 지정 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-157">Implementing [ICustomFormatter](xref:System.ICustomFormatter) and [IFormatProvider](xref:System.IFormatProvider) to provide a complete custom formatting solution.</span></span> <span data-ttu-id="96132-158">자세한 내용은 [ICustomFormatter를 사용한 사용자 지정 서식 지정](#custom-formatting-with-icustomformatter) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-158">For more information, see the [Custom formatting with ICustomFormatter](#custom-formatting-with-icustomformatter) section.</span></span>

<span data-ttu-id="96132-159">다음 단원에서는 개체를 문자열 표현으로 변환하는 데 대해 이러한 메서드를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-159">The following sections examine these methods for converting an object to its string representation.</span></span>

## <a name="default-formatting-using-the-tostring-method"></a><span data-ttu-id="96132-160">ToString 메서드를 사용한 기본 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-160">Default formatting using the ToString method</span></span>

<span data-ttu-id="96132-161">[System.Object](xref:System.Object)에서 파생된 모든 형식은 기본적으로 형식의 이름을 반환하는, 매개 변수가 없는 [ToString](xref:System.Object.ToString) 메서드를 자동으로 상속받습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-161">Every type that is derived from [System.Object](xref:System.Object) automatically inherits a parameterless [ToString](xref:System.Object.ToString) method, which returns the name of the type by default.</span></span> <span data-ttu-id="96132-162">다음 예제에서는 기본 [ToString](xref:System.Object.ToString) 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96132-162">The following example illustrates the default [ToString](xref:System.Object.ToString) method.</span></span> <span data-ttu-id="96132-163">이 예제에서는 구현이 없는 `Automobile`이라는 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-163">It defines a class named `Automobile` that has no implementation.</span></span> <span data-ttu-id="96132-164">클래스를 인스턴스화하고 [ToString](xref:System.Object.ToString) 메서드를 호출하면 해당 형식 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-164">When the class is instantiated and its [ToString](xref:System.Object.ToString) method is called, it displays its type name.</span></span> <span data-ttu-id="96132-165">예제에서는 [ToString](xref:System.Object.ToString) 메서드를 명시적으로 호출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-165">Note that the [ToString](xref:System.Object.ToString) method is not explicitly called in the example.</span></span> <span data-ttu-id="96132-166">[Console.WriteLine(Object)](xref:System.Console.WriteLine(System.Object)) 메서드는 인수로 전달된 개체의 [ToString](xref:System.Object.ToString) 메서드를 암시적으로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-166">The [Console.WriteLine(Object)](xref:System.Console.WriteLine(System.Object)) method implicitly calls the [ToString](xref:System.Object.ToString) method of the object passed to it as an argument.</span></span> 

```csharp
using System;

public class Automobile
{
   // No implementation. All members are inherited from Object.
}

public class Example
{
   public static void Main()
   {
      Automobile firstAuto = new Automobile();
      Console.WriteLine(firstAuto);
   }
}
// The example displays the following output:
//       Automobile
```

```vb 
Public Class Automobile
   ' No implementation. All members are inherited from Object.
End Class

Module Example
   Public Sub Main()
      Dim firstAuto As New Automobile()
      Console.WriteLine(firstAuto)
   End Sub
End Module
' The example displays the following output:
'       Automobile
```

<span data-ttu-id="96132-167">인터페이스를 제외한 모든 형식이 [Object](xref:System.Object)에서 파생되기 때문에 이 함수는 사용자 지정 클래스 또는 구조체에 자동으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-167">Because all types other than interfaces are derived from [Object](xref:System.Object), this functionality is automatically provided to your custom classes or structures.</span></span> <span data-ttu-id="96132-168">그러나 기본 [ToString](xref:System.Object.ToString) 메서드에서 제공하는 기능은 제한적이므로 형식을 식별하더라도 해당 형식의 인스턴스에 대한 정보를 제공하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-168">However, the functionality offered by the default [ToString](xref:System.Object.ToString) method, is limited: Although it identifies the type, it fails to provide any information about an instance of the type.</span></span> <span data-ttu-id="96132-169">이 개체에 대한 정보를 제공하는 개체의 문자열 표현을 제공하려면 [ToString](xref:System.Object.ToString) 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-169">To provide a string representation of an object that provides information about that object, you must override the [ToString](xref:System.Object.ToString) method.</span></span>

> [!NOTE]
> <span data-ttu-id="96132-170">구조체는 [ValueType](xref:System.ValueType)에서 상속받고, 이 형식은 다시 [Object](xref:System.Object)에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-170">Structures inherit from [ValueType](xref:System.ValueType), which in turn is derived from [Object](xref:System.Object).</span></span> <span data-ttu-id="96132-171">[ValueType](xref:System.ValueType)이 [Object.ToString](xref:System.Object.ToString)을 재정의해도 해당 구현은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-171">Although [ValueType](xref:System.ValueType) overrides [Object.ToString](xref:System.Object.ToString), its implementation is identical.</span></span>

## <a name="overriding-the-tostring-method"></a><span data-ttu-id="96132-172">ToString 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="96132-172">Overriding the ToString method</span></span>

<span data-ttu-id="96132-173">형식 이름을 표시할 수 있는 경우가 종종 제한되어 형식의 사용자가 서로 다른 인스턴스를 구분할 수 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-173">Displaying the name of a type is often of limited use and does not allow consumers of your types to differentiate one instance from another.</span></span> <span data-ttu-id="96132-174">그러나 [ToString](xref:System.Object.ToString) 메서드를 재정의하여 개체 값을 더 유용하게 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-174">However, you can override the [ToString](xref:System.Object.ToString) method to provide a more useful representation of an object’s value.</span></span> <span data-ttu-id="96132-175">다음 예제에서는 `Temperature` 개체를 정의하고 해당 [ToString](xref:System.Object.ToString) 메서드를 재정의하여 온도를 섭씨 단위로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-175">The following example defines a `Temperature` object and overrides its [ToString](xref:System.Object.ToString) method to display the temperature in degrees Celsius.</span></span>

```csharp
using System;

public class Temperature
{
   private decimal temp;

   public Temperature(decimal temperature)
   {
      this.temp = temperature;   
   }

   public override string ToString()
   {
      return this.temp.ToString("N1") + "°C";
   }
}

public class Example
{
   public static void Main()
   {
      Temperature currentTemperature = new Temperature(23.6m);
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString());
   }
}
// The example displays the following output:
//       The current temperature is 23.6°C.
```

```vb
Public Class Temperature
   Private temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.temp = temperature
   End Sub

   Public Overrides Function ToString() As String
      Return Me.temp.ToString("N1") + "°C"   
   End Function
End Class

Module Example
   Public Sub Main()
      Dim currentTemperature As New Temperature(23.6d)
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString())
   End Sub
End Module
' The example displays the following output:
'       The current temperature is 23.6°C.
```

<span data-ttu-id="96132-176">.NET에서 각 기본 값 형식의 [ToString](xref:System.Object.ToString) 메서드는 개체의 이름 대신 개체의 값을 표시하도록 재정의되었습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-176">In .NET, the [ToString](xref:System.Object.ToString) method of each primitive value type has been overridden to display the object’s value instead of its name.</span></span> <span data-ttu-id="96132-177">다음 표에는 각 기본 형식의 재정의가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-177">The following table shows the override for each primitive type.</span></span> <span data-ttu-id="96132-178">재정의된 메서드의 대부분은 [ToString](xref:System.Object.ToString) 메서드의 다른 오버로드를 호출하고 해당 형식의 일반적인 서식을 정의하는 "G" 형식 지정자와 현재 문화권을 나타내는 [IFormatProvider](xref:System.IFormatProvider) 개체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-178">Note that most of the overridden methods call another overload of the [ToString](xref:System.Object.ToString) method and pass it the "G" format specifier, which defines the general format for its type, and an [IFormatProvider](xref:System.IFormatProvider) object that represents the current culture.</span></span>

<span data-ttu-id="96132-179">형식</span><span class="sxs-lookup"><span data-stu-id="96132-179">Type</span></span> | <span data-ttu-id="96132-180">ToString 재정의</span><span class="sxs-lookup"><span data-stu-id="96132-180">ToString override</span></span>
---- | -----------------
[<span data-ttu-id="96132-181">Boolean</span><span class="sxs-lookup"><span data-stu-id="96132-181">Boolean</span></span>](xref:System.Boolean) | <span data-ttu-id="96132-182">[Boolean.TrueString](xref:System.Boolean.TrueString) 또는 [Boolean.FalseString](xref:System.Boolean.FalseString)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-182">Returns either [Boolean.TrueString](xref:System.Boolean.TrueString) or [Boolean.FalseString](xref:System.Boolean.FalseString).</span></span>
[<span data-ttu-id="96132-183">Byte</span><span class="sxs-lookup"><span data-stu-id="96132-183">Byte</span></span>](xref:System.Byte) | <span data-ttu-id="96132-184">`Byte.ToString("G", NumberFormatInfo.CurrentInfo)`을 호출하여 현재 문화권에 대한 [Byte](xref:System.Byte) 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-184">Calls `Byte.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Byte](xref:System.Byte) value for the current culture.</span></span>
[<span data-ttu-id="96132-185">Char</span><span class="sxs-lookup"><span data-stu-id="96132-185">Char</span></span>](xref:System.Char) | <span data-ttu-id="96132-186">문자를 문자열로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-186">Returns the character as a string.</span></span>
[<span data-ttu-id="96132-187">DateTime</span><span class="sxs-lookup"><span data-stu-id="96132-187">DateTime</span></span>](xref:System.DateTime) | <span data-ttu-id="96132-188">`DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)`을 호출하여 현재 문화권에 대한 날짜 및 시간 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-188">Calls `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)` to format the date and time value for the current culture.</span></span> 
[<span data-ttu-id="96132-189">Decimal</span><span class="sxs-lookup"><span data-stu-id="96132-189">Decimal</span></span>](xref:System.Decimal) | <span data-ttu-id="96132-190">`Decimal.ToString("G", NumberFormatInfo.CurrentInfo)`을 호출하여 현재 문화권에 대한 [Decimal](xref:System.Decimal) 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-190">Calls `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Decimal](xref:System.Decimal) value for the current culture.</span></span>
[<span data-ttu-id="96132-191">Double</span><span class="sxs-lookup"><span data-stu-id="96132-191">Double</span></span>](xref:System.Double) | <span data-ttu-id="96132-192">`Double.ToString("G", NumberFormatInfo.CurrentInfo)`을 호출하여 현재 문화권에 대한 [Double](xref:System.Double) 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-192">Calls `Double.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Double](xref:System.Double) value for the current culture.</span></span>
[<span data-ttu-id="96132-193">Int16</span><span class="sxs-lookup"><span data-stu-id="96132-193">Int16</span></span>](xref:System.Int16) | <span data-ttu-id="96132-194">`Int16.ToString("G", NumberFormatInfo.CurrentInfo)`을 호출하여 현재 문화권에 대한 [Int16](xref:System.Int16) 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-194">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int16](xref:System.Int16) value for the current culture.</span></span>
[<span data-ttu-id="96132-195">Int32</span><span class="sxs-lookup"><span data-stu-id="96132-195">Int32</span></span>](xref:System.Int32) | <span data-ttu-id="96132-196">`Int16.ToString("G", NumberFormatInfo.CurrentInfo)`을 호출하여 현재 문화권에 대한 [Int32](xref:System.Int32) 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-196">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int32](xref:System.Int32) value for the current culture.</span></span>
[<span data-ttu-id="96132-197">Int64</span><span class="sxs-lookup"><span data-stu-id="96132-197">Int64</span></span>](xref:System.Int64) | <span data-ttu-id="96132-198">`Int16.ToString("G", NumberFormatInfo.CurrentInfo)`을 호출하여 현재 문화권에 대한 [Int64](xref:System.Int64) 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-198">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int64](xref:System.Int64) value for the current culture.</span></span>
[<span data-ttu-id="96132-199">SByte</span><span class="sxs-lookup"><span data-stu-id="96132-199">SByte</span></span>](xref:System.SByte) | <span data-ttu-id="96132-200">`Int16.ToString("G", NumberFormatInfo.CurrentInfo)`을 호출하여 현재 문화권에 대한 [SByte](xref:System.SByte)</span><span class="sxs-lookup"><span data-stu-id="96132-200">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [SByte](xref:System.SByte)</span></span> | <span data-ttu-id="96132-201">값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-201">value for the current culture.</span></span>
[<span data-ttu-id="96132-202">Single</span><span class="sxs-lookup"><span data-stu-id="96132-202">Single</span></span>](xref:System.Single) | <span data-ttu-id="96132-203">`Int16.ToString("G", NumberFormatInfo.CurrentInfo)`을 호출하여 현재 문화권에 대한 [Single](xref:System.Single) 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-203">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Single](xref:System.Single) value for the current culture.</span></span>
[<span data-ttu-id="96132-204">UInt32</span><span class="sxs-lookup"><span data-stu-id="96132-204">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="96132-205">`Int16.ToString("G", NumberFormatInfo.CurrentInfo)`을 호출하여 현재 문화권에 대한 [UInt32](xref:System.UInt32) 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-205">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt32](xref:System.UInt32)value for the current culture.</span></span>
[<span data-ttu-id="96132-206">UInt32</span><span class="sxs-lookup"><span data-stu-id="96132-206">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="96132-207">`Int16.ToString("G", NumberFormatInfo.CurrentInfo)`을 호출하여 현재 문화권에 대한 [UInt32](xref:System.UInt32) 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-207">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt32](xref:System.UInt32) value for the current culture.</span></span>
[<span data-ttu-id="96132-208">UInt64</span><span class="sxs-lookup"><span data-stu-id="96132-208">UInt64</span></span>](xref:System.UInt64) | <span data-ttu-id="96132-209">`Int16.ToString("G", NumberFormatInfo.CurrentInfo)`을 호출하여 현재 문화권에 대한 [UInt64](xref:System.UInt64) 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-209">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt64](xref:System.UInt64)  value for the current culture.</span></span>

## <a name="the-tostring-method-and-format-strings"></a><span data-ttu-id="96132-210">ToString 메서드 및 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-210">The ToString method and format strings</span></span>

<span data-ttu-id="96132-211">개체에 문자열 표현이 하나만 있는 경우에는 기본 [ToString](xref:System.Object.ToString) 메서드를 사용하거나 [ToString](xref:System.Object.ToString)을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-211">Relying on the default [ToString](xref:System.Object.ToString) method or overriding [ToString](xref:System.Object.ToString) is appropriate when an object has a single string representation.</span></span> <span data-ttu-id="96132-212">하지만 개체의 값에 여러 표현이 있는 경우가 자주 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-212">However, the value of an object often has multiple representations.</span></span> <span data-ttu-id="96132-213">예를 들어 온도는 화씨, 섭씨 또는 캘빈으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-213">For example, a temperature can be expressed in degrees Fahrenheit, degrees Celsius, or kelvins.</span></span> <span data-ttu-id="96132-214">마찬가지로 정수 값 10도 10, 10.0, 1.0e01, $10.00 등과 같은 여러 가지 방식으로 표현될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-214">Similarly, the integer value 10 can be represented in numerous ways, including 10, 10.0, 1.0e01, or $10.00.</span></span>

<span data-ttu-id="96132-215">하나의 값에 여러 문자열 표현을 허용하기 위해 .NET에서는 형식 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-215">To enable a single value to have multiple string representations, .NET uses format strings.</span></span> <span data-ttu-id="96132-216">형식 문자열은 하나 이상의 미리 정의된 형식 지정자가 들어 있는 문자열이며, 이러한 형식 지정자는 [ToString](xref:System.Object.ToString) 메서드가 해당 출력의 형식을 지정하는 방식을 정의한 단일 문자 또는 문자 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="96132-216">A format string is a string that contains one or more predefined format specifiers, which are single characters or groups of characters that define how the [ToString](xref:System.Object.ToString) method should format its output.</span></span> <span data-ttu-id="96132-217">형식 문자열은 개체의 [ToString](xref:System.Object.ToString) 메서드에 매개 변수로 전달되어 개체의 값에 대한 문자열 표현의 표시 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-217">The format string is then passed as a parameter to the object's [ToString](xref:System.Object.ToString) method and determines how the string representation of that object's value should appear.</span></span>

<span data-ttu-id="96132-218">.NET의 모든 숫자 형식, 날짜/시간 형식 및 열거형 형식은 미리 정의된 형식 지정자 집합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-218">All numeric types, date and time types, and enumeration types in .NET support a predefined set of format specifiers.</span></span> <span data-ttu-id="96132-219">형식 문자열을 사용하여 응용 프로그램 정의 데이터 형식의 여러 문자열 표현도 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-219">You can also use format strings to define multiple string representations of your application-defined data types.</span></span>

### <a name="standard-format-strings"></a><span data-ttu-id="96132-220">표준 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-220">Standard format strings</span></span>

<span data-ttu-id="96132-221">표준 형식 문자열에는 개체의 문자열 표현을 정의하는 영문자인 단일 형식 지정자와 함께 결과 문자열을 표시하는 데 사용할 자릿수에 영향을 주는 선택적 전체 자릿수 지정자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-221">A standard format string contains a single format specifier, which is an alphabetic character that defines the string representation of the object to which it is applied, along with an optional precision specifier that affects how many digits are displayed in the result string.</span></span> <span data-ttu-id="96132-222">전체 자릿수 지정자가 생략되었거나 지원되지 않으면 표준 형식 지정자는 표준 형식 문자열과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-222">If the precision specifier is omitted or is not supported, a standard format specifier is equivalent to a standard format string.</span></span> 

<span data-ttu-id="96132-223">.NET에서는 모든 숫자 형식, 날짜/시간 형식 및 열거형 형식에 대한 표준 형식 지정자 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-223">.NET defines a set of standard format specifiers for all numeric types, all date and time types, and all enumeration types.</span></span> <span data-ttu-id="96132-224">예를 들어, 이러한 각 범주는 해당 형식 값에 대한 일반적인 문자열 표현을 정의하는 "G" 표준 형식 지정자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-224">For example, each of these categories supports a "G" standard format specifier, which defines a general string representation of a value of that type.</span></span>

<span data-ttu-id="96132-225">열거형 형식의 표준 형식 문자열은 값의 문자열 표현을 직접 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-225">Standard format strings for enumeration types directly control the string representation of a value.</span></span> <span data-ttu-id="96132-226">열거형 값의 [ToString](xref:System.Object.ToString) 메서드에 전달된 형식 문자열은 값이 문자열 이름("G" 및 "F" 형식 지정자), 내부 정수 값("D" 형식 지정자) 또는 16진수 값("X" 형식 지정자)을 사용하여 표시되는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-226">The format strings passed to an enumeration value’s [ToString](xref:System.Object.ToString) method determine whether the value is displayed using its string name (the "G" and "F" format specifiers), its underlying integral value (the "D" format specifier), or its hexadecimal value (the "X" format specifier).</span></span> <span data-ttu-id="96132-227">다음 예제에서는 표준 형식 문자열을 사용하여 [DayOfWeek](xref:System.DayOfWeek) 열거형 값의 형식을 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96132-227">The following example illustrates the use of standard format strings to format a [DayOfWeek](xref:System.DayOfWeek) enumeration value.</span></span> 

```csharp
DayOfWeek thisDay = DayOfWeek.Monday;
string[] formatStrings = {"G", "F", "D", "X"};

foreach (string formatString in formatStrings)
   Console.WriteLine(thisDay.ToString(formatString));
// The example displays the following output:
//       Monday
//       Monday
//       1
//       00000001
```

```vb
Dim thisDay As DayOfWeek = DayOfWeek.Monday
Dim formatStrings() As String = {"G", "F", "D", "X"}

For Each formatString As String In formatStrings
   Console.WriteLine(thisDay.ToString(formatString))
Next
' The example displays the following output:
'       Monday
'       Monday
'       1
'       00000001
```

<span data-ttu-id="96132-228">열거형 서식 문자열에 대한 자세한 내용은 [열거형 서식 문자열](enumeration-format.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-228">For information about enumeration format strings, see [Enumeration format strings](enumeration-format.md).</span></span>

<span data-ttu-id="96132-229">일반적으로 숫자 형식의 표준 형식 문자열은 정확한 모양이 하나 이상의 속성 값에 의해 제어되는 결과 문자열을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-229">Standard format strings for numeric types usually define a result string whose precise appearance is controlled by one or more property values.</span></span> <span data-ttu-id="96132-230">예를 들어, "C" 형식 지정자는 숫자의 형식을 통화 값으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-230">For example, the "C" format specifier formats a number as a currency value.</span></span> <span data-ttu-id="96132-231">"C" 형식 지정자를 유일한 매개 변수로 사용하여 [ToString](xref:System.Object.ToString) 메서드를 호출하면 현재 문화권의 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 개체에 있는 다음 속성 값이 숫자 값의 문자열 표현을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-231">When you call the [ToString](xref:System.Object.ToString) method with the "C" format specifier as the only parameter, the following property values from the current culture’s [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object are used to define the string representation of the numeric value:</span></span>

* <span data-ttu-id="96132-232">현재 문화권의 통화 기호를 지정하는 [CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) 속성</span><span class="sxs-lookup"><span data-stu-id="96132-232">The [CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) property, which specifies the current culture’s currency symbol.</span></span>

* <span data-ttu-id="96132-233">다음과 같은 사항을 결정하는 정수를 반환하는 [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) 또는 [CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern) 속성</span><span class="sxs-lookup"><span data-stu-id="96132-233">The [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) or [CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern) property, which returns an integer that determines the following:</span></span> 

    * <span data-ttu-id="96132-234">통화 기호의 위치</span><span class="sxs-lookup"><span data-stu-id="96132-234">The placement of the currency symbol.</span></span>
    
    * <span data-ttu-id="96132-235">음수 값이 선행 음수 기호, 후행 음수 기호 또는 괄호로 표시되는지 여부</span><span class="sxs-lookup"><span data-stu-id="96132-235">Whether negative values are indicated by a leading negative sign, a trailing negative sign, or parentheses.</span></span>
    
    * <span data-ttu-id="96132-236">숫자 값과 통화 기호 사이에 공백이 표시되는지 여부</span><span class="sxs-lookup"><span data-stu-id="96132-236">Whether a space appears between the numeric value and the currency symbol.</span></span>
    
* <span data-ttu-id="96132-237">결과 문자열의 소수 자릿수를 정의하는 [CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits) 속성</span><span class="sxs-lookup"><span data-stu-id="96132-237">The [CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits) property, which defines the number of fractional digits in the result string.</span></span>

* <span data-ttu-id="96132-238">결과 문자열의 소수 구분 기호를 정의하는 [CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) 속성</span><span class="sxs-lookup"><span data-stu-id="96132-238">The [CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) property, which defines the decimal separator symbol in the result string.</span></span>

* <span data-ttu-id="96132-239">그룹 구분 기호를 정의하는 [CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) 속성</span><span class="sxs-lookup"><span data-stu-id="96132-239">The [CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) property, which defines the group separator symbol.</span></span>

* <span data-ttu-id="96132-240">정수 부분의 각 그룹 자릿수를 정의하는 [CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes) 속성</span><span class="sxs-lookup"><span data-stu-id="96132-240">The [CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes) property, which defines the number of digits in each group to the left of the decimal.</span></span>

* <span data-ttu-id="96132-241">음수 값을 나타내는 데 괄호가 사용되지 않는 경우 결과 문자열에 사용되는 음수 기호를 결정하는 [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) 속성</span><span class="sxs-lookup"><span data-stu-id="96132-241">The [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) property, which determines the negative sign used in the result string if parentheses are not used to indicate negative values.</span></span>

<span data-ttu-id="96132-242">이외에도 숫자 형식 문자열에는 전체 자릿수 지정자가 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-242">In addition, numeric format strings may include a precision specifier.</span></span> <span data-ttu-id="96132-243">이 지정자의 의미는 해당 지정자가 사용되는 형식 문자열에 따라 달라지지만 일반적으로 결과 문자열에 표시될 전체 자릿수나 소수 자릿수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="96132-243">The meaning of this specifier depends on the format string with which it is used, but it typically indicates either the total number of digits or the number of fractional digits that should appear in the result string.</span></span> <span data-ttu-id="96132-244">예를 들어, 다음 예제에서는 "X4" 표준 숫자 문자열과 전체 자릿수 지정자를 사용하여 네 자리의 16진수로 구성된 문자열 값을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96132-244">For example, the following example uses the "X4" standard numeric string and a precision specifier to create a string value that has four hexadecimal digits.</span></span>

```csharp
byte[] byteValues = { 12, 163, 255 };
foreach (byte byteValue in byteValues)
   Console.WriteLine(byteValue.ToString("X4"));
// The example displays the following output:
//       000C
//       00A3
//       00FF
```

```vb
Dim byteValues() As Byte = { 12, 163, 255 }
For Each byteValue As Byte In byteValues
   Console.WriteLine(byteValue.ToString("X4"))
Next
' The example displays the following output:
'       000C
'       00A3
'       00FF
```

<span data-ttu-id="96132-245">표준 숫자 서식 문자열에 대한 자세한 내용은 [표준 숫자 서식 문자열](standard-numeric.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-245">For more information about standard numeric formatting strings, see [Standard numeric format strings](standard-numeric.md).</span></span> 

<span data-ttu-id="96132-246">날짜 및 시간 값의 표준 형식 문자열은 특정 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 클래스에 저장된 사용자 지정 형식 문자열의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="96132-246">Standard format strings for date and time values are aliases for custom format strings stored by a particular [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) class.</span></span> <span data-ttu-id="96132-247">예를 들어, "D" 형식 지정자를 사용하여 날짜 및 시간 값의 [ToString](xref:System.Object.ToString) 메서드를 호출하면 현재 문화권의 [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) 속성에 저장된 사용자 지정 형식 문자열을 사용하여 날짜 및 시간이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-247">For example, calling the [ToString](xref:System.Object.ToString) method of a date and time value with the "D" format specifier displays the date and time by using the custom format string stored in the current culture’s [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) property.</span></span> <span data-ttu-id="96132-248">사용자 지정 서식 문자열에 대한 자세한 내용은 [사용자 지정 서식 문자열](#custom-format-strings)을 참조하세요. 다음 예제에서는 이러한 관계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96132-248">(For more information about custom format strings, see the [Custom format strings](#custom-format-strings) section.) The following example illustrates this relationship.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      DateTime date1 = new DateTime(2017, 6, 30);
      Console.WriteLine("D Format Specifier:     {0:D}", date1);
      string longPattern = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern;
      Console.WriteLine("'{0}' custom format string:     {1}", 
                        longPattern, date1.ToString(longPattern));
   }
}
// The example displays the following output when run on a system whose
// current culture is en-US:
//    D Format Specifier:     Tuesday, June 30, 2017
//    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2017
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim date1 As Date = #6/30/2009#
      Console.WriteLine("D Format Specifier:     {0:D}", date1)
      Dim longPattern As String = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern
      Console.WriteLine("'{0}' custom format string:     {1}", _
                        longPattern, date1.ToString(longPattern))
   End Sub
End Module
' The example displays the following output when run on a system whose
' current culture is en-US:
'    D Format Specifier:     Tuesday, June 30, 2009
'    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2009
```

<span data-ttu-id="96132-249">표준 날짜 및 시간 서식 문자열에 대한 자세한 내용은 [표준 날짜 및 시간 서식 문자열](standard-datetime.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-249">For more information about standard date and time format strings, see [Standard date and time format strings](standard-datetime.md).</span></span>

<span data-ttu-id="96132-250">표준 형식 문자열을 사용하여 개체의 `ToString(String)` 메서드에 의해 생성되는 응용 프로그램 정의 개체의 문자열 표현도 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-250">You can also use standard format strings to define the string representation of an application-defined object that is produced by the object’s `ToString(String)` method.</span></span> <span data-ttu-id="96132-251">개체가 지원하는 특정 표준 형식 지정자를 정의하고 이러한 지정자가 대/소문자를 구분하는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-251">You can define the specific standard format specifiers that your object supports, and you can determine whether they are case-sensitive or case-insensitive.</span></span> <span data-ttu-id="96132-252">`ToString(String)` 메서드의 구현에서는 다음을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-252">Your implementation of the `ToString(String)` method should support the following:</span></span>

* <span data-ttu-id="96132-253">개체의 사용자 지정 또는 일반 형식을 나타내는 "G" 형식 지정자.</span><span class="sxs-lookup"><span data-stu-id="96132-253">A "G" format specifier that represents a customary or common format of the object.</span></span> <span data-ttu-id="96132-254">개체의 `ToString` 메서드에 대한 매개 변수가 없는 오버로드는 해당 `ToString(String)` 오버로드를 호출하고 이를 "G" 표준 형식 문자열에 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-254">The parameterless overload of your object's `ToString` method should call its `ToString(String)` overload and pass it the "G" standard format string.</span></span>

* <span data-ttu-id="96132-255">null 참조와 동일한 형식 지정자에 대한 지원.</span><span class="sxs-lookup"><span data-stu-id="96132-255">Support for a format specifier that is equal to a null reference.</span></span> <span data-ttu-id="96132-256">null 참조와 동일한 형식 지정자는 "G" 형식 지정자와 같은 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-256">A format specifier that is equal to a null reference should be considered equivalent to the "G" format specifier.</span></span>

<span data-ttu-id="96132-257">예를 들어 `Temperature` 클래스는 섭씨 온도를 내부적으로 저장하고 형식 지정자를 사용하여 `Temperature` 개체의 값을 섭씨, 화씨 및 캘빈으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-257">For example, a `Temperature` class can internally store the temperature in degrees Celsius and use format specifiers to represent the value of the `Temperature` object in degrees Celsius, degrees Fahrenheit, and kelvins.</span></span> <span data-ttu-id="96132-258">다음 예제에서 이에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-258">The following example provides an illustration.</span></span>

```csharp
using System;

public class Temperature
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round(((decimal) (this.m_Temp * 9 / 5 + 32)), 2); }
   }

   public override string ToString()
   {
      return this.ToString("C");
   }

   public string ToString(string format)
   {  
      // Handle null or empty string.
      if (String.IsNullOrEmpty(format)) format = "C";
      // Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant();      

      // Convert temperature to Fahrenheit and return string.
      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2") + " °F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2") + " K";
         // return temperature in Celsius.
         case "G":
         case "C":
            return this.Celsius.ToString("N2") + " °C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}

public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(0m);
      Console.WriteLine(temp1.ToString());
      Console.WriteLine(temp1.ToString("G"));
      Console.WriteLine(temp1.ToString("C"));
      Console.WriteLine(temp1.ToString("F"));
      Console.WriteLine(temp1.ToString("K"));

      Temperature temp2 = new Temperature(-40m);
      Console.WriteLine(temp2.ToString());
      Console.WriteLine(temp2.ToString("G"));
      Console.WriteLine(temp2.ToString("C"));
      Console.WriteLine(temp2.ToString("F"));
      Console.WriteLine(temp2.ToString("K"));

      Temperature temp3 = new Temperature(16m);
      Console.WriteLine(temp3.ToString());
      Console.WriteLine(temp3.ToString("G"));
      Console.WriteLine(temp3.ToString("C"));
      Console.WriteLine(temp3.ToString("F"));
      Console.WriteLine(temp3.ToString("K"));

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3));
   }
}
// The example displays the following output:
//       0.00 °C
//       0.00 °C
//       0.00 °C
//       32.00 °F
//       273.15 K
//       -40.00 °C
//       -40.00 °C
//       -40.00 °C
//       -40.00 °F
//       233.15 K
//       16.00 °C
//       16.00 °C
//       16.00 °C
//       60.80 °F
//       289.15 K
//       The temperature is now 16.00 °C.
```

```vb
Public Class Temperature
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("C")
   End Function

   Public Overloads Function ToString(format As String) As String  
      ' Handle null or empty string.
      If String.IsNullOrEmpty(format) Then format = "C"
      ' Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant()      

      Select Case format
         Case "F"
           ' Convert temperature to Fahrenheit and return string.
            Return Me.Fahrenheit.ToString("N2") & " °F"
         Case "K"
            ' Convert temperature to Kelvin and return string.
            Return Me.Kelvin.ToString("N2") & " K"
         Case "C", "G"
            ' Return temperature in Celsius.
            Return Me.Celsius.ToString("N2") & " °C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(0d)
      Console.WriteLine(temp1.ToString())
      Console.WriteLine(temp1.ToString("G"))
      Console.WriteLine(temp1.ToString("C"))
      Console.WriteLine(temp1.ToString("F"))
      Console.WriteLine(temp1.ToString("K"))

      Dim temp2 As New Temperature(-40d)
      Console.WriteLine(temp2.ToString())
      Console.WriteLine(temp2.ToString("G"))
      Console.WriteLine(temp2.ToString("C"))
      Console.WriteLine(temp2.ToString("F"))
      Console.WriteLine(temp2.ToString("K"))

      Dim temp3 As New Temperature(16d)
      Console.WriteLine(temp3.ToString())
      Console.WriteLine(temp3.ToString("G"))
      Console.WriteLine(temp3.ToString("C"))
      Console.WriteLine(temp3.ToString("F"))
      Console.WriteLine(temp3.ToString("K"))

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3))
   End Sub
End Module
' The example displays the following output:
'       0.00 °C
'       0.00 °C
'       0.00 °C
'       32.00 °F
'       273.15 K
'       -40.00 °C
'       -40.00 °C
'       -40.00 °C
'       -40.00 °F
'       233.15 K
'       16.00 °C
'       16.00 °C
'       16.00 °C
'       60.80 °F
'       289.15 K
'       The temperature is now 16.00 °C.
```

### <a name="custom-format-strings"></a><span data-ttu-id="96132-259">사용자 지정 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-259">Custom format strings</span></span>

<span data-ttu-id="96132-260">표준 형식 문자열 외에도 .NET에서는 숫자 값과 날짜 및 시간 값에 대한 사용자 지정 형식 문자열을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-260">In addition to the standard format strings, .NET defines custom format strings for both numeric values and date and time values.</span></span> <span data-ttu-id="96132-261">사용자 지정 형식 문자열은 값의 문자열 표현을 정의하는 하나 이상의 사용자 지정 형식 지정자로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-261">A custom format string consists of one or more custom format specifiers that define the string representation of a value.</span></span> <span data-ttu-id="96132-262">예를 들어, en-US 문화권의 경우 사용자 지정 날짜 및 시간 형식 문자열 "yyyy/mm/dd hh:mm:ss t zzz"는 날짜를 "2008/11/15 07:45:00.0000 P -08:00" 형태의 문자열 표현으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-262">For example, the custom date and time format string "yyyy/mm/dd hh:mm:ss.ffff t zzz" converts a date to its string representation in the form "2008/11/15 07:45:00.0000 P -08:00" for the en-US culture.</span></span> <span data-ttu-id="96132-263">마찬가지로 사용자 지정 형식 문자열 "0000"은 정수 값 12를 "0012"로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-263">Similarly, the custom format string "0000" converts the integer value 12 to "0012".</span></span> <span data-ttu-id="96132-264">사용자 지정 서식 문자열의 전체 목록은 [사용자 지정 날짜 및 시간 서식 문자열](custom-datetime.md) 및 [사용자 지정 숫자 서식 문자열](custom-numeric.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-264">For a complete list of custom format strings, see [Custom date and time format strings](custom-datetime.md) and [Custom numeric format strings](custom-numeric.md).</span></span>

<span data-ttu-id="96132-265">형식 문자열이 단일 사용자 지정 형식 지정자로 구성된 경우에는 표준 형식 지정자와 혼동되지 않도록 형식 지정자 앞에 백분율 기호(%)가 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-265">If a format string consists of a single custom format specifier, the format specifier should be preceded by the percent (%) symbol to avoid confusion with a standard format specifier.</span></span> <span data-ttu-id="96132-266">다음 예제에서는 "M" 사용자 지정 형식 지정자를 사용하여 특정 날짜의 월에 해당하는 한 자리 또는 두 자리 숫자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-266">The following example uses the "M" custom format specifier to display a one-digit or two-digit number of the month of a particular date.</span></span>

```csharp
DateTime date1 = new DateTime(2009, 9, 8);
Console.WriteLine(date1.ToString("%M"));       
// Displays 9
```

```vb
Dim date1 As Date = #09/08/2009#
Console.WriteLine(date1.ToString("%M"))      ' Displays 9
```

<span data-ttu-id="96132-267">많은 표준 형식 문자열은 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 개체의 속성에 정의된 사용자 지정 형식 문자열의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="96132-267">Many standard format strings for date and time values are aliases for custom format strings that are defined by properties of the [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object.</span></span> <span data-ttu-id="96132-268">또한 사용자 지정 형식 문자열을 사용하면 상당히 융통성 있게 숫자 값 또는 날짜 및 시간 값에 대한 응용 프로그램 정의 형식 지정 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-268">Custom format strings also offer considerable flexibility in providing application-defined formatting for numeric values or date and time values.</span></span> <span data-ttu-id="96132-269">여러 사용자 지정 형식 지정자를 하나의 사용자 지정 형식 문자열로 결합하여 숫자 값과 날짜 및 시간 값에 대한 사용자 지정 결과 문자열을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-269">You can define your own custom result strings for both numeric values and date and time values by combining multiple custom format specifiers into a single custom format string.</span></span> <span data-ttu-id="96132-270">다음 예제에서는 월 이름, 일, 연도 및 괄호로 묶은 요일을 차례로 표시하는 사용자 지정 형식 문자열을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-270">The following example defines a custom format string that displays the day of the week in parentheses after the month name, day, and year.</span></span>

```csharp
string customFormat = "MMMM dd, yyyy (dddd)";
DateTime date1 = new DateTime(2009, 8, 28);
Console.WriteLine(date1.ToString(customFormat));   
// The example displays the following output if run on a system
// whose language is English:
//       August 28, 2009 (Friday) 
```

```vb
Dim customFormat As String = "MMMM dd, yyyy (dddd)"
Dim date1 As Date = #8/28/2009#
Console.WriteLine(date1.ToString(customFormat))   
' The example displays the following output if run on a system
' whose language is English:
'       August 28, 2009 (Friday) 
```

<span data-ttu-id="96132-271">다음 예제에서는 [Int64](xref:System.Int64) 값을 7자리 표준 미국 전화 번호로 지역 번호와 함께 표시하는 사용자 지정 형식 문자열을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-271">The following example defines a custom format string that displays an [Int64](xref:System.Int64) value as a standard, seven-digit U.S. telephone number along with its area code.</span></span> 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      long number = 8009999999;
      string fmt = "000-000-0000";
      Console.WriteLine(number.ToString(fmt));
   }
}
// The example displays the following output:
//        800-999-9999
```

```vb
Module Example
   Public Sub Main()
      Dim number As Long = 8009999999
      Dim fmt As String = "000-000-0000"
      Console.WriteLine(number.ToString(fmt))
   End Sub
End Module
' The example displays the following output:

' The example displays the following output:
'       800-999-9999
```

<span data-ttu-id="96132-272">일반적으로 표준 형식 문자열로 응용 프로그램 정의 형식의 형식 지정 요구를 대부분 처리할 수 있지만 사용자 지정 형식 지정자를 정의하여 형식의 형식을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-272">Although standard format strings can generally handle most of the formatting needs for your application-defined types, you may also define custom format specifiers to format your types.</span></span> 

### <a name="format-strings-and-net-types"></a><span data-ttu-id="96132-273">서식 문자열 및 .NET 형식</span><span class="sxs-lookup"><span data-stu-id="96132-273">Format strings and .NET types</span></span>

<span data-ttu-id="96132-274">모든 숫자 형식(즉, [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64), [BigInteger](xref:System.Numerics.BigInteger) 형식), [DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset), [TimeSpan](xref:System.TimeSpan), [Guid](xref:System.Guid) 및 모든 열거형 형식은 형식 문자열을 사용한 형식 지정을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-274">All numeric types (that is, the [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64), and [BigInteger](xref:System.Numerics.BigInteger) types), as well as the [DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset), [TimeSpan](xref:System.TimeSpan), [Guid](xref:System.Guid), and all enumeration types, support formatting with format strings.</span></span> <span data-ttu-id="96132-275">각 형식에서 지원되는 형식 문자열에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-275">For information on the specific format strings supported by each type, see the following topics:</span></span> 

<span data-ttu-id="96132-276">제목</span><span class="sxs-lookup"><span data-stu-id="96132-276">Title</span></span> | <span data-ttu-id="96132-277">정의</span><span class="sxs-lookup"><span data-stu-id="96132-277">Definition</span></span>
----- | ----------
[<span data-ttu-id="96132-278">표준 숫자 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-278">Standard numeric format strings</span></span>](standard-numeric.md) | <span data-ttu-id="96132-279">숫자 값의 일반적으로 사용되는 문자열 표현을 만드는 표준 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-279">Describes standard format strings that create commonly used string representations of numeric values.</span></span> 
[<span data-ttu-id="96132-280">사용자 지정 숫자 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-280">Custom numeric format strings</span></span>](custom-numeric.md) | <span data-ttu-id="96132-281">숫자 값의 응용 프로그램별 형식을 만드는 사용자 지정 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-281">Describes custom format strings that create application-specific formats for numeric values.</span></span>
[<span data-ttu-id="96132-282">표준 날짜 및 시간 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-282">Standard date and time format strings</span></span>](standard-datetime.md) | <span data-ttu-id="96132-283">[DateTime](xref:System.DateTime) 값의 일반적으로 사용되는 문자열 표현을 만드는 표준 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-283">Describes standard format strings that create commonly used string representations of [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="96132-284">사용자 지정 날짜 및 시간 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-284">Custom date and time format strings</span></span>](custom-datetime.md) | <span data-ttu-id="96132-285">[DateTime](xref:System.DateTime) 값의 응용 프로그램별 형식을 만드는 사용자 지정 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-285">Describes custom format strings that create application-specific formats for [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="96132-286">표준 TimeSpan 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-286">Standard TimeSpan format Strings</span></span>](standard-timespan.md) | <span data-ttu-id="96132-287">시간 간격의 일반적으로 사용되는 문자열 표현을 만드는 표준 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-287">Describes standard format strings that create commonly used string representations of time intervals.</span></span>
[<span data-ttu-id="96132-288">사용자 지정 TimeSpan 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-288">Custom TimeSpan format strings</span></span>](custom-timespan.md) | <span data-ttu-id="96132-289">시간 간격의 응용 프로그램별 형식을 만드는 사용자 지정 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-289">Describes custom format strings that create application-specific formats for time intervals.</span></span>
[<span data-ttu-id="96132-290">열거형 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-290">Enumeration format strings</span></span>](enumeration-format.md) | <span data-ttu-id="96132-291">열거형 값의 문자열 표현을 만드는 데 사용되는 표준 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-291">Describes standard format strings that are used to create string representations of enumeration values.</span></span>
<span data-ttu-id="96132-292">[Guid.ToString(String)](xref:System.Guid.ToString(System.String))</span><span class="sxs-lookup"><span data-stu-id="96132-292">[Guid.ToString(String)](xref:System.Guid.ToString(System.String))</span></span> | <span data-ttu-id="96132-293">[Guid](xref:System.Guid) 값의 표준 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-293">Describes standard format strings for [Guid](xref:System.Guid) values.</span></span>

## <a name="culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface"></a><span data-ttu-id="96132-294">형식 공급자 및 IFormatProvider 인터페이스를 사용하여 문화권 구분 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-294">Culture-Sensitive Formatting with Format Providers and the IFormatProvider Interface</span></span>

<span data-ttu-id="96132-295">형식 지정자를 사용하여 개체의 형식 지정을 사용자 지정할 수 있기는 하지만 의미 있는 개체의 문자열 표현을 만들려면 추가 형식 지정 정보가 필요한 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-295">Although format specifiers let you customize the formatting of objects, producing a meaningful string representation of objects often requires additional formatting information.</span></span> <span data-ttu-id="96132-296">예를 들어, C" 표준 형식 문자열이나 "$ #,#.00" 같은 사용자 지정 형식 문자열을 사용하여 숫자의 형식을 통화 값으로 지정하려면 최소한 올바른 통화 기호, 그룹 구분 기호 및 소수 구분 기호에 대한 정보를 형식 지정된 문자열에 포함할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-296">For example, formatting a number as a currency value by using either the "C" standard format string or a custom format string such as "$ #,#.00" requires, at a minimum, information about the correct currency symbol, group separator, and decimal separator to be available to include in the formatted string.</span></span> <span data-ttu-id="96132-297">.NET에서는 이러한 추가 형식 지정 정보를 [IFormatProvider](xref:System.IFormatProvider) 인터페이스를 통해 사용할 수 있습니다. 이러한 인터페이스는 숫자 형식과 날짜 및 시간 형식의 `ToString` 메서드에 대한 하나 이상의 오버로드에 매개 변수로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-297">In .NET, this additional formatting information is made available through the [IFormatProvider](xref:System.IFormatProvider) interface, which is provided as a parameter to one or more overloads of the `ToString` method of numeric types and date and time types.</span></span> <span data-ttu-id="96132-298">[IFormatProvider](xref:System.IFormatProvider) 구현은 문화권별 형식 지정을 지원하기 위해 .NET에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-298">[IFormatProvider](xref:System.IFormatProvider) implementations are used in .NET to support culture-specific formatting.</span></span> <span data-ttu-id="96132-299">다음 예제에서는 서로 다른 문화권을 나타내는 세 [IFormatProvider](xref:System.IFormatProvider) 개체를 사용하여 형식을 지정할 때 개체의 문자열 표현이 어떻게 바뀌는지 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96132-299">The following example illustrates how the string representation of an object changes when it is formatted with three [IFormatProvider](xref:System.IFormatProvider) objects that represent different cultures.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      decimal value = 1603.42m;
      Console.WriteLine(value.ToString("C3", new CultureInfo("en-US")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("fr-FR")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("de-DE")));
   }
}
// The example displays the following output:
//       $1,603.420
//       1 603,420 €
//       1.603,420 €
```

```vb
Imports System.Globalization

Public Module Example
   Public Sub Main()
      Dim value As Decimal = 1603.42d
      Console.WriteLine(value.ToString("C3", New CultureInfo("en-US")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("fr-FR")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("de-DE")))
   End Sub
End Module
' The example displays the following output:
'       $1,603.420
'       1 603,420 €
'       1.603,420 €
```

<span data-ttu-id="96132-300">[IFormatProvider](xref:System.IFormatProvider) 인터페이스에는 [GetFormat(Type)](xref:System.IFormatProvider.GetFormat(System.Type)) 메서드가 하나 있으며, 이 메서드에는 형식 지정 정보를 제공하는 개체의 형식을 지정하는 매개 변수가 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-300">The [IFormatProvider](xref:System.IFormatProvider) interface includes one method, [GetFormat(Type)](xref:System.IFormatProvider.GetFormat(System.Type)), which has a single parameter that specifies the type of object that provides formatting information.</span></span> <span data-ttu-id="96132-301">이 메서드는 해당 형식의 개체를 제공할 수 있는 경우 해당 형식의 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-301">If the method can provide an object of that type, it returns it.</span></span> <span data-ttu-id="96132-302">제공할 수 없으면 null 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-302">Otherwise, it returns a null reference.</span></span>

<span data-ttu-id="96132-303">[IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))은 콜백 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="96132-303">[IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) is a callback method.</span></span> <span data-ttu-id="96132-304">[IFormatProvider](xref:System.IFormatProvider) 매개 변수가 포함된 `ToString` 메서드 오버로드를 호출하면 해당 [IFormatProvider](xref:System.IFormatProvider) 개체의 [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-304">When you call a `ToString` method overload that includes an [IFormatProvider](xref:System.IFormatProvider) parameter, it calls the [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method of that [IFormatProvider](xref:System.IFormatProvider) object.</span></span> <span data-ttu-id="96132-305">[GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) 메서드는 *formatType* 매개 변수에 지정된 대로 필요한 형식 지정 정보를 제공하는 개체를 `ToString` 메서드에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-305">The [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method is responsible for returning an object that provides the necessary formatting information, as specified by its *formatType* parameter, to the `ToString` method.</span></span> 

<span data-ttu-id="96132-306">[IFormatProvider](xref:System.IFormatProvider) 형식의 매개 변수를 포함하는 형식 지정 또는 문자열 변환 메서드가 많이 있기는 하지만 대부분의 경우 메서드를 호출할 때 매개 변수의 값이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-306">A number of formatting or string conversion methods include a parameter of type [IFormatProvider](xref:System.IFormatProvider), but in many cases the value of the parameter is ignored when the method is called.</span></span> <span data-ttu-id="96132-307">다음 표에서는 매개 변수를 사용하는 형식 지정 메서드와 이러한 메서드가 [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) 메서드로 전달하는 [Type](xref:System.Type) 개체의 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96132-307">The following table lists some of the formatting methods that use the parameter and the type of the [Type](xref:System.Type) object that they pass to the [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method.</span></span> 

<span data-ttu-id="96132-308">메서드</span><span class="sxs-lookup"><span data-stu-id="96132-308">Method</span></span> | <span data-ttu-id="96132-309">*formatType* 매개 변수의 유형</span><span class="sxs-lookup"><span data-stu-id="96132-309">Type of *formatType* parameter</span></span>
------ | ------------------------------
<span data-ttu-id="96132-310">숫자 형식의 `ToString` 메서드</span><span class="sxs-lookup"><span data-stu-id="96132-310">`ToString` method of numeric types</span></span> | [<span data-ttu-id="96132-311">System.Globalization.NumberFormatInfo</span><span class="sxs-lookup"><span data-stu-id="96132-311">System.Globalization.NumberFormatInfo</span></span>](xref:System.Globalization.NumberFormatInfo)
<span data-ttu-id="96132-312">날짜 및 시간 형식의 `ToString` 메서드</span><span class="sxs-lookup"><span data-stu-id="96132-312">`ToString` method of date and time types</span></span> | [<span data-ttu-id="96132-313">System.Globalization.DateTimeFormatInfo</span><span class="sxs-lookup"><span data-stu-id="96132-313">System.Globalization.DateTimeFormatInfo</span></span>](xref:System.Globalization.DateTimeFormatInfo)
<span data-ttu-id="96132-314">[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="96132-314">[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))</span></span> | [<span data-ttu-id="96132-315">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="96132-315">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)
<span data-ttu-id="96132-316">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="96132-316">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span></span> | [<span data-ttu-id="96132-317">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="96132-317">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)

<span data-ttu-id="96132-318">.NET에는 [IFormatProvider](xref:System.IFormatProvider)를 구현하는 세 가지 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-318">.NET provides three classes that implement [IFormatProvider](xref:System.IFormatProvider):</span></span> 

* <span data-ttu-id="96132-319">특정 문화권의 날짜 및 시간 값에 대한 형식 지정 정보를 제공하는 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 클래스.</span><span class="sxs-lookup"><span data-stu-id="96132-319">[DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), a class that provides formatting information for date and time values for a specific culture.</span></span> <span data-ttu-id="96132-320">이 클래스에 대해 [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))을 구현하면 해당 클래스의 인스턴스가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-320">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation returns an instance of itself.</span></span>

* <span data-ttu-id="96132-321">특정 문화권의 숫자 형식 지정 정보를 제공하는 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 클래스.</span><span class="sxs-lookup"><span data-stu-id="96132-321">[NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), a class that provides numeric formatting information for a specific culture.</span></span> <span data-ttu-id="96132-322">이 클래스에 대해 [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))을 구현하면 해당 클래스의 인스턴스가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-322">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation returns an instance of itself.</span></span>

* <span data-ttu-id="96132-323">[CultureInfo](xref:System.Globalization.CultureInfo).</span><span class="sxs-lookup"><span data-stu-id="96132-323">[CultureInfo](xref:System.Globalization.CultureInfo).</span></span> <span data-ttu-id="96132-324">이 클래스에 대해 [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))을 구현하면 숫자 형식 지정 정보를 제공하는 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 개체 또는 날짜 및 시간 값에 대한 형식 지정 정보를 제공하는 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 개체가 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-324">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation can return either a [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object to provide numeric formatting information or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object to provide formatting information for date and time values.</span></span> 

<span data-ttu-id="96132-325">사용자 고유의 형식 공급자를 구현하여 이러한 클래스 중 하나를 대체할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-325">You can also implement your own format provider to replace any one of these classes.</span></span> <span data-ttu-id="96132-326">그러나 `GetFormat` 메서드에 형식 지정 정보를 제공해야 하는 경우에는 구현된 형식 공급자의 `ToString` 메서드에서 위의 표에 나와 있는 형식의 개체를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-326">However, your implementation’s `GetFormat` method must return an object of the type listed in the previous table if it has to provide formatting information to the `ToString` method.</span></span>

### <a name="culture-sensitive-formatting-of-numeric-values"></a><span data-ttu-id="96132-327">숫자 값의 문화권 구분 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-327">Culture-sensitive formatting of numeric values</span></span>

<span data-ttu-id="96132-328">기본적으로 숫자 값의 형식은 문화권을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-328">By default, the formatting of numeric values is culture-sensitive.</span></span> <span data-ttu-id="96132-329">형식 지정 메서드를 호출할 때 문화권을 지정하지 않으면 현재 스레드 문화권의 형식 규칙이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-329">If you do not specify a culture when you call a formatting method, the formatting conventions of the current thread culture are used.</span></span> <span data-ttu-id="96132-330">이는 현재 스레드 문화권을 4번 변경한 후 [Decimal.ToString(String)](xref:System.Decimal.ToString(System.String)) 메서드를 호출하는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-330">This is illustrated in the following example, which changes the current thread culture four times and then calls the [Decimal.ToString(String)](xref:System.Decimal.ToString(System.String)) method.</span></span> <span data-ttu-id="96132-331">각각의 경우 결과 문자열은 현재 문화권의 형식 규칙을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-331">In each case, the result string reflects the formatting conventions of the current culture.</span></span> <span data-ttu-id="96132-332">이는 `ToString` 및 `ToString(String)` 메서드가 각 숫자 형식의 `ToString(String, IFormatProvider)` 메서드에 대한 호출을 래핑하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="96132-332">This is because the `ToString` and `ToString(String)` methods wrap calls to each numeric type's `ToString(String, IFormatProvider)` method.</span></span> 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      Decimal value = 1043.17m;

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(value.ToString("C2"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       $1,043.17
//       
//       The current culture is fr-FR
//       1 043,17 €
//       
//       The current culture is es-MX
//       $1,043.17
//       
//       The current culture is de-DE
//       1.043,17 €
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim value As Decimal = 1043.17d 

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(value.ToString("C2"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       $1,043.17
'       
'       The current culture is fr-FR
'       1 043,17 €
'       
'       The current culture is es-MX
'       $1,043.17
'       
'       The current culture is de-DE
'       1.043,17 €
```

<span data-ttu-id="96132-333">*provider* 매개 변수를 포함하는 `ToString` 오버로드를 호출하고 여기에 다음 중 하나를 전달하여 특정 문화권에 대한 숫자 값의 형식을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-333">You can also format a numeric value for a specific culture by calling a `ToString` overload that has a *provider* parameter and passing it either of the following:</span></span> 

* <span data-ttu-id="96132-334">사용할 형식 규칙이 포함된 문화권을 나타내는 [CultureInfo](xref:System.Globalization.CultureInfo) 개체.</span><span class="sxs-lookup"><span data-stu-id="96132-334">A [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the culture whose formatting conventions are to be used.</span></span> <span data-ttu-id="96132-335">해당 [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) 메서드는 숫자 값에 대한 문화권별 형식 정보를 제공하는 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 개체인 [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) 속성의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-335">Its [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns the value of the [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) property, which is the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that provides culture-specific formatting information for numeric values.</span></span>

* <span data-ttu-id="96132-336">사용할 문화권별 형식 규칙을 정의하는 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 개체.</span><span class="sxs-lookup"><span data-stu-id="96132-336">A [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that defines the culture-specific formatting conventions to be used.</span></span> <span data-ttu-id="96132-337">해당 [GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) 메서드는 자신의 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-337">Its [GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) method returns an instance of itself.</span></span>

<span data-ttu-id="96132-338">다음 예제에서는 부동 소수점 숫자의 형식을 지정하기 위해 영어(미국) 및 영어(영국) 문화권과 프랑스어 및 러시아어 중립 문화권을 나타내는 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-338">The following example uses [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) objects that represent the English (United States) and English (Great Britain) cultures and the French and Russian neutral cultures to format a floating-point number.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      Double value = 1043.62957;
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         NumberFormatInfo nfi = CultureInfo.CreateSpecificCulture(name).NumberFormat;
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 1,043.630
//       en-GB: 1,043.630
//       ru:    1 043,630
//       fr:    1 043,630
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As Double = 1043.62957
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim nfi As NumberFormatInfo = CultureInfo.CreateSpecificCulture(name).NumberFormat
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 1,043.630
'       en-GB: 1,043.630
'       ru:    1 043,630
'       fr:    1 043,630
```

### <a name="culture-sensitive-formatting-of-date-and-time-values"></a><span data-ttu-id="96132-339">날짜 및 시간 값의 문화권 구분 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-339">Culture-sensitive formatting of date and time values</span></span>

<span data-ttu-id="96132-340">기본적으로 날짜 및 시간 값의 형식은 문화권을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-340">By default, the formatting of date and time values is culture-sensitive.</span></span> <span data-ttu-id="96132-341">형식 지정 메서드를 호출할 때 문화권을 지정하지 않으면 현재 스레드 문화권의 형식 규칙이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-341">If you do not specify a culture when you call a formatting method, the formatting conventions of the current thread culture are used.</span></span> <span data-ttu-id="96132-342">이는 현재 스레드 문화권을 4번 변경한 후 [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)) 메서드를 호출하는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-342">This is illustrated in the following example, which changes the current thread culture four times and then calls the [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)) method.</span></span> <span data-ttu-id="96132-343">각각의 경우 결과 문자열은 현재 문화권의 형식 규칙을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-343">In each case, the result string reflects the formatting conventions of the current culture.</span></span> <span data-ttu-id="96132-344">이는 [DateTime.ToString()](xref:System.DateTime.ToString), [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)), [DateTimeOffset.ToString()](xref:System.DateTimeOffset.ToString(System.String)) 및 [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) 메서드가 [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) 및 [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) 메서드 호출을 래핑하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="96132-344">This is because the [DateTime.ToString()](xref:System.DateTime.ToString), [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)), [DateTimeOffset.ToString()](xref:System.DateTimeOffset.ToString(System.String)), and [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) methods wrap calls to the [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) and [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) methods.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      DateTime dateToFormat = new DateTime(2012, 5, 28, 11, 30, 0);

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(dateToFormat.ToString("F"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       Monday, May 28, 2012 11:30:00 AM
//       
//       The current culture is fr-FR
//       lundi 28 mai 2012 11:30:00
//       
//       The current culture is es-MX
//       lunes, 28 de mayo de 2012 11:30:00 a.m.
//       
//       The current culture is de-DE
//       Montag, 28. Mai 2012 11:30:00
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim dateToFormat As Date = #5/28/2012 11:30AM#

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(dateToFormat.ToString("F"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       Monday, May 28, 2012 11:30:00 AM
'       
'       The current culture is fr-FR
'       lundi 28 mai 2012 11:30:00
'       
'       The current culture is es-MX
'       lunes, 28 de mayo de 2012 11:30:00 a.m.
'       
'       The current culture is de-DE
'       Montag, 28. Mai 2012 11:30:00
```

<span data-ttu-id="96132-345">provider 매개 변수를 포함하는 [DateTime.ToString](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) 또는 [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) 오버로드를 호출하고 여기에 다음 중 하나를 전달하여 특정 문화권에 대한 날짜 및 시간 값의 형식을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-345">You can also format a date and time value for a specific culture by calling a [DateTime.ToString](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) or [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) overload that has a provider parameter and passing it either of the following:</span></span> 

* <span data-ttu-id="96132-346">사용할 형식 규칙이 포함된 문화권을 나타내는 [CultureInfo](xref:System.Globalization.CultureInfo) 개체.</span><span class="sxs-lookup"><span data-stu-id="96132-346">A [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the culture whose formatting conventions are to be used.</span></span> <span data-ttu-id="96132-347">해당 [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) 메서드는 숫자 값에 대한 문화권별 형식 정보를 제공하는 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 개체인 [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) 속성의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-347">Its [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns the value of the [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) property, which is the [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that provides culture-specific formatting information for numeric values.</span></span>

* <span data-ttu-id="96132-348">사용할 문화권별 형식 규칙을 정의하는 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 개체.</span><span class="sxs-lookup"><span data-stu-id="96132-348">A [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that defines the culture-specific formatting conventions to be used.</span></span> <span data-ttu-id="96132-349">해당 [GetFormat](xref:System.Globalization.DateTimeFormatInfo.GetFormat(System.Type)) 메서드는 자신의 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-349">Its [GetFormat](xref:System.Globalization.DateTimeFormatInfo.GetFormat(System.Type)) method returns an instance of itself.</span></span>

<span data-ttu-id="96132-350">다음 예제에서는 날짜의 형식을 지정하기 위해 영어(미국) 및 영어(영국) 문화권과 프랑스어 및 러시아어 중립 문화권을 나타내는 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-350">The following example uses [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) objects that represent the English (United States) and English (Great Britain) cultures and the French and Russian neutral cultures to format a date.</span></span> 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      DateTime dat1 = new DateTime(2012, 5, 28, 11, 30, 0);
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         DateTimeFormatInfo dtfi = CultureInfo.CreateSpecificCulture(name).DateTimeFormat;
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 5/28/2012 11:30:00 AM
//       en-GB: 28/05/2012 11:30:00
//       ru: 28.05.2012 11:30:00
//       fr: 28/05/2012 11:30:00
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dat1 As Date = #5/28/2012 11:30AM#
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim dtfi As DateTimeFormatInfo = CultureInfo.CreateSpecificCulture(name).DateTimeFormat
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 5/28/2012 11:30:00 AM
'       en-GB: 28/05/2012 11:30:00
'       ru: 28.05.2012 11:30:00
'       fr: 28/05/2012 11:30:00
```

## <a name="the-iformattable-interface"></a><span data-ttu-id="96132-351">IFormattable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="96132-351">The IFormattable interface</span></span>

<span data-ttu-id="96132-352">일반적으로 형식 문자열과 [IFormatProvider](xref:System.IFormatProvider) 매개 변수로 `ToString` 메서드를 오버로드하는 형식은 [IFormattable](xref:System.IFormattable) 인터페이스도 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-352">Typically, types that overload the `ToString` method with a format string and an [IFormatProvider](xref:System.IFormatProvider) parameter also implement the [IFormattable](xref:System.IFormattable) interface.</span></span> <span data-ttu-id="96132-353">이 인터페이스에는 형식 문자열과 형식 공급자가 매개 변수로 포함되어 있는 [IFormattable.ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)) 멤버가 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-353">This interface has a single member, [IFormattable.ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)), that includes both a format string and a format provider as parameters.</span></span>

<span data-ttu-id="96132-354">응용 프로그램 정의 클래스에 대해 [IFormattable](xref:System.IFormattable) 인터페이스를 구현하면 다음과 같은 두 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-354">Implementing the [IFormattable](xref:System.IFormattable) interface for your application-defined class offers two advantages:</span></span> 

* <span data-ttu-id="96132-355">[Convert](xref:System.Convert) 클래스를 사용한 문자열 변환을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-355">Support for string conversion by the [Convert](xref:System.Convert) class.</span></span> <span data-ttu-id="96132-356">[Convert.ToString(Object)](xref:System.Convert.ToString(System.Object)) 및 [Convert.ToString(Object, IFormatProvider)](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) 메서드를 호출하면 사용자 [IFormattable](xref:System.IFormattable) 구현이 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-356">Calls to the [Convert.ToString(Object)](xref:System.Convert.ToString(System.Object)) and [Convert.ToString(Object, IFormatProvider)](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) methods call your [IFormattable](xref:System.IFormattable) implementation automatically.</span></span>

* <span data-ttu-id="96132-357">복합 형식 지정을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-357">Support for composite formatting.</span></span> <span data-ttu-id="96132-358">형식 문자열을 포함한 형식 항목을 사용하여 사용자 지정 형식의 서식을 지정하는 경우 공용 언어 런타임에서 자동으로 사용자 [IFormattable](xref:System.IFormattable) 구현을 호출하고 형식 문자열을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-358">If a format item that includes a format string is used to format your custom type, the Common Language Runtime automatically calls your [IFormattable](xref:System.IFormattable) implementation and passes it the format string.</span></span> <span data-ttu-id="96132-359">`String.Format` 또는 `Console.WriteLine` 같은 메서드를 사용하는 복합 서식 지정에 대한 자세한 내용은 [복합 서식 지정](#composite-formatting) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-359">For more information about composite formatting with methods such as `String.Format` or `Console.WriteLine`, see the [Composite formatting](#composite-formatting) section.</span></span>

<span data-ttu-id="96132-360">다음 예제에서는 [IFormattable](xref:System.IFormattable) 인터페이스를 구현하는 `Temperature` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-360">The following example defines a `Temperature` class that implements the [IFormattable](xref:System.IFormattable) interface.</span></span> <span data-ttu-id="96132-361">이 클래스는 온도를 섭씨로 표시하는 "C" 또는 "G" 형식 지정자, 온도를 화씨로 표시하는 "F" 형식 지정자 또는 온도를 켈빈으로 표시하는 "K" 형식 지정자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-361">It supports the "C" or "G" format specifiers to display the temperature in Celsius, the "F" format specifier to display the temperature in Fahrenheit, and the "K" format specifier to display the temperature in Kelvin.</span></span>

```csharp
using System;
using System.Globalization;

public class Temperature : IFormattable
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round((decimal) this.m_Temp * 9 / 5 + 32, 2); }
   }

   public override string ToString()
   {
      return this.ToString("G", null);
   }

   public string ToString(string format)
   {
      return this.ToString(format, null);
   }

   public string ToString(string format, IFormatProvider provider)  
   {
      // Handle null or empty arguments.
      if (String.IsNullOrEmpty(format)) format = "G";
      // Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant();

      if (provider == null) provider = NumberFormatInfo.CurrentInfo;

      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2", provider) + "°F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2", provider) + "K";
         // Return temperature in Celsius.
         case "C":
         case "G":
            return this.Celsius.ToString("N2", provider) + "°C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}
```

```vb
Imports System.Globalization

Public Class Temperature : Implements IFormattable
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("G", Nothing)
   End Function

   Public Overloads Function ToString(format As String) As String
      Return Me.ToString(format, Nothing)
   End Function

   Public Overloads Function ToString(format As String, provider As IFormatProvider) As String _  
      Implements IFormattable.ToString

      ' Handle null or empty arguments.
      If String.IsNullOrEmpty(format) Then format = "G"
      ' Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant()

      If provider Is Nothing Then provider = NumberFormatInfo.CurrentInfo

      Select Case format
         ' Convert temperature to Fahrenheit and return string.
         Case "F"
            Return Me.Fahrenheit.ToString("N2", provider) & "°F"
         ' Convert temperature to Kelvin and return string.
         Case "K"
            Return Me.Kelvin.ToString("N2", provider) & "K"
         ' Return temperature in Celsius.
         Case "C", "G"
            Return Me.Celsius.ToString("N2", provider) & "°C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class
```

<span data-ttu-id="96132-362">다음 예제에서는 `Temperature` 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-362">The following example instantiates a `Temperature` object.</span></span> <span data-ttu-id="96132-363">그런 다음 [ToString](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) 메서드를 호출하고 여러 복합 형식 문자열을 사용하여 `Temperature` 개체의 다양한 문자열 표현을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-363">It then calls the [ToString](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) method and uses several composite format strings to obtain different string representations of a `Temperature` object.</span></span> <span data-ttu-id="96132-364">이 메서드를 호출할 때마다 자동으로 `Temperature` 클래스의 [IFormattable](xref:System.IFormattable) 구현도 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-364">Each of these method calls, in turn, calls the [IFormattable](xref:System.IFormattable) implementation of the `Temperature` class.</span></span>

```csharp
public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(22m);
      Console.WriteLine(Convert.ToString(temp1, new CultureInfo("ja-JP")));
      Console.WriteLine("Temperature: {0:K}", temp1);
      Console.WriteLine("Temperature: {0:F}", temp1);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), "Temperature: {0:F}", temp1));
   }
}
// The example displays the following output:
//       22.00°C
//       Temperature: 295.15°K
//       Temperature: 71.60°F
//       Temperature: 71,60°F
```

```vb
Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(22d)
      Console.WriteLine(Convert.ToString(temp1, New CultureInfo("ja-JP")))
      Console.WriteLine("Temperature: {0:K}", temp1)
      Console.WriteLine("Temperature: {0:F}", temp1)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), "Temperature: {0:F}", temp1)) 
   End Sub
End Module
' The example displays the following output:
'       22.00°C
'       Temperature: 295.15°K
'       Temperature: 71.60°F
'       Temperature: 71,60°F
```

## <a name="composite-formatting"></a><span data-ttu-id="96132-365">복합 형식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-365">Composite formatting</span></span>

<span data-ttu-id="96132-366">`String.Format` 및 `StringBuilder.AppendFormat` 같은 일부 메서드는 복합 형식 지정을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-366">Some methods, such as `String.Format` and `StringBuilder.AppendFormat`, support composite formatting.</span></span> <span data-ttu-id="96132-367">복합 형식 문자열은 0개 이상의 개체에 대한 문자열 표현이 통합된 단일 문자열을 반환하는 일종의 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="96132-367">A composite format string is a kind of template that returns a single string that incorporates the string representation of zero, one, or more objects.</span></span> <span data-ttu-id="96132-368">복합 형식 문자열에서는 각 개체가 인덱싱된 형식 항목으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-368">Each object is represented in the composite format string by an indexed format item.</span></span> <span data-ttu-id="96132-369">형식 항목의 인덱스는 메서드의 매개 변수 목록에 표시되는 개체의 위치에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-369">The index of the format item corresponds to the position of the object that it represents in the method's parameter list.</span></span> <span data-ttu-id="96132-370">인덱스는 0에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-370">Indexes are zero-based.</span></span> <span data-ttu-id="96132-371">예를 들어 다음과 같은 `String.Format` 메서드 호출에서 첫 번째 형식 항목인 `{0:D}`는 `thatDate`의 문자열 표현으로 바뀌고, 두 번째 형식 항목인 `{1}`은 `item1`의 문자열 표현으로 바뀌고, 세 번째 형식 항목인 `{2:C2}`는 `item1.Value`의 문자열 표현으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="96132-371">For example, in the following call to the `String.Format` method, the first format item, `{0:D}`, is replaced by the string representation of `thatDate`; the second format item, `{1}`, is replaced by the string representation of `item1`; and the third format item, `{2:C2}`, is replaced by the string representation of `item1.Value`.</span></span>

```csharp
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", 
                       thatDate, item1, item1.Value);
Console.WriteLine(result);                            
// The example displays output like the following if run on a system
// whose current culture is en-US:
//       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

```vb
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", _
                       thatDate, item1, item1.Value)
Console.WriteLine(result)                            
' The example displays output like the following if run on a system
' whose current culture is en-US:
'       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

<span data-ttu-id="96132-372">형식 항목을 해당 개체의 문자열 표현으로 바꾸는 것 외에도 형식 항목을 통해 다음을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-372">In addition to replacing a format item with the string representation of its corresponding object, format items also let you control the following:</span></span> 

* <span data-ttu-id="96132-373">개체가 [IFormattable](xref:System.IFormattable) 인터페이스를 구현하고 형식 문자열을 지원하는 경우 개체가 문자열로 표현되는 특정 방식.</span><span class="sxs-lookup"><span data-stu-id="96132-373">The specific way in which an object is represented as a string, if the object implements the [IFormattable](xref:System.IFormattable) interface and supports format strings.</span></span> <span data-ttu-id="96132-374">이렇게 하려면 형식 항목의 인덱스 뒤에 :(콜론) 및 유효한 형식 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-374">You do this by following the format item's index with a : (colon) followed by a valid format string.</span></span> <span data-ttu-id="96132-375">이전 예제에서는 날짜 값의 형식을 "d"(짧은 날짜 패턴) 형식 문자열(예: `{0:d}`)로 지정하고 숫자 값의 형식을 "C2" 형식 문자열(예: `{2:C2}`)로 지정하여 소수 두 자리의 통화 값으로 숫자를 나타냈습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-375">The previous example did this by formatting a date value with the "d" (short date pattern) format string (for example, `{0:d}`) and by formatting a numeric value with the "C2" format string (for example, `{2:C2}` to represent the number as a currency value with two fractional decimal digits).</span></span> 

* <span data-ttu-id="96132-376">개체의 문자열 표현을 포함하는 필드의 너비 및 해당 필드의 문자열 표현 맞춤.</span><span class="sxs-lookup"><span data-stu-id="96132-376">The width of the field that contains the object's string representation, and the alignment of the string representation in that field.</span></span> <span data-ttu-id="96132-377">이렇게 하려면 형식 항목의 인덱스 뒤에 ,(쉼표) 및 필드 너비를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-377">You do this by following the format item's index with a , (comma) followed the field width.</span></span> <span data-ttu-id="96132-378">필드 너비가 양수 값이면 문자열이 필드에 오른쪽 맞춤되고, 필드 너비가 음수 값이면 왼쪽 맞춤됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-378">The string is right-aligned in the field if the field width is a positive value, and it is left-aligned if the field width is a negative value.</span></span> <span data-ttu-id="96132-379">다음 예제에서는 날짜 값을 20자 필드에 왼쪽 맞춤하고, 소수 1자리의 10진수 값을 11자 필드에 오른쪽 맞춤합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-379">The following example left-aligns date values in a 20-character field, and it right-aligns decimal values with one fractional digit in an 11-character field.</span></span> 

```csharp
DateTime startDate = new DateTime(2015, 8, 28, 6, 0, 0);
decimal[] temps = { 73.452m, 68.98m, 72.6m, 69.24563m,
                   74.1m, 72.156m, 72.228m };
Console.WriteLine("{0,-20} {1,11}\n", "Date", "Temperature");
for (int ctr = 0; ctr < temps.Length; ctr++)
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps[ctr]);

// The example displays the following output:
//       Date                 Temperature
//
//       8/28/2015 6:00 AM           73.5
//       8/29/2015 6:00 AM           69.0
//       8/30/2015 6:00 AM           72.6
//       8/31/2015 6:00 AM           69.2
//       9/1/2015 6:00 AM            74.1
//       9/2/2015 6:00 AM            72.2
//       9/3/2015 6:00 AM            72.2
```

```vb
Dim startDate As New Date(2015, 8, 28, 6, 0, 0)
Dim temps() As Decimal = { 73.452, 68.98, 72.6, 69.24563,
                           74.1, 72.156, 72.228 }
Console.WriteLine("{0,-20} {1,11}", "Date", "Temperature")
Console.WriteLine()
For ctr As Integer = 0 To temps.Length - 1
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps(ctr))
Next
' The example displays the following output:
'       Date                 Temperature
'
'       8/28/2015 6:00 AM           73.5
'       8/29/2015 6:00 AM           69.0
'       8/30/2015 6:00 AM           72.6
'       8/31/2015 6:00 AM           69.2
'       9/1/2015 6:00 AM            74.1
'       9/2/2015 6:00 AM            72.2
'       9/3/2015 6:00 AM            72.2
```

<span data-ttu-id="96132-380">맞춤 문자열 구성 요소와 형식 문자열 구성 요소가 둘 다 있는 경우 맞춤 문자열 구성 요소가 우선합니다(예: `{0,-20:g}`).</span><span class="sxs-lookup"><span data-stu-id="96132-380">Note that, if both the alignment string component and the format string component are present, the former precedes the latter (for example, `{0,-20:g}`.</span></span> 

<span data-ttu-id="96132-381">복합 서식 지정에 대한 자세한 내용은 [복합 서식 지정](composite-format.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96132-381">For more information about composite formatting, see [Composite formatting](composite-format.md).</span></span>

## <a name="custom-formatting-with-icustomformatter"></a><span data-ttu-id="96132-382">ICustomFormatter를 사용한 사용자 지정 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-382">Custom formatting with ICustomFormatter</span></span>

<span data-ttu-id="96132-383">두 복합 형식 지정 메서드 [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object[])) 및 [StringBuilder.AppendFormat(IFormatProvider, String, Object[])](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))에는 사용자 지정 형식 지정을 지원하는 형식 공급자 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-383">Two composite formatting methods, [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object[])) and [StringBuilder.AppendFormat(IFormatProvider, String, Object[])](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)), include a format provider parameter that supports custom formatting.</span></span> <span data-ttu-id="96132-384">이러한 형식 지정 메서드 중 하나를 호출하면 [ICustomFormatter](xref:System.ICustomFormatter) 인터페이스를 나타내는 [Type](xref:System.Type) 개체가 형식 공급자의 `GetFormat` 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-384">When either of these formatting methods is called, it passes a [Type](xref:System.Type) object that represents an [ICustomFormatter](xref:System.ICustomFormatter) interface to the format provider’s `GetFormat` method.</span></span> <span data-ttu-id="96132-385">그러면 `GetFormat` 메서드가 사용자 지정 형식 지정을 제공하는 [ICustomFormatter](xref:System.ICustomFormatter) 구현을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-385">The `GetFormat` method is then responsible for returning the [ICustomFormatter](xref:System.ICustomFormatter) implementation that provides custom formatting.</span></span>

<span data-ttu-id="96132-386">[ICustomFormatter](xref:System.ICustomFormatter) 인터페이스에는 복합 형식 지정 메서드에 의해 자동으로 복합 형식 문자열의 각 형식 항목마다 한 번씩 호출되는 [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) 메서드가 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-386">The [ICustomFormatter](xref:System.ICustomFormatter) interface has a single method, [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)), that is called automatically by a composite formatting method, once for each format item in a composite format string.</span></span> <span data-ttu-id="96132-387">[Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) 메서드에는 세 개의 매개 변수, 즉 형식 항목의 *formatString* 인수를 나타내는 형식 문자열, 형식을 지정할 개체 및 형식 지정 서비스를 제공하는 [IFormatProvider](xref:System.IFormatProvider) 개체가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-387">The [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method has three parameters: a format string, which represents the *formatString* argument in a format item, an object to format, and an [IFormatProvider](xref:System.IFormatProvider) object that provides formatting services.</span></span> <span data-ttu-id="96132-388">일반적으로 [ICustomFormatter](xref:System.ICustomFormatter)를 구현하는 클래스는 [IFormatProvider](xref:System.IFormatProvider)도 구현하여 이 마지막 매개 변수가 사용자 지정 형식 지정 클래스를 참조하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-388">Typically, the class that implements [ICustomFormatter](xref:System.ICustomFormatter) also implements [IFormatProvider](xref:System.IFormatProvider), so this last parameter is a reference to the custom formatting class itself.</span></span> <span data-ttu-id="96132-389">이 메서드는 형식을 지정할 개체의 사용자 지정 형식 문자열 표현을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-389">The method returns a custom formatted string representation of the object to be formatted.</span></span> <span data-ttu-id="96132-390">이 메서드가 개체의 형식을 지정할 수 없는 경우에는 null 참조가 반환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-390">If the method cannot format the object, it should return a null reference.</span></span>

<span data-ttu-id="96132-391">다음 예제에서는 정수 값을 뒤에 공백이 오는 두 자리 16진수 값 시퀀스로 표시하는 `ByteByByteFormatter`라는 [ICustomFormatter](xref:System.ICustomFormatter) 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-391">The following example provides an [ICustomFormatter](xref:System.ICustomFormatter) implementation named `ByteByByteFormatter` that displays integer values as a sequence of two-digit hexadecimal values followed by a space.</span></span>

```csharp
public class ByteByByteFormatter : IFormatProvider, ICustomFormatter
{
   public object GetFormat(Type formatType)
   { 
      if (formatType == typeof(ICustomFormatter))
         return this;
      else
         return null;
   }

   public string Format(string format, object arg, 
                          IFormatProvider formatProvider)
   {   
      if (! formatProvider.Equals(this)) return null;

      // Handle only hexadecimal format string.
      if (! format.StartsWith("X")) return null;

      byte[] bytes;
      string output = null;

      // Handle only integral types.
      if (arg is Byte) 
         bytes = BitConverter.GetBytes((Byte) arg);
      else if (arg is Int16)
         bytes = BitConverter.GetBytes((Int16) arg);
      else if (arg is Int32)
         bytes = BitConverter.GetBytes((Int32) arg);
      else if (arg is Int64)   
         bytes = BitConverter.GetBytes((Int64) arg);
      else if (arg is SByte)
         bytes = BitConverter.GetBytes((SByte) arg);
      else if (arg is UInt16)
         bytes = BitConverter.GetBytes((UInt16) arg);
      else if (arg is UInt32)
         bytes = BitConverter.GetBytes((UInt32) arg);
      else if (arg is UInt64)
         bytes = BitConverter.GetBytes((UInt64) arg);
      else
         return null;

      for (int ctr = bytes.Length - 1; ctr >= 0; ctr--)
         output += String.Format("{0:X2} ", bytes[ctr]);   

      return output.Trim();
   }
}
```

```vb
Public Class ByteByByteFormatter : Implements IFormatProvider, ICustomFormatter
   Public Function GetFormat(formatType As Type) As Object _
                   Implements IFormatProvider.GetFormat
      If formatType Is GetType(ICustomFormatter) Then
         Return Me
      Else
         Return Nothing
      End If
   End Function

   Public Function Format(fmt As String, arg As Object, 
                          formatProvider As IFormatProvider) As String _
                          Implements ICustomFormatter.Format

      If Not formatProvider.Equals(Me) Then Return Nothing

      ' Handle only hexadecimal format string.
      If Not fmt.StartsWith("X") Then 
            Return Nothing
      End If

      ' Handle only integral types.
      If Not typeof arg Is Byte AndAlso
         Not typeof arg Is Int16 AndAlso
         Not typeof arg Is Int32 AndAlso
         Not typeof arg Is Int64 AndAlso
         Not typeof arg Is SByte AndAlso
         Not typeof arg Is UInt16 AndAlso
         Not typeof arg Is UInt32 AndAlso
         Not typeof arg Is UInt64 Then _
            Return Nothing

      Dim bytes() As Byte = BitConverter.GetBytes(arg)
      Dim output As String = Nothing

      For ctr As Integer = bytes.Length - 1 To 0 Step -1
         output += String.Format("{0:X2} ", bytes(ctr))   
      Next

      Return output.Trim()
   End Function
End Class
```

<span data-ttu-id="96132-392">다음 예제에서는 `ByteByByteFormatter` 클래스를 사용하여 정수 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-392">The following example uses the `ByteByByteFormatter` class to format integer values.</span></span> <span data-ttu-id="96132-393">[ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) 메서드는 두 번째 [String.Format(IFormatProvider, String, Object[])](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) 메서드 호출에서 두 번 이상 호출되고 `.ByteByByteFormatter.Format` 메서드가 "N0" 형식 문자열을 인식하지 못하고 null 참조를 반환하기 때문에 세 번째 메서드 호출에서는 기본 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 공급자가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-393">Note that the [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method is called more than once in the second [String.Format(IFormatProvider, String, Object[])](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method call, and that the default [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) provider is used in the third method call because the `.ByteByByteFormatter.Format` method does not recognize the "N0" format string and returns a null reference.</span></span>

```csharp
public class Example
{
   public static void Main()
   {
      long value = 3210662321; 
      byte value1 = 214;
      byte value2 = 19;

      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X}", value));
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 & value2));                                
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0,10:N0}", value));
   }
}
// The example displays the following output:
//       00 00 00 00 BF 5E D1 B1
//       00 D6 And 00 13 = 00 12 (018)
//       3,210,662,321
```

```vb
Public Module Example
   Public Sub Main()
      Dim value As Long = 3210662321 
      Dim value1 As Byte = 214
      Dim value2 As Byte = 19

      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X}", value)))
      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 And value2)))                                
      Console.WriteLine(String.Format(New ByteByByteFormatter(), "{0,10:N0}", value))
   End Sub
End Module
' The example displays the following output:
'       00 00 00 00 BF 5E D1 B1
'       00 D6 And 00 13 = 00 12 (018)
'       3,210,662,321
```

## <a name="related-topics"></a><span data-ttu-id="96132-394">관련 항목</span><span class="sxs-lookup"><span data-stu-id="96132-394">Related topics</span></span>

<span data-ttu-id="96132-395">제목</span><span class="sxs-lookup"><span data-stu-id="96132-395">Title</span></span> | <span data-ttu-id="96132-396">정의</span><span class="sxs-lookup"><span data-stu-id="96132-396">Definition</span></span>
----- | ----------
[<span data-ttu-id="96132-397">표준 숫자 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-397">Standard numeric format strings</span></span>](standard-numeric.md) | <span data-ttu-id="96132-398">숫자 값의 일반적으로 사용되는 문자열 표현을 만드는 표준 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-398">Describes standard format strings that create commonly used string representations of numeric values.</span></span> 
[<span data-ttu-id="96132-399">사용자 지정 숫자 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-399">Custom numeric format strings</span></span>](custom-numeric.md) | <span data-ttu-id="96132-400">숫자 값의 응용 프로그램별 형식을 만드는 사용자 지정 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-400">Describes custom format strings that create application-specific formats for numeric values.</span></span>
[<span data-ttu-id="96132-401">표준 날짜 및 시간 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-401">Standard date and time format strings</span></span>](standard-datetime.md) |  <span data-ttu-id="96132-402">[DateTime](xref:System.DateTime) 값의 일반적으로 사용되는 문자열 표현을 만드는 표준 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-402">Describes standard format strings that create commonly used string representations of [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="96132-403">사용자 지정 날짜 및 시간 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-403">Custom date and time format strings</span></span>](custom-datetime.md) | <span data-ttu-id="96132-404">[DateTime](xref:System.DateTime) 값의 응용 프로그램별 형식을 만드는 사용자 지정 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-404">Describes custom format strings that create application-specific formats for [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="96132-405">표준 TimeSpan 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-405">Standard TimeSpan format strings</span></span>](standard-timespan.md) | <span data-ttu-id="96132-406">시간 간격의 일반적으로 사용되는 문자열 표현을 만드는 표준 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-406">Describes standard format strings that create commonly used string representations of time intervals.</span></span>
[<span data-ttu-id="96132-407">사용자 지정 TimeSpan 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-407">Custom TimeSpan format strings</span></span>](custom-timespan.md) | <span data-ttu-id="96132-408">시간 간격의 응용 프로그램별 형식을 만드는 사용자 지정 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-408">Describes custom format strings that create application-specific formats for time intervals.</span></span>
[<span data-ttu-id="96132-409">열거형 서식 문자열</span><span class="sxs-lookup"><span data-stu-id="96132-409">Enumeration format strings</span></span>](enumeration-format.md) | <span data-ttu-id="96132-410">열거형 값의 문자열 표현을 만드는 데 사용되는 표준 형식 문자열에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-410">Describes standard format strings that are used to create string representations of enumeration values.</span></span>
[<span data-ttu-id="96132-411">복합 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96132-411">Composite formatting</span></span>](composite-format.md) | <span data-ttu-id="96132-412">문자열에 형식이 지정된 하나 이상의 값을 포함시키는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-412">Describes how to embed one or more formatted values in a string.</span></span> <span data-ttu-id="96132-413">그런 후 해당 문자열을 콘솔에 표시하거나 스트림에 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96132-413">The string can subsequently be displayed on the console or written to a stream.</span></span>
[<span data-ttu-id="96132-414">서식 지정 작업 수행</span><span class="sxs-lookup"><span data-stu-id="96132-414">Performing formatting operations</span></span>](performing-formatting-operations.md) | <span data-ttu-id="96132-415">특정 형식 지정 작업을 수행하기 위한 단계별 지침을 제공하는 항목을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-415">Lists topics that provide step-by-step instructions for performing specific formatting operations.</span></span>
[<span data-ttu-id="96132-416">문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="96132-416">Parsing strings</span></span>](parsing-strings.md) | <span data-ttu-id="96132-417">개체를 해당 개체의 문자열 표현으로 표시되는 값으로 초기화하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96132-417">Describes how to initialize objects to the values described by string representations of those objects.</span></span> <span data-ttu-id="96132-418">구문 분석은 형식 지정의 역순으로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="96132-418">Parsing is the inverse operation of formatting.</span></span>

## <a name="reference"></a><span data-ttu-id="96132-419">참조</span><span class="sxs-lookup"><span data-stu-id="96132-419">Reference</span></span>

[<span data-ttu-id="96132-420">System.IFormattable</span><span class="sxs-lookup"><span data-stu-id="96132-420">System.IFormattable</span></span>](xref:System.IFormattable)

[<span data-ttu-id="96132-421">System.IFormatProvider</span><span class="sxs-lookup"><span data-stu-id="96132-421">System.IFormatProvider</span></span>](xref:System.IFormatProvider)

[<span data-ttu-id="96132-422">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="96132-422">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)

