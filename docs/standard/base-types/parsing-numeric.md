---
title: ".NET에서 숫자 문자열 구문 분석"
description: ".NET에서 숫자 문자열 구문 분석"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e393430a-731a-49fa-83de-ff7ed52d5704
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 85cd57d33b03f7a2105ee3f770b2f8bcc0a57ee4
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-numeric-strings-in-net"></a><span data-ttu-id="1dd14-104">.NET에서 숫자 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="1dd14-104">Parsing numeric strings in .NET</span></span>

<span data-ttu-id="1dd14-105">모든 숫자 형식에는 두 개의 정적 구문 분석 메서드인 `Parse` 및 `TryParse`가 있습니다. 이를 사용하여 숫자의 문자열 표현을 숫자 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-105">All numeric types have two static parsing methods, `Parse` and `TryParse`, that you can use to convert the string representation of a number into a numeric type.</span></span> <span data-ttu-id="1dd14-106">이러한 메서드를 사용하면 [표준 숫자 서식 문자열](standard-numeric.md) 및 [사용자 지정 숫자 서식 문자열](custom-numeric.md)에서 설명하는 서식 문자열을 사용하여 생성된 문자열을 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-106">These methods enable you to parse strings that were produced by using the format strings documented in [Standard Numeric Format Strings](standard-numeric.md) and [Custom Numeric Format Strings](custom-numeric.md).</span></span> <span data-ttu-id="1dd14-107">기본적으로 `Parse` 및 `TryParse` 메서드는 정수 소수 자릿수를 포함하는 문자열을 정수 값으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-107">By default, the `Parse` and `TryParse` methods can successfully convert strings that contain integral decimal digits only to integer values.</span></span> <span data-ttu-id="1dd14-108">정수 및 소수&10;진수 숫자, 그룹 구분 기호 및 소수 구분 기호를 포함하는 문자열을 부동 소수점 값으로 성공적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-108">They can successfully convert strings that contain integral and fractional decimal digits, group separators, and a decimal separator to floating-point values.</span></span> <span data-ttu-id="1dd14-109">작업에 실패하면 `Parse` 메서드는 예외를 throw하지만 `TryParse` 메서드는 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-109">The `Parse` method throws an exception if the operation fails, whereas the `TryParse` method returns `false`.</span></span>

## <a name="parsing-and-format-providers"></a><span data-ttu-id="1dd14-110">구문 분석 및 서식 공급자</span><span class="sxs-lookup"><span data-stu-id="1dd14-110">Parsing and format providers</span></span>

<span data-ttu-id="1dd14-111">일반적으로 숫자 값의 문자열 표현은 문화권마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-111">Typically, the string representations of numeric values differ by culture.</span></span> <span data-ttu-id="1dd14-112">통화 기호, 그룹(또는 천 단위 자리) 구분 기호 및 소수 구분 기호와 같은 숫자 문자열의 요소는 모두 문화권마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-112">Elements of numeric strings such as currency symbols, group (or thousands) separators, and decimal separators all vary by culture.</span></span> <span data-ttu-id="1dd14-113">구문 분석 메서드는 이러한 문화권별 차이를 인식하는 서식 공급자를 암시적 또는 명시적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-113">Parsing methods either implicitly or explicitly use a format provider that recognizes these culture-specific variations.</span></span> <span data-ttu-id="1dd14-114">서식 공급자가 `Parse` 또는 `TryParse` 메서드에 대한 호출에 지정되지 않은 경우 현재 스레드 문화권과 연결된 서식 공급자([NumberFormatInfo.CurrentInfo](xref:System.Globalization.NumberFormatInfo.CurrentInfo) 속성에서 반환한 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 개체)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-114">If no format provider is specified in a call to the `Parse` or `TryParse` method, the format provider associated with the current thread culture (the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object returned by the [NumberFormatInfo.CurrentInfo](xref:System.Globalization.NumberFormatInfo.CurrentInfo) property) is used.</span></span> 

<span data-ttu-id="1dd14-115">서식 공급자는 [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) 구현에서 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-115">A format provider is represented by an [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) implementation.</span></span> <span data-ttu-id="1dd14-116">이 인터페이스는 단일 구성원인 [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) 메서든이며 여기서 단일 매개 변수는 서식을 지정할 형식을 나타내는 [Type](xref:System.Type) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-116">This interface has a single member, the [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method, whose single parameter is a [Type](xref:System.Type) object that represents the type to be formatted.</span></span> <span data-ttu-id="1dd14-117">이 메서드는 서식 지정 정보를 제공하는 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-117">This method returns the object that provides formatting information.</span></span> <span data-ttu-id="1dd14-118">.NET에서는 숫자 문자열을 구문 분석하기 위해 다음과 같은 두 가지 [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) 구현을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-118">.NET supports the following two [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) implementations for parsing numeric strings:</span></span>

* <span data-ttu-id="1dd14-119">[CultureInfo](xref:System.Globalization.CultureInfo) 개체의 [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) 메서드는 문화권별 서식 지정 정보를 제공하는 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-119">A [CultureInfo](xref:System.Globalization.CultureInfo) object whose [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns a [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that provides culture-specific formatting information.</span></span>

* <span data-ttu-id="1dd14-120">[NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 개체의 [NumberFormatInfo.GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) 메서드는 스스로를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-120">A [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object whose [NumberFormatInfo.GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) method returns itself.</span></span>

<span data-ttu-id="1dd14-121">다음 예제에서는 배열의 각 문자열을 [Double](xref:System.Double) 값으로 변환하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-121">The following example tries to convert each string in an array to a [Double](xref:System.Double) value.</span></span> <span data-ttu-id="1dd14-122">먼저 영어(미국) 문화권의 규칙을 반영하는 서식 공급자를 사용하여 문자열을 구문 분석하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-122">It first tries to parse the string by using a format provider that reflects the conventions of the English (United States) culture.</span></span> <span data-ttu-id="1dd14-123">이 작업에서 [FormatException](xref:System.FormatException)을 throw하는 경우 프랑스어(프랑스) 문화권의 규칙을 반영하는 서식 공급자를 사용하여 문자열을 구문 분석하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-123">If this operation throws a [FormatException](xref:System.FormatException), it tries to parse the string by using a format provider that reflects the conventions of the French (France) culture.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string[] values = { "1,304.16", "$1,456.78", "1,094", "152", 
                          "123,45 €", "1 304,16", "Ae9f" };
      double number;
      CultureInfo culture = null;

      foreach (string value in values) {
         try {
            culture = CultureInfo.CreateSpecificCulture("en-US");
            number = Double.Parse(value, culture);
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
         }   
         catch (FormatException) {
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value);
            culture = CultureInfo.CreateSpecificCulture("fr-FR");
            try {
               number = Double.Parse(value, culture);
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
            }
            catch (FormatException) {
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value);
            }
         }
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//    en-US: 1,304.16 --> 1304.16
//    
//    en-US: Unable to parse '$1,456.78'.
//    fr-FR: Unable to parse '$1,456.78'.
//    
//    en-US: 1,094 --> 1094
//    
//    en-US: 152 --> 152
//    
//    en-US: Unable to parse '123,45 €'.
//    fr-FR: Unable to parse '123,45 €'.
//    
//    en-US: Unable to parse '1 304,16'.
//    fr-FR: 1 304,16 --> 1304.16
//    
//    en-US: Unable to parse 'Ae9f'.
//    fr-FR: Unable to parse 'Ae9f'.
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim values() As String = { "1,304.16", "$1,456.78", "1,094", "152", 
                                 "123,45 €", "1 304,16", "Ae9f" }
      Dim number As Double
      Dim culture As CultureInfo = Nothing

      For Each value As String In values
         Try
            culture = CultureInfo.CreateSpecificCulture("en-US")
            number = Double.Parse(value, culture)
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
         Catch e As FormatException
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value)
            culture = CultureInfo.CreateSpecificCulture("fr-FR")
            Try
               number = Double.Parse(value, culture)
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
            Catch ex As FormatException
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value)
            End Try
         End Try
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays the following output:
'    en-US: 1,304.16 --> 1304.16
'    
'    en-US: Unable to parse '$1,456.78'.
'    fr-FR: Unable to parse '$1,456.78'.
'    
'    en-US: 1,094 --> 1094
'    
'    en-US: 152 --> 152
'    
'    en-US: Unable to parse '123,45 €'.
'    fr-FR: Unable to parse '123,45 €'.
'    
'    en-US: Unable to parse '1 304,16'.
'    fr-FR: 1 304,16 --> 1304.16
'    
'    en-US: Unable to parse 'Ae9f'.
'    fr-FR: Unable to parse 'Ae9f'.
```

## <a name="parsing-and-numberstyles-values"></a><span data-ttu-id="1dd14-124">구문 분석 및 NumberStyles 값</span><span class="sxs-lookup"><span data-stu-id="1dd14-124">Parsing and NumberStyles values</span></span>

<span data-ttu-id="1dd14-125">구문 분석 작업이 처리할 수 있는 스타일 요소(예: 공백, 그룹 구분 기호 및 소수 구분 기호)는 [NumberStyles](xref:System.Globalization.NumberStyles) 열거형 값에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-125">The style elements (such as white space, group separators, and decimal separator) that the parse operation can handle are defined by a [NumberStyles](xref:System.Globalization.NumberStyles) enumeration value.</span></span> <span data-ttu-id="1dd14-126">기본적으로 정수 값을 나타내는 문자열은 숫자, 선행 및 후행 공백 및 선행 기호만을 허용하는 [NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer) 값을 사용하여 구문 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-126">By default, strings that represent integer values are parsed by using the [NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer) value, which permits only numeric digits, leading and trailing white space, and a leading sign.</span></span> <span data-ttu-id="1dd14-127">부동 소수점 값을 나타내는 문자열은 [NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) 및 [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) 값의 조합을 사용하여 구문 분석됩니다. 이 복합 스타일은 선행 및 후행 공백, 선행 기호, 소수 구분 기호, 그룹 구분 기호 및 지수와 함께&10;진수 숫자를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-127">Strings that represent floating-point values are parsed using a combination of the [NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) and [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) values; this composite style permits decimal digits along with leading and trailing white space, a leading sign, a decimal separator, a group separator, and an exponent.</span></span> <span data-ttu-id="1dd14-128">구문 분석 작업이 성공하기 위해 [NumberStyles](xref:System.Globalization.NumberStyles) 형식의 매개 변수를 포함하는 `Parse` 또는 `TryParse` 메서드의 오버로드를 호출하고 하나 이상의 [NumberStyles](xref:System.Globalization.NumberStyles) 플래그를 설정하여 문자열에 나타날 수 있는 스타일 요소를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-128">By calling an overload of the `Parse` or `TryParse` method that includes a parameter of type [NumberStyles](xref:System.Globalization.NumberStyles) and setting one or more [NumberStyles](xref:System.Globalization.NumberStyles) flags, you can control the style elements that can be present in the string for the parse operation to succeed.</span></span> 

<span data-ttu-id="1dd14-129">예를 들어 그룹 구분 기호를 포함하는 문자열은 [Int32.Parse(String)](xref:System.Int32.Parse(System.String)) 메서드를 사용하여 [Int32](xref:System.Int32) 값으로 변환할 수 없지만,</span><span class="sxs-lookup"><span data-stu-id="1dd14-129">For example, a string that contains a group separator cannot be converted to an [Int32](xref:System.Int32) value by using the [Int32.Parse(String)](xref:System.Int32.Parse(System.String)) method.</span></span> <span data-ttu-id="1dd14-130">다음 예제에서 설명하는 것처럼 [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) 플래그를 사용할 경우 변환이 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-130">However, the conversion succeeds if you use the [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) flag, as the following example illustrates.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string value = "1,304";
      int number;
      IFormatProvider provider = CultureInfo.CreateSpecificCulture("en-US");
      if (Int32.TryParse(value, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);

      if (Int32.TryParse(value, NumberStyles.Integer | NumberStyles.AllowThousands, 
                        provider, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);
   }
}
// The example displays the following output:
//       Unable to convert '1,304'
//       1,304 --> 1304
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As String = "1,304"
      Dim number As Integer
      Dim provider As IFormatProvider = CultureInfo.CreateSpecificCulture("en-US")
      If Int32.TryParse(value, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If

      If Int32.TryParse(value, NumberStyles.Integer Or NumberStyles.AllowThousands, 
                        provider, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If
   End Sub
End Module
' The example displays the following output:
'       Unable to convert '1,304'
'       1,304 --> 1304
```

> <span data-ttu-id="1dd14-131">**경고**</span><span class="sxs-lookup"><span data-stu-id="1dd14-131">**Warning**</span></span>
>
> <span data-ttu-id="1dd14-132">구문 분석 작업은 항상 특정 문화권의 서식 지정 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-132">The parse operation always uses the formatting conventions of a particular culture.</span></span> <span data-ttu-id="1dd14-133">[CultureInfo](xref:System.Globalization.CultureInfo) 또는 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 개체를 전달하여 문화권을 지정하지 않는 경우 현재 스레드와 관련된 문화권이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-133">If you do not specify a culture by passing a [CultureInfo](xref:System.Globalization.CultureInfo) or [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object, the culture associated with the current thread is used.</span></span>
 
<span data-ttu-id="1dd14-134">다음 테이블에서는 [NumberStyles](xref:System.Globalization.NumberStyles) 열거형의 구성원을 나열하고 구문 분석 작업에 미치는 영향에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-134">The following table lists the members of the [NumberStyles](xref:System.Globalization.NumberStyles) enumeration and describes the effect that they have on the parsing operation.</span></span>

<span data-ttu-id="1dd14-135">NumberStyles 값</span><span class="sxs-lookup"><span data-stu-id="1dd14-135">NumberStyles value</span></span> | <span data-ttu-id="1dd14-136">구문 분석할 문자열에 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="1dd14-136">Effect on the string to be parsed</span></span>
------------------ | --------------------------------- 
[<span data-ttu-id="1dd14-137">NumberStyles.None</span><span class="sxs-lookup"><span data-stu-id="1dd14-137">NumberStyles.None</span></span>](xref:System.Globalization.NumberStyles.None) | <span data-ttu-id="1dd14-138">숫자만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-138">Only numeric digits are permitted.</span></span>
[<span data-ttu-id="1dd14-139">NumberStyles.AllowDecimalPoint</span><span class="sxs-lookup"><span data-stu-id="1dd14-139">NumberStyles.AllowDecimalPoint</span></span>](xref:System.Globalization.NumberStyles.AllowDecimalPoint) | <span data-ttu-id="1dd14-140">소수 구분 기호 및 소수 자릿수가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-140">The decimal separator and fractional digits are permitted.</span></span> <span data-ttu-id="1dd14-141">정수 값의 경우 소수 자릿수로&0;만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-141">For integer values, only zero is permitted as a fractional digit.</span></span> <span data-ttu-id="1dd14-142">[NumberFormatInfo.NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) 또는 [NumberFormatInfo.CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) 속성에 의해 유효한 소수 구분 기호가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-142">Valid decimal separators are determined by the [NumberFormatInfo.NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) or [NumberFormatInfo.CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) property.</span></span>
[<span data-ttu-id="1dd14-143">NumberStyles.AllowExponent</span><span class="sxs-lookup"><span data-stu-id="1dd14-143">NumberStyles.AllowExponent</span></span>](xref:System.Globalization.NumberStyles.AllowExponent) | <span data-ttu-id="1dd14-144">지수 표기법을 나타내기 위해 "e" 또는 "E" 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-144">The "e" or "E" character can be used to indicate exponential notation.</span></span>
[<span data-ttu-id="1dd14-145">NumberStyles.AllowLeadingWhite</span><span class="sxs-lookup"><span data-stu-id="1dd14-145">NumberStyles.AllowLeadingWhite</span></span>](xref:System.Globalization.NumberStyles.AllowLeadingWhite) | <span data-ttu-id="1dd14-146">선행 공백이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-146">Leading white space is permitted.</span></span>
[<span data-ttu-id="1dd14-147">NumberStyles.AllowTrailingWhite</span><span class="sxs-lookup"><span data-stu-id="1dd14-147">NumberStyles.AllowTrailingWhite</span></span>](xref:System.Globalization.NumberStyles.AllowTrailingWhite) | <span data-ttu-id="1dd14-148">후행 공백이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-148">Trailing white space is permitted.</span></span>
[<span data-ttu-id="1dd14-149">NumberStyles.AllowLeadingSign</span><span class="sxs-lookup"><span data-stu-id="1dd14-149">NumberStyles.AllowLeadingSign</span></span>](xref:System.Globalization.NumberStyles.AllowLeadingSign) | <span data-ttu-id="1dd14-150">양수 또는 음수 기호를 숫자 앞에 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-150">A positive or negative sign can precede numeric digits.</span></span>
[<span data-ttu-id="1dd14-151">NumberStyles.AllowTrailingSign</span><span class="sxs-lookup"><span data-stu-id="1dd14-151">NumberStyles.AllowTrailingSign</span></span>](xref:System.Globalization.NumberStyles.AllowTrailingSign) | <span data-ttu-id="1dd14-152">양수 또는 음수 기호를 숫자 뒤에 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-152">A positive or negative sign can follow numeric digits.</span></span>
[<span data-ttu-id="1dd14-153">NumberStyles.AllowParentheses</span><span class="sxs-lookup"><span data-stu-id="1dd14-153">NumberStyles.AllowParentheses</span></span>](xref:System.Globalization.NumberStyles.AllowParentheses) | <span data-ttu-id="1dd14-154">괄호는 음수 값을 나타내는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-154">Parentheses can be used to indicate negative values.</span></span>
[<span data-ttu-id="1dd14-155">NumberStyles.AllowThousands</span><span class="sxs-lookup"><span data-stu-id="1dd14-155">NumberStyles.AllowThousands</span></span>](xref:System.Globalization.NumberStyles.AllowThousands) | <span data-ttu-id="1dd14-156">그룹 구분 기호가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-156">The group separator is permitted.</span></span> <span data-ttu-id="1dd14-157">그룹 구분 기호는 [NumberFormatInfo.NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) 또는 [NumberFormatInfo.CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) 속성에서 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-157">The group separator character is determined by the [NumberFormatInfo.NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) or [NumberFormatInfo.CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) property.</span></span>
[<span data-ttu-id="1dd14-158">NumberStyles.AllowCurrencySymbol</span><span class="sxs-lookup"><span data-stu-id="1dd14-158">NumberStyles.AllowCurrencySymbol</span></span>](xref:System.Globalization.NumberStyles.AllowCurrencySymbol) | <span data-ttu-id="1dd14-159">통화 기호가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-159">The currency symbol is permitted.</span></span> <span data-ttu-id="1dd14-160">통화 기호는 [NumberFormatInfo.CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) 속성에서 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-160">The currency symbol is defined by the [NumberFormatInfo.CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) property.</span></span>
[<span data-ttu-id="1dd14-161">NumberStyles.AllowHexSpecifier</span><span class="sxs-lookup"><span data-stu-id="1dd14-161">NumberStyles.AllowHexSpecifier</span></span>](xref:System.Globalization.NumberStyles.AllowHexSpecifier) | <span data-ttu-id="1dd14-162">구문 분석될 문자열은&16;진수 숫자로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-162">The string to be parsed is interpreted as a hexadecimal number.</span></span> <span data-ttu-id="1dd14-163">16진수인 0-9, A-F 및 a-f를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-163">It can include the hexadecimal digits 0-9, A-F, and a-f.</span></span> <span data-ttu-id="1dd14-164">이 플래그는 정수 값을 구문 분석하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-164">This flag can be used only to parse integer values.</span></span>
 
<span data-ttu-id="1dd14-165">또한 [NumberStyles](xref:System.Globalization.NumberStyles) 열거형은 다중 [NumberStyles](xref:System.Globalization.NumberStyles) 플래그를 포함하는 다음과 같은 복합 스타일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-165">In addition, the [NumberStyles](xref:System.Globalization.NumberStyles) enumeration provides the following composite styles, which include multiple [NumberStyles](xref:System.Globalization.NumberStyles) flags.</span></span> 

<span data-ttu-id="1dd14-166">복합 NumberStyles 값</span><span class="sxs-lookup"><span data-stu-id="1dd14-166">Composite NumberStyles value</span></span> | <span data-ttu-id="1dd14-167">구성원 포함</span><span class="sxs-lookup"><span data-stu-id="1dd14-167">Includes members</span></span>
---------------------------- | ---------------- 
[<span data-ttu-id="1dd14-168">NumberStyles.Integer</span><span class="sxs-lookup"><span data-stu-id="1dd14-168">NumberStyles.Integer</span></span>](xref:System.Globalization.NumberStyles.Integer) | <span data-ttu-id="1dd14-169">[NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) 및 [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign) 스타일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-169">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), and [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign) styles.</span></span> <span data-ttu-id="1dd14-170">정수 값을 구문 분석하는 데 사용되는 기본 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-170">This is the default style used to parse integer values.</span></span>
[<span data-ttu-id="1dd14-171">NumberStyles.Number</span><span class="sxs-lookup"><span data-stu-id="1dd14-171">NumberStyles.Number</span></span>](xref:System.Globalization.NumberStyles.Number) | <span data-ttu-id="1dd14-172">[NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) 및 [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) 스타일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-172">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint), and [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) styles.</span></span>
[<span data-ttu-id="1dd14-173">NumberStyles.Float</span><span class="sxs-lookup"><span data-stu-id="1dd14-173">NumberStyles.Float</span></span>](xref:System.Globalization.NumberStyles.Float) | <span data-ttu-id="1dd14-174">[NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) 및 [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) 스타일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-174">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint), and [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) styles.</span></span>
[<span data-ttu-id="1dd14-175">NumberStyles.Currency</span><span class="sxs-lookup"><span data-stu-id="1dd14-175">NumberStyles.Currency</span></span>](xref:System.Globalization.NumberStyles.Currency) | <span data-ttu-id="1dd14-176">[NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) 및 [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier)를 제외한 모든 스타일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-176">Includes all styles except [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) and [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span></span>
[<span data-ttu-id="1dd14-177">NumberStyles.Any</span><span class="sxs-lookup"><span data-stu-id="1dd14-177">NumberStyles.Any</span></span>](xref:System.Globalization.NumberStyles.Any) | <span data-ttu-id="1dd14-178">[NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier)를 제외한 모든 스타일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-178">Includes all styles except [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span></span>
[<span data-ttu-id="1dd14-179">NumberStyles.HexNumber</span><span class="sxs-lookup"><span data-stu-id="1dd14-179">NumberStyles.HexNumber</span></span>](xref:System.Globalization.NumberStyles.HexNumber) | <span data-ttu-id="1dd14-180">[NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) 및 [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier) 스타일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-180">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), and [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier) styles.</span></span>
 
## <a name="parsing-and-unicode-digits"></a><span data-ttu-id="1dd14-181">구문 분석 및 유니코드 숫자</span><span class="sxs-lookup"><span data-stu-id="1dd14-181">Parsing and Unicode digits</span></span>

<span data-ttu-id="1dd14-182">유니코드 표준은 다양한 문자 체계의 숫자에 대한 코드 포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-182">The Unicode standard defines code points for digits in various writing systems.</span></span> <span data-ttu-id="1dd14-183">예를 들어 U+0030에서 U+0039의 코드 포인트는 기본 라틴어 숫자 0부터 9까지를 나타내며, U+09E6에서 U+09EF의 코드 포인트는 벵골어 숫자 0부터 9까지, U+FF10에서 U+FF19의 코드 포인트는 전자 숫자 0부터 9까지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-183">For example, code points from U+0030 to U+0039 represent the basic Latin digits 0 through 9, code points from U+09E6 to U+09EF represent the Bangla digits 0 through 9, and code points from U+FF10 to U+FF19 represent the Fullwidth digits 0 through 9.</span></span> <span data-ttu-id="1dd14-184">그러나 메서드를 구문 분석하여 인식되는 숫자 자릿수는 U +0030에서 U +0039까지의 코드 포인트를 가진 기본 라틴어 숫자 0-9입니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-184">However, the only numeric digits recognized by parsing methods are the basic Latin digits 0-9 with code points from U+0030 to U+0039.</span></span> <span data-ttu-id="1dd14-185">메서드를 구문 분석하는 숫자가 다른 숫자를 포함하는 문자열로 전달되는 경우 메서드에서는 [FormatException](xref:System.FormatException)을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-185">If a numeric parsing method is passed a string that contains any other digits, the method throws a [FormatException](xref:System.FormatException).</span></span>

<span data-ttu-id="1dd14-186">다음 예제에서는 [Int32.Parse](xref:System.Int32.Parse(System.String)) 메서드를 사용하여 다른 쓰기 시스템에 있는 숫자로 구성된 문자열을 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-186">The following example uses the [Int32.Parse](xref:System.Int32.Parse(System.String)) method to parse strings that consist of digits in different writing systems.</span></span> <span data-ttu-id="1dd14-187">이 예제의 결과에서와 같이 기본 라틴어 숫자에 대한 구문 분석 시도는 성공하지만 전자, 아랍어-인도어, 벵골어 숫자에 대한 구문 분석 시도는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd14-187">As the output from the example shows, the attempt to parse the basic Latin digits succeeds, but the attempt to parse the Fullwidth, Arabic-Indic, and Bangla digits fails.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string value;
      // Define a string of basic Latin digits 1-5.
      value = "\u0031\u0032\u0033\u0034\u0035";
      ParseDigits(value);

      // Define a string of Fullwidth digits 1-5.
      value = "\uFF11\uFF12\uFF13\uFF14\uFF15";
      ParseDigits(value);

      // Define a string of Arabic-Indic digits 1-5.
      value = "\u0661\u0662\u0663\u0664\u0665";
      ParseDigits(value);

      // Define a string of Bangla digits 1-5.
      value = "\u09e7\u09e8\u09e9\u09ea\u09eb";
      ParseDigits(value);
   }

   static void ParseDigits(string value)
   {
      try {
         int number = Int32.Parse(value);
         Console.WriteLine("'{0}' --> {1}", value, number);
      }   
      catch (FormatException) {
         Console.WriteLine("Unable to parse '{0}'.", value);      
      }     
   }
}
// The example displays the following output:
//       '12345' --> 12345
//       Unable to parse '１２３４５'.
//       Unable to parse '١٢٣٤٥'.
//       Unable to parse '১২৩৪৫'.
```

```vb
Module Example
   Public Sub Main()
      Dim value As String
      ' Define a string of basic Latin digits 1-5.
      value = ChrW(&h31) + ChrW(&h32) + ChrW(&h33) + ChrW(&h34) + ChrW(&h35)
      ParseDigits(value)

      ' Define a string of Fullwidth digits 1-5.
      value = ChrW(&hff11) + ChrW(&hff12) + ChrW(&hff13) + ChrW(&hff14) + ChrW(&hff15)
      ParseDigits(value)

      ' Define a string of Arabic-Indic digits 1-5.
      value = ChrW(&h661) + ChrW(&h662) + ChrW(&h663) + ChrW(&h664) + ChrW(&h665)
      ParseDigits(value)

      ' Define a string of Bangla digits 1-5.
      value = ChrW(&h09e7) + ChrW(&h09e8) + ChrW(&h09e9) + ChrW(&h09ea) + ChrW(&h09eb)
      ParseDigits(value)
   End Sub

   Sub ParseDigits(value As String)
      Try
         Dim number As Integer = Int32.Parse(value)
         Console.WriteLine("'{0}' --> {1}", value, number)
      Catch e As FormatException
         Console.WriteLine("Unable to parse '{0}'.", value)      
      End Try     
   End Sub
End Module
' The example displays the following output:
'       '12345' --> 12345
'       Unable to parse '１２３４５'.
'       Unable to parse '١٢٣٤٥'.
'       Unable to parse '১২৩৪৫'.
```

## <a name="see-also"></a><span data-ttu-id="1dd14-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1dd14-188">See also</span></span>

[<span data-ttu-id="1dd14-189">System.Globalization.NumberStyles</span><span class="sxs-lookup"><span data-stu-id="1dd14-189">System.Globalization.NumberStyles</span></span>](xref:System.Globalization.NumberStyles)

[<span data-ttu-id="1dd14-190">.NET에서 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="1dd14-190">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="1dd14-191">.NET의 서식 지정 형식</span><span class="sxs-lookup"><span data-stu-id="1dd14-191">Formatting types in .NET</span></span>](formatting-types.md)


