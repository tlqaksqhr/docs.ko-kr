---
title: ".NET에서 날짜 및 시간 문자열 구문 분석"
description: ".NET에서 날짜 및 시간 문자열 구문 분석"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e61514cd-5329-4eb8-b122-482fffb54ab7
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f0131baa0874880b6697458426da5ae9ce1705b7
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-date-and-time-strings-in-net"></a><span data-ttu-id="dd117-104">.NET에서 날짜 및 시간 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="dd117-104">Parsing date and time strings in .NET</span></span>

<span data-ttu-id="dd117-105">구문 분석 메서드는 날짜 및 시간의 지정된 문자열 표현을 해당하는 [DateTime](xref:System.DateTime) 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-105">Parsing methods convert the string representation of a date and time to an equivalent [DateTime](xref:System.DateTime) object.</span></span> <span data-ttu-id="dd117-106">[Parse](xref:System.DateTime.Parse(System.String)) 및 [TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) 메서드는 날짜와 시간의 몇 가지 공통된 표현을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-106">The [Parse](xref:System.DateTime.Parse(System.String)) and [TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) methods convert any of several common representations of a date and time.</span></span> <span data-ttu-id="dd117-107">[ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) 및 [TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)) 메서드는 날짜 및 시간 서식 문자열에 지정된 패턴을 따르는 문자열 표현을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-107">The [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) and [TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)) methods convert a string representation that conforms to the pattern specified by a date and time format string.</span></span> <span data-ttu-id="dd117-108">[표준 날짜 및 시간 서식 문자열](standard-datetime.md) 및 [사용자 지정 날짜 및 시간 서식 문자열](custom-datetime.md)의 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd117-108">(See the topics on [standard date and time format strings](standard-datetime.md) and [custom date and time format strings](custom-datetime.md).)</span></span> 

<span data-ttu-id="dd117-109">구문 분석은 날짜 및 시간 구분 기호와 월, 일 및 연대의 이름에 사용되는 문자열과 같은 정보를 제공하는 서식 공급자의 속성에 의해 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-109">Parsing is influenced by the properties of a format provider that supplies information such as the strings used for date and time separators, and the names of months, days, and eras.</span></span> <span data-ttu-id="dd117-110">서식 공급자는 현재 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 개체이며 현재 스레드 문화권에 의해 암시적으로 제공되거나 구문 분석 메서드의 [IFormatProvider](xref:System.IFormatProvider) 매개 변수에 의해 명시적으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-110">The format provider is the current [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object, which is provided implicitly by the current thread culture or explicitly by the [IFormatProvider](xref:System.IFormatProvider) parameter of a parsing method.</span></span> <span data-ttu-id="dd117-111">[IFormatProvider](xref:System.IFormatProvider) 매개 변수의 경우 문화권 또는 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 개체를 나타내는 [CultureInfo](xref:System.Globalization.CultureInfo) 개체를 지정합니다..</span><span class="sxs-lookup"><span data-stu-id="dd117-111">For the [IFormatProvider](xref:System.IFormatProvider) parameter, specify a [CultureInfo](xref:System.Globalization.CultureInfo) object, which represents a culture, or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object.</span></span> 

<span data-ttu-id="dd117-112">구문 분석될 날짜의 문자열 표현은 월을 포함해야 하고 적어도 날이나 연도를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-112">The string representation of a date to be parsed must include the month and at least a day or year.</span></span> <span data-ttu-id="dd117-113">시간의 문자열 표현은 시간을 포함해야 하고 적어도 분이나 AM/PM 지정자를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-113">The string representation of a time must include the hour and at least minutes or the AM/PM designator.</span></span> <span data-ttu-id="dd117-114">하지만 가능한 경우 구문 분석은 생략된 구성 요소에 대한 기본값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-114">However, parsing supplies default values for omitted components if possible.</span></span> <span data-ttu-id="dd117-115">누락된 날짜는 기본값으로 현재 날짜를 사용하고 누락된 연도는 현재 연도를 사용하며 누락된 월의 날은 월의 첫 번째 날을 사용하고 누락된 시간은 자정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-115">A missing date defaults to the current date, a missing year defaults to the current year, a missing day of the month defaults to the first day of the month, and a missing time defaults to midnight.</span></span> 

<span data-ttu-id="dd117-116">문자열 표현이 시간만을 지정한 경우 구문 분석은 [Today](xref:System.DateTime.Today) 속성에 해당하는 값으로 설정된 [Year](xref:System.DateTime.Year), [Month](xref:System.DateTime.Month) 및 [Day](xref:System.DateTime.Day) 속성을 가진 [DateTime](xref:System.DateTime) 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-116">If the string representation specifies only a time, parsing returns a [DateTime](xref:System.DateTime) object with its [Year](xref:System.DateTime.Year), [Month](xref:System.DateTime.Month), and [Day](xref:System.DateTime.Day) properties set to the corresponding values of the [Today](xref:System.DateTime.Today) property.</span></span> <span data-ttu-id="dd117-117">그러나 [DateTimeStyles.NoCurrentDateDefault](xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault) 상수가 구문 분석 메서드에서 지정된 경우 결과인 연도, 월 및 일 속성이 1로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-117">However, if the [DateTimeStyles.NoCurrentDateDefault](xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault) constant is specified in the parsing method, the resulting year, month, and day properties are set to the value 1.</span></span>

<span data-ttu-id="dd117-118">날짜 및 시간 구성 요소 외에도 날짜 및 시간의 문자열 표현은 시간이 UTC(협정 세계시)와 얼마나 다른지를 나타내는 오프셋을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-118">In addition to a date and a time component, the string representation of a date and time can include an offset that indicates how much the time differs from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="dd117-119">예를 들어, 문자열 "2/14/2007 5:32:00 -7:00"는 UTC보다 7시간 이전인 시간을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-119">For example, the string "2/14/2007 5:32:00 -7:00" defines a time that is seven hours earlier than UTC.</span></span> <span data-ttu-id="dd117-120">오프셋을 시간의 문자열 표현에서 생략하면 구문 분석은 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)으로 설정된 해당 [Kind](xref:System.DateTime.Kind) 속성과 [DateTime](xref:System.DateTime) 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-120">If an offset is omitted from the string representation of a time, parsing returns a [DateTime](xref:System.DateTime) object with its [Kind](xref:System.DateTime.Kind) property set to [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span> <span data-ttu-id="dd117-121">오프셋을 지정하면 구문 분석은 [로컬](xref:System.DateTimeKind.Local)로 설정된 [Kind](xref:System.DateTime.Kind) 속성 및 컴퓨터의 현지 표준 시간대로 조정된 해당 값과 [DateTime](xref:System.DateTime) 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-121">If an offset is specified, parsing returns a [DateTime](xref:System.DateTime) object with its [Kind](xref:System.DateTime.Kind) property set to [Local](xref:System.DateTimeKind.Local) and its value adjusted to the local time zone of your machine.</span></span> <span data-ttu-id="dd117-122">구문 분석 메서드와 [DateTimeStyles](xref:System.Globalization.DateTimeStyles) 상수를 사용하여 이 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-122">You can modify this behavior by using a [DateTimeStyles](xref:System.Globalization.DateTimeStyles) constant with the parsing method.</span></span>

<span data-ttu-id="dd117-123">서식 공급자는 모호한 날짜를 해석하는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-123">The format provider is also used to interpret an ambiguous numeric date.</span></span> <span data-ttu-id="dd117-124">예를 들어 "02/03/04" 문자열에서 나타내는 날짜의 구성 요소 중 무엇이 월, 일 및 연도인지가 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-124">For example, it is not clear which components of the date represented by the string "02/03/04" are the month, day, and year.</span></span> <span data-ttu-id="dd117-125">이 경우에 구성 요소는 서식 공급자에서 비슷한 날짜 서식의 순서에 따라 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-125">In this case, the components are interpreted according to the order of similar date formats in the format provider.</span></span> 

## <a name="parse"></a><span data-ttu-id="dd117-126">구문 분석</span><span class="sxs-lookup"><span data-stu-id="dd117-126">Parse</span></span>

<span data-ttu-id="dd117-127">다음 코드 예제에서는 문자열을 `DateTime`로 변환하는 `Parse` 메서드를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-127">The following code example illustrates the use of the `Parse` method to convert a string into a `DateTime`.</span></span> <span data-ttu-id="dd117-128">이 예제에서는 현재 스레드와 연결된 문화권을 사용하여 구문 분석을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-128">This example uses the culture associated with the current thread to perform the parse.</span></span> <span data-ttu-id="dd117-129">현재 문화권과 연결된 [CultureInfo](xref:System.Globalization.CultureInfo)가 입력 문자열을 구문 분석할 수 없는 경우 [FormatException](xref:System.FormatException)이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-129">If the [CultureInfo](xref:System.Globalization.CultureInfo) associated with the current culture cannot parse the input string, a [FormatException](xref:System.FormatException) is thrown.</span></span>

```csharp
string MyString = "Jan 1, 2009";
DateTime MyDateTime = DateTime.Parse(MyString);
Console.WriteLine(MyDateTime);
// Displays the following output on a system whose culture is en-US:
//       1/1/2009 12:00:00 AM
```

```vb
Dim MyString As String = "Jan 1, 2009"
Dim MyDateTime As DateTime = DateTime.Parse(MyString)
Console.WriteLine(MyDateTime)
' Displays the following output on a system whose culture is en-US:
'       1/1/2009 12:00:00 AM
```

<span data-ttu-id="dd117-130">`CultureInfo`을 해당 개체에서 정의하는 문화권 중 하나로 설정하거나 [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) 속성에서 반환하는 표준 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 개체 중 하나를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-130">You can also specify a `CultureInfo` set to one of the cultures defined by that object, or you can specify one of the standard [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) objects returned by the [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) property.</span></span> <span data-ttu-id="dd117-131">다음 코드 예제에서는 서식 공급자를 사용하여 독일어 문자열을 `DateTime`로 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-131">The following code example uses a format provider to parse a German string into a `DateTime`.</span></span> <span data-ttu-id="dd117-132">de-DE 문화권을 나타내는 `CultureInfo`은 구문 분석 중인 문자열과 함께 정의되고 전달되어 이 특정 문자열의 구문 분석이 성공하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-132">A `CultureInfo` representing the de-DE culture is defined and passed with the string being parsed to ensure successful parsing of this particular string.</span></span> <span data-ttu-id="dd117-133">그러면 `CurrentThread`의 `CurrentCulture`에 있는 모든 설정이 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-133">This precludes whatever setting is in the `CurrentCulture` of the `CurrentThread`.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("de-DE");
      string MyString = "12 Juni 2008";
      DateTime MyDateTime = DateTime.Parse(MyString, MyCultureInfo);
      Console.WriteLine(MyDateTime);
   }
}
// The example displays the following output:
//       6/12/2008 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("de-DE")
      Dim MyString As String = "12 Juni 2008"
      Dim MyDateTime As DateTime = DateTime.Parse(MyString, MyCultureInfo)
      Console.WriteLine(MyDateTime)
   End Sub
End Module
' The example displays the following output:
'       6/12/2008 12:00:00 AM
```

<span data-ttu-id="dd117-134">그러나 [Parse](xref:System.DateTime.Parse(System.String)) 메서드의 오버로드를 사용하여 사용자 지정 서식 공급자를 지정할 수 있지만 이 메서드는 비표준 서식 공급자를 사용하도록 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-134">However, although you can use overloads of the [Parse](xref:System.DateTime.Parse(System.String)) method to specify custom format providers, the method does not support the use of non-standard format providers.</span></span> <span data-ttu-id="dd117-135">비표준 서식으로 표현된 날짜 및 시간을 구문 분석하려면 대신 [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-135">To parse a date and time expressed in a non-standard format, use the [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method instead.</span></span>

<span data-ttu-id="dd117-136">다음 코드 예제에서는 [DateTimeStyles](xref:System.Globalization.DateTimeStyles) 열거형을 사용하여 현재 날짜 및 시간 정보를 문자열에서 정의하지 않는 필드의 `DateTime`에 추가하지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-136">The following code example uses the [DateTimeStyles](xref:System.Globalization.DateTimeStyles) enumeration to specify that the current date and time information should not be added to the `DateTime` for fields that the string does not define.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("de-DE");
      string MyString = "12 Juni 2008";
      DateTime MyDateTime = DateTime.Parse(MyString, MyCultureInfo, 
                                           DateTimeStyles.NoCurrentDateDefault);
      Console.WriteLine(MyDateTime);
   }
}
// The example displays the following output if the current culture is en-US:
//      6/12/2008 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("de-DE")
      Dim MyString As String = "12 Juni 2008"
      Dim MyDateTime As DateTime = DateTime.Parse(MyString, MyCultureInfo)
      Console.WriteLine(MyDateTime)
   End Sub
End Module
' The example displays the following output:
'       6/12/2008 12:00:00 AM
```

## <a name="parseexact"></a><span data-ttu-id="dd117-137">ParseExact</span><span class="sxs-lookup"><span data-stu-id="dd117-137">ParseExact</span></span>

<span data-ttu-id="dd117-138">[DateTime.ParseExact]((xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) 메서드는 지정 된 문자열 패턴을 따르는 문자열을 `DateTime` 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-138">The [DateTime.ParseExact]((xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method converts a string that conforms to a specified string pattern to a `DateTime` object.</span></span> <span data-ttu-id="dd117-139">지정된 형식이 아닌 문자열을 이 메서드에 전달할 때 [FormatException](xref:System.FormatException)이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-139">When a string that is not of the form specified is passed to this method, a [FormatException](xref:System.FormatException) is thrown.</span></span> <span data-ttu-id="dd117-140">표준 날짜 및 시간 서식 지정자 또는 사용자 지정 날짜 및 시간 서식 지정자의 제한 조합 중 하나를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-140">You can specify one of the standard date and time format specifiers or a limited combination of the custom date and time format specifiers.</span></span> <span data-ttu-id="dd117-141">사용자 지정 서식 지정자를 사용하면 사용자 지정 문자열을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-141">Using the custom format specifiers, it is possible for you to construct a custom recognition string.</span></span> <span data-ttu-id="dd117-142">지정자에 대한 설명은 [표준 날짜 및 시간 서식 문자열](standard-datetime.md) 및 [사용자 지정 날짜 및 시간 서식 문자열](custom-datetime.md)의 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd117-142">For an explanation of the specifiers, see the topics on [standard date and time format strings](standard-datetime.md) and [custom date and time format strings](custom-datetime.md).</span></span> 

<span data-ttu-id="dd117-143">또한 [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) 메서드의 오버로드 각각에는 일반적으로 문자열의 서식을 지정하는 방법에 대한 문화권별 정보를 제공하는 [IFormatProvider](xref:System.IFormatProvider) 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-143">Each overload of the [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method also has an [IFormatProvider](xref:System.IFormatProvider) parameter that typically provides culture-specific information about the formatting of the string.</span></span> <span data-ttu-id="dd117-144">일반적으로 이 [IFormatProvider](xref:System.IFormatProvider) 개체는 표준 문화권을 나타내는 [CultureInfo](xref:System.Globalization.CultureInfo) 개체 또는 [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) 속성에서 반환되는 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-144">Typically, this [IFormatProvider](xref:System.IFormatProvider) object is a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents a standard culture or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that is returned by the [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) property.</span></span> <span data-ttu-id="dd117-145">그러나 다른 날짜 및 시간 구문 분석 기능과 달리 이 메서드는 비표준 날짜 및 시간 서식을 정의하는 [IFormatProvider](xref:System.IFormatProvider)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-145">However, unlike the other date and time parsing functions, this method also supports an [IFormatProvider](xref:System.IFormatProvider) that defines a non-standard date and time format.</span></span> 

<span data-ttu-id="dd117-146">다음 코드 예제에서 `ParseExact` 메서드는 서식 지정자와 `CultureInfo` 개체의 뒤에 구문 분석할 문자열 개체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-146">In the following code example, the `ParseExact` method is passed a string object to parse, followed by a format specifier, followed by a `CultureInfo` object.</span></span> <span data-ttu-id="dd117-147">이 `ParseExact` 메서드는 en-US 문화권의 자세한 날짜 패턴을 수행하는 문자열을 구문 분석할 수 있을 따름입니다.</span><span class="sxs-lookup"><span data-stu-id="dd117-147">This `ParseExact` method can only parse strings that exhibit the long date pattern in the en-US culture.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("en-US");
      string[] MyString = {" Friday, April 10, 2009", "Friday, April 10, 2009"};
      foreach (string dateString in MyString)
      {
         try {
            DateTime MyDateTime = DateTime.ParseExact(dateString, "D", MyCultureInfo);
            Console.WriteLine(MyDateTime);
         }
         catch (FormatException) {
            Console.WriteLine("Unable to parse '{0}'", dateString);
         }
      }
   }
}
// The example displays the following output:
//       Unable to parse ' Friday, April 10, 2009'
//       4/10/2009 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("en-US")
      Dim MyString() As String = {" Friday, April 10, 2009", "Friday, April 10, 2009"}
      For Each dateString As String In MyString
         Try
            Dim MyDateTime As DateTime = DateTime.ParseExact(dateString, "D", _
                                                             MyCultureInfo)
            Console.WriteLine(MyDateTime)
         Catch e As FormatException
            Console.WriteLine("Unable to parse '{0}'", dateString)
         End Try
      Next
   End Sub
End Module
' The example displays the following output:
'       Unable to parse ' Friday, April 10, 2009'
'       4/10/2009 12:00:00 AM
```

## <a name="see-also"></a><span data-ttu-id="dd117-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd117-148">See Also</span></span>

[<span data-ttu-id="dd117-149">.NET에서 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="dd117-149">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="dd117-150">.NET의 서식 지정 형식</span><span class="sxs-lookup"><span data-stu-id="dd117-150">Formatting types in .NET</span></span>](formatting-types.md)

[<span data-ttu-id="dd117-151">.NET에서 형식 변환</span><span class="sxs-lookup"><span data-stu-id="dd117-151">Type conversion in .NET</span></span>](type-conversion.md)


