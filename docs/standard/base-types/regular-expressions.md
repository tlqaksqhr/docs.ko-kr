---
title: ".NET에서의 정규식"
description: ".NET에서의 정규식"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d1a640cf-09ca-48f7-800c-a627a6d549c9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: ac26821819b22aa3ea47e6945bb5c8575dcd9807
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="regular-expressions-in-net"></a><span data-ttu-id="c5aa1-104">.NET에서의 정규식</span><span class="sxs-lookup"><span data-stu-id="c5aa1-104">Regular expressions in .NET</span></span>

<span data-ttu-id="c5aa1-105">정규식은 텍스트를 처리하는 강력하고 유연하며 효율적인 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-105">Regular expressions provide a powerful, flexible, and efficient method for processing text.</span></span> <span data-ttu-id="c5aa1-106">정규식의 광범위한 패턴 일치 표기법을 사용하여 많은 양의 텍스트를 신속하게 구문 분석함으로써 특정 문자 패턴을 찾고, 텍스트의 유효성을 검사하여 해당 텍스트가 미리 정의된 패턴(예: 전자 메일 주소)과 일치하는지 확인하며, 텍스트 부분 문자열을 추출, 편집, 바꾸기 또는 삭제하고, 추출된 문자열을 컬렉션에 추가하여 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-106">The extensive pattern-matching notation of regular expressions enables you to quickly parse large amounts of text to find specific character patterns; to validate text to ensure that it matches a predefined pattern (such as an e-mail address); to extract, edit, replace, or delete text substrings; and to add the extracted strings to a collection in order to generate a report.</span></span> <span data-ttu-id="c5aa1-107">문자열을 처리하거나 텍스트의 큰 블록을 구문 분석하는 많은 응용 프로그램의 경우 정규식은 필수적인 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-107">For many applications that deal with strings or that parse large blocks of text, regular expressions are an indispensable tool.</span></span>

## <a name="how-regular-expressions-work"></a><span data-ttu-id="c5aa1-108">정규식의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="c5aa1-108">How Regular Expressions Work</span></span>

<span data-ttu-id="c5aa1-109">정규식을 사용하여 텍스트를 처리하는 중심에는 .NET에서 [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) 개체로 표현되는 정규식 엔진이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-109">The centerpiece of text processing with regular expressions is the regular expression engine, which is represented by the [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) object in .NET.</span></span> <span data-ttu-id="c5aa1-110">정규식을 사용하여 텍스트를 처리하려면 최소한 정규식 엔진이 다음과 같은 두 가지 정보 항목과 함께 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-110">At a minimum, processing text using regular expressions requires that the regular expression engine be provided with the following two items of information:</span></span>

* <span data-ttu-id="c5aa1-111">텍스트에서 식별할 정규식 패턴</span><span class="sxs-lookup"><span data-stu-id="c5aa1-111">The regular expression pattern to identify in the text.</span></span> 
  
  <span data-ttu-id="c5aa1-112">.NET에서 정규식 패턴은 특수 구문 또는 언어로 정의되며 Perl 5 정규식과 호환되고 오른쪽에서 왼쪽으로 일치와 같은 몇 가지 기능을 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-112">In .NET, regular expression patterns are defined by a special syntax or language, which is compatible with Perl 5 regular expressions and adds some additional features such as right-to-left matching.</span></span> <span data-ttu-id="c5aa1-113">자세한 내용은 [정규식 언어 - 빠른 참조](quick-ref.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-113">For more information, see [Regular Expression Language - Quick Reference](quick-ref.md).</span></span>
  
* <span data-ttu-id="c5aa1-114">정규식 패턴에 대해 구문 분석할 텍스트</span><span class="sxs-lookup"><span data-stu-id="c5aa1-114">The text to parse for the regular expression pattern.</span></span>

<span data-ttu-id="c5aa1-115">[Regex](xref:System.Text.RegularExpressions.Regex) 클래스의 메서드를 사용하여 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-115">The methods of the [Regex](xref:System.Text.RegularExpressions.Regex) class let you perform the following operations:</span></span>

* <span data-ttu-id="c5aa1-116">[Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) 메서드를 호출하여 입력 텍스트에서 정규식 패턴이 발생하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-116">Determine whether the regular expression pattern occurs in the input text by calling the [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) method.</span></span> <span data-ttu-id="c5aa1-117">텍스트 유효성 검사에 [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) 메서드를 사용하는 예제에 대해서는 [방법: 문자열이 올바른 전자 메일 서식인지 확인](verify-format.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-117">For an example that uses the [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) method for validating text, see [How to: Verify that Strings Are in Valid Email Format](verify-format.md).</span></span>

* <span data-ttu-id="c5aa1-118">[Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) 또는 [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) 메서드를 호출하여 정규식 패턴과 일치하는 텍스트를 하나 또는 모두 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-118">Retrieve one or all occurrences of text that matches the regular expression pattern by calling the [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) or [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) method.</span></span> <span data-ttu-id="c5aa1-119">전자 메서드는 일치하는 텍스트에 대한 정보를 제공하는 [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-119">The former method returns a [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) object that provides information about the matching text.</span></span> <span data-ttu-id="c5aa1-120">후자는 구문 분석된 텍스트에서 찾은 각 일치 항목의 [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) 개체 하나를 포함하는 [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-120">The latter returns a [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) object that contains one [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) object for each match found in the parsed text.</span></span> 

* <span data-ttu-id="c5aa1-121">[Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) 메서드를 호출하여 정규식 패턴과 일치하는 텍스트를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-121">Replace text that matches the regular expression pattern by calling the [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method.</span></span> <span data-ttu-id="c5aa1-122">[Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) 메서드를 사용하여 날짜 서식을 변경하고 문자열에서 잘못된 문자를 제거하는 예제는 [방법: 문자열에서 유효하지 않은 문자 제거](strip-characters.md) 및 [정규식 예제: 날짜 서식 변경](changing-formats.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-122">For examples that use the [Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method to change date formats and remove invalid characters from a string, see [How to: Strip Invalid Characters from a String](strip-characters.md) and [Regular Expression Example: Changing Date Formats](changing-formats.md).</span></span>

<span data-ttu-id="c5aa1-123">정규식 개체 모델의 개요는 [정규식 개체 모델](object-model.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-123">For an overview of the regular expression object model, see [The Regular Expression Object Model](object-model.md).</span></span>

<span data-ttu-id="c5aa1-124">정규식 언어에 대한 자세한 내용은 [정규식 언어 - 빠른 참조](quick-ref.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-124">For more information about the regular expression language, see [Regular Expression Language - Quick Reference](quick-ref.md).</span></span>

## <a name="regular-expression-examples"></a><span data-ttu-id="c5aa1-125">정규식 예제</span><span class="sxs-lookup"><span data-stu-id="c5aa1-125">Regular Expression Examples</span></span>

<span data-ttu-id="c5aa1-126">[String](xref:System.String) 클래스에는 큰 문자열에서 리터럴 문자열을 찾을 때 사용할 수 있는 다양한 문자열 검색 및 바꾸기 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-126">The [String](xref:System.String) class includes a number of string search and replacement methods that you can use when you want to locate literal strings in a larger string.</span></span> <span data-ttu-id="c5aa1-127">정규식은 다음 예제에서 보여 주는 것처럼 큰 문자열에서 여러 부분 문자열 중 하나를 찾거나 문자열에서 패턴을 식별할 때 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-127">Regular expressions are most useful either when you want to locate one of several substrings in a larger string, or when you want to identify patterns in a string, as the following examples illustrate.</span></span> 

### <a name="example-1-replacing-substrings"></a><span data-ttu-id="c5aa1-128">예제 1: 부분 문자열 바꾸기</span><span class="sxs-lookup"><span data-stu-id="c5aa1-128">Example 1: Replacing Substrings</span></span>

<span data-ttu-id="c5aa1-129">메일 그룹에 경우에 따라 호칭(Mr., Mrs., Miss 또는 Ms.)이 이름 및 성과 함께 포함되어 있는 이름이 들어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-129">Assume that a mailing list contains names that sometimes include a title (Mr., Mrs., Miss, or Ms.) along with a first and last name.</span></span> <span data-ttu-id="c5aa1-130">메일 그룹에서 봉투 레이블을 생성할 때 호칭을 포함하지 않으려는 경우 다음 예제에서 보여 주는 것처럼 정규식을 사용하여 호칭을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-130">If you do not want to include the titles when you generate envelope labels from the list, you can use a regular expression to remove the titles, as the following example illustrates.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "(Mr\\.? |Mrs\\.? |Miss |Ms\\.? )";
      string[] names = { "Mr. Henry Hunt", "Ms. Sara Samuels", 
                         "Abraham Adams", "Ms. Nicole Norris" };
      foreach (string name in names)
         Console.WriteLine(Regex.Replace(name, pattern, String.Empty));
   }
}
// The example displays the following output:
//    Henry Hunt
//    Sara Samuels
//    Abraham Adams
//    Nicole Norris
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(Mr\.? |Mrs\.? |Miss |Ms\.? )"
      Dim names() As String = { "Mr. Henry Hunt", "Ms. Sara Samuels", _
                                "Abraham Adams", "Ms. Nicole Norris" }
      For Each name As String In names
         Console.WriteLine(Regex.Replace(name, pattern, String.Empty))
      Next                                
   End Sub
End Module
' The example displays the following output:
'    Henry Hunt
'    Sara Samuels
'    Abraham Adams
'    Nicole Norris
```

<span data-ttu-id="c5aa1-131">정규식 패턴 `(Mr\.? |Mrs\.? |Miss |Ms\.? )`는 모든 "Mr", "Mr.", "Mrs", "Mrs.", "Miss", "Ms" 또는 "Ms."가 발생하는 것과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-131">The regular expression pattern `(Mr\.? |Mrs\.? |Miss |Ms\.? )` matches any occurrence of "Mr ", "Mr. ", "Mrs ", "Mrs. ", "Miss ", "Ms or "Ms. ".</span></span> <span data-ttu-id="c5aa1-132">[Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) 메서드에 대한 호출은 일치하는 문자열을 [String.Empty](xref:System.String.Empty)로 바꿉니다. 즉, 원래 문자열에서 일치하는 문자열을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-132">The call to the [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method replaces the matched string with [String.Empty](xref:System.String.Empty); in other words, it removes it from the original string.</span></span>

### <a name="example-2-identifying-duplicated-words"></a><span data-ttu-id="c5aa1-133">예제 2: 중복된 단어 식별</span><span class="sxs-lookup"><span data-stu-id="c5aa1-133">Example 2: Identifying Duplicated Words</span></span>

<span data-ttu-id="c5aa1-134">실수로 단어를 중복하는 것은 작성자가 흔히 하는 실수입니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-134">Accidentally duplicating words is a common error that writers make.</span></span> <span data-ttu-id="c5aa1-135">다음 예제에서 보여 주는 것처럼 정규식을 사용하여 중복된 단어를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-135">A regular expression can be used to identify duplicated words, as the following example shows.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Class1
{
   public static void Main()
   {
      string pattern = @"\b(\w+?)\s\1\b";
      string input = "This this is a nice day. What about this? This tastes good. I saw a a dog.";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine("{0} (duplicates '{1}') at position {2}", 
                           match.Value, match.Groups[1].Value, match.Index);
   }
}
// The example displays the following output:
//       This this (duplicates 'This)' at position 0
//       a a (duplicates 'a)' at position 66
```

```vb
Imports System.Text.RegularExpressions

Module modMain
   Public Sub Main()
      Dim pattern As String = "\b(\w+?)\s\1\b"
      Dim input As String = "This this is a nice day. What about this? This tastes good. I saw a a dog."
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine("{0} (duplicates '{1}') at position {2}", _
                           match.Value, match.Groups(1).Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       This this (duplicates 'This)' at position 0
'       a a (duplicates 'a)' at position 66
```

<span data-ttu-id="c5aa1-136">정규식 패턴 `\b(\w+?)\s\1\b`는 다음과 같이 해석될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-136">The regular expression pattern `\b(\w+?)\s\1\b` can be interpreted as follows:</span></span>

<span data-ttu-id="c5aa1-137">구문</span><span class="sxs-lookup"><span data-stu-id="c5aa1-137">Syntax</span></span> | <span data-ttu-id="c5aa1-138">의미</span><span class="sxs-lookup"><span data-stu-id="c5aa1-138">Meaning</span></span>
------ | -------
`\b` | <span data-ttu-id="c5aa1-139">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-139">Start at a word boundary.</span></span>
`(\w+?)` | <span data-ttu-id="c5aa1-140">하나 이상의 단어 문자(가능한 한 적은 문자)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-140">Match one or more word characters, but as few characters as possible.</span></span> <span data-ttu-id="c5aa1-141">이러한 단어 문자는 함께 `\1`이라고 할 수 있는 그룹을 형성합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-141">Together, they form a group that can be referred to as `\1`.</span></span>
`\s` | <span data-ttu-id="c5aa1-142">공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-142">Match a white-space character.</span></span>
`\1` | <span data-ttu-id="c5aa1-143">`\1`이라는 그룹과 같은 부분 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-143">Match the substring that is equal to the group named `\1`.</span></span>
`\b` | <span data-ttu-id="c5aa1-144">단어 경계를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-144">Match a word boundary.</span></span>

<span data-ttu-id="c5aa1-145">[Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) 메서드는 [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase)로 설정된 정규식 옵션을 사용하여 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-145">The [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) method is called with regular expression options set to [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase).</span></span> <span data-ttu-id="c5aa1-146">따라서 찾기 작업은 대/소문자를 구분하지 않으며, 이 예제에서는 부분 문자열 "This this"를 중복으로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-146">Therefore, the match operation is case-insensitive, and the example identifies the substring "This this" as a duplication.</span></span>

<span data-ttu-id="c5aa1-147">입력 문자열에 부분 문자열 "this?</span><span class="sxs-lookup"><span data-stu-id="c5aa1-147">Note that the input string includes the substring "this?</span></span> <span data-ttu-id="c5aa1-148">This"가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-148">This".</span></span> <span data-ttu-id="c5aa1-149">그러나 문장 부호가 중간에 있어 이는 중복으로 식별되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-149">However, because of the intervening punctuation mark, it is not identified as a duplication.</span></span>

### <a name="example-3-dynamically-building-a-culture-sensitive-regular-expression"></a><span data-ttu-id="c5aa1-150">예제 3: 동적으로 문화권 구분 정규식 작성</span><span class="sxs-lookup"><span data-stu-id="c5aa1-150">Example 3: Dynamically Building a Culture-Sensitive Regular Expression</span></span>

<span data-ttu-id="c5aa1-151">다음 예제에서는 정규식이 .NET의 전역화 기능에서 제공하는 유연성과 결합되었을 때의 성능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-151">The following example illustrates the power of regular expressions combined with the flexibility offered by .NET's globalization features.</span></span> <span data-ttu-id="c5aa1-152">이 예제에서는 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 개체를 사용하여 시스템의 현재 문화권의 통화 값 서식을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-152">It uses the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object to determine the format of currency values in the system's current culture.</span></span> <span data-ttu-id="c5aa1-153">그런 다음 해당 정보를 사용하여 텍스트에서 통화 값을 추출하는 정규식을 동적으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-153">It then uses that information to dynamically construct a regular expression that extracts currency values from the text.</span></span> <span data-ttu-id="c5aa1-154">각 일치 항목에 대해 숫자 문자열만 포함된 하위 그룹을 추출하여 [Decimal](xref:System.Decimal) 값으로 변환하고 누계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-154">For each match, it extracts the subgroup that contains the numeric string only, converts it to a [Decimal](xref:System.Decimal) value, and calculates a running total.</span></span> 

```csharp
using System;
using System.Collections.Generic;
using System.Globalization;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      // Define text to be parsed.
      string input = "Office expenses on 2/13/2008:\n" + 
                     "Paper (500 sheets)                      $3.95\n" + 
                     "Pencils (box of 10)                     $1.00\n" + 
                     "Pens (box of 10)                        $4.49\n" + 
                     "Erasers                                 $2.19\n" + 
                     "Ink jet printer                        $69.95\n\n" + 
                     "Total Expenses                        $ 81.58\n"; 

      // Get current culture's NumberFormatInfo object.
      NumberFormatInfo nfi = CultureInfo.CurrentCulture.NumberFormat;
      // Assign needed property values to variables.
      string currencySymbol = nfi.CurrencySymbol;
      bool symbolPrecedesIfPositive = nfi.CurrencyPositivePattern % 2 == 0;
      string groupSeparator = nfi.CurrencyGroupSeparator;
      string decimalSeparator = nfi.CurrencyDecimalSeparator;

      // Form regular expression pattern.
      string pattern = Regex.Escape( symbolPrecedesIfPositive ? currencySymbol : "") + 
                       @"\s*[-+]?" + "([0-9]{0,3}(" + groupSeparator + "[0-9]{3})*(" + 
                       Regex.Escape(decimalSeparator) + "[0-9]+)?)" + 
                       (! symbolPrecedesIfPositive ? currencySymbol : ""); 
      Console.WriteLine( "The regular expression pattern is:");
      Console.WriteLine("   " + pattern);      

      // Get text that matches regular expression pattern.
      MatchCollection matches = Regex.Matches(input, pattern, 
                                              RegexOptions.IgnorePatternWhitespace);               
      Console.WriteLine("Found {0} matches.", matches.Count); 

      // Get numeric string, convert it to a value, and add it to List object.
      List<decimal> expenses = new List<Decimal>();

      foreach (Match match in matches)
         expenses.Add(Decimal.Parse(match.Groups[1].Value));      

      // Determine whether total is present and if present, whether it is correct.
      decimal total = 0;
      foreach (decimal value in expenses)
         total += value;

      if (total / 2 == expenses[expenses.Count - 1]) 
         Console.WriteLine("The expenses total {0:C2}.", expenses[expenses.Count - 1]);
      else
         Console.WriteLine("The expenses total {0:C2}.", total);
   }  
}
// The example displays the following output:
//       The regular expression pattern is:
//          \$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)
//       Found 6 matches.
//       The expenses total $81.58.
```

```vb
Imports System.Collections.Generic
Imports System.Globalization
Imports System.Text.RegularExpressions

Public Module Example
   Public Sub Main()
      ' Define text to be parsed.
      Dim input As String = "Office expenses on 2/13/2008:" + vbCrLf + _
                            "Paper (500 sheets)                      $3.95" + vbCrLf + _
                            "Pencils (box of 10)                     $1.00" + vbCrLf + _
                            "Pens (box of 10)                        $4.49" + vbCrLf + _
                            "Erasers                                 $2.19" + vbCrLf + _
                            "Ink jet printer                        $69.95" + vbCrLf + vbCrLf + _
                            "Total Expenses                        $ 81.58" + vbCrLf
      ' Get current culture's NumberFormatInfo object.
      Dim nfi As NumberFormatInfo = CultureInfo.CurrentCulture.NumberFormat
      ' Assign needed property values to variables.
      Dim currencySymbol As String = nfi.CurrencySymbol
      Dim symbolPrecedesIfPositive As Boolean = CBool(nfi.CurrencyPositivePattern Mod 2 = 0)
      Dim groupSeparator As String = nfi.CurrencyGroupSeparator
      Dim decimalSeparator As String = nfi.CurrencyDecimalSeparator

      ' Form regular expression pattern.
      Dim pattern As String = Regex.Escape(CStr(IIf(symbolPrecedesIfPositive, currencySymbol, ""))) + _
                              "\s*[-+]?" + "([0-9]{0,3}(" + groupSeparator + "[0-9]{3})*(" + _
                              Regex.Escape(decimalSeparator) + "[0-9]+)?)" + _
                              CStr(IIf(Not symbolPrecedesIfPositive, currencySymbol, "")) 
      Console.WriteLine("The regular expression pattern is: ")
      Console.WriteLine("   " + pattern)      

      ' Get text that matches regular expression pattern.
      Dim matches As MatchCollection = Regex.Matches(input, pattern, RegexOptions.IgnorePatternWhitespace)               
      Console.WriteLine("Found {0} matches. ", matches.Count)

      ' Get numeric string, convert it to a value, and add it to List object.
      Dim expenses As New List(Of Decimal)

      For Each match As Match In matches
         expenses.Add(Decimal.Parse(match.Groups.Item(1).Value))      
      Next

      ' Determine whether total is present and if present, whether it is correct.
      Dim total As Decimal
      For Each value As Decimal In expenses
         total += value
      Next

      If total / 2 = expenses(expenses.Count - 1) Then
         Console.WriteLine("The expenses total {0:C2}.", expenses(expenses.Count - 1))
      Else
         Console.WriteLine("The expenses total {0:C2}.", total)
      End If   
   End Sub
End Module
' The example displays the following output:
'       The regular expression pattern is:
'          \$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)
'       Found 6 matches.
'       The expenses total $81.58.
```

<span data-ttu-id="c5aa1-155">현재 문화권이 영어 - 미국(en-US)인 컴퓨터에서 이 예제를 실행할 경우 정규식 `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`가 동적으로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-155">On a computer whose current culture is English - United States (en-US), the example dynamically builds the regular expression `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`.</span></span> <span data-ttu-id="c5aa1-156">이 정규식 패턴은 다음과 같이 해석될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-156">This regular expression pattern can be interpreted as follows:</span></span>

<span data-ttu-id="c5aa1-157">구문</span><span class="sxs-lookup"><span data-stu-id="c5aa1-157">Syntax</span></span> | <span data-ttu-id="c5aa1-158">의미</span><span class="sxs-lookup"><span data-stu-id="c5aa1-158">Meaning</span></span>
------ | -------
`\$` | <span data-ttu-id="c5aa1-159">입력 문자열에서 단일 달러 기호($)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-159">Look for a single occurrence of the dollar symbol ($) in the input string.</span></span> <span data-ttu-id="c5aa1-160">정규식 패턴 문자열에는 백슬래시가 포함되어 달러 기호가 정규식 앵커로 해석되는 것이 아니라 리터럴로 해석될 것임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-160">The regular expression pattern string includes a backslash to indicate that the dollar symbol is to be interpreted literally rather than as a regular expression anchor.</span></span> <span data-ttu-id="c5aa1-161">($ 기호 단독으로는 정규식 엔진이 문자열의 끝 부분에서 찾기를 시작하려고 해야 한다는 사실을 나타냅니다.) 현재 문화권의 통화 기호가 정규식 기호로 잘못 해석되지 않도록 하기 위해 이 예제에서는 [Escape](xref:System.Text.RegularExpressions.Regex.Escape(System.String)) 메서드를 호출하여 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-161">(The $ symbol alone would indicate that the regular expression engine should try to begin its match at the end of a string.) To ensure that the current culture's currency symbol is not misinterpreted as a regular expression symbol, the example calls the [Escape](xref:System.Text.RegularExpressions.Regex.Escape(System.String)) method to escape the character.</span></span>
`\s*` | <span data-ttu-id="c5aa1-162">0개 이상의 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-162">Look for zero or more occurrences of a white-space character.</span></span>
`[-+]?` | <span data-ttu-id="c5aa1-163">0개 이상의 더하기 기호 또는 빼기 기호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-163">Look for zero or one occurrence of either a positive sign or a negative sign.</span></span>
`([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)` | <span data-ttu-id="c5aa1-164">이 식을 둘러싼 바깥쪽 괄호는 이 식을 캡처링 그룹 또는 하위 식으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-164">The outer parentheses around this expression define it as a capturing group or a subexpression.</span></span> <span data-ttu-id="c5aa1-165">일치 항목을 찾은 경우 일치하는 문자열의 이 부분에 대한 정보는 [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) 속성에서 반환하는 [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) 개체의 두 번째 [Group](xref:System.Text.RegularExpressions.Group) 개체에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-165">If a match is found, information about this part of the matching string can be retrieved from the second [Group](xref:System.Text.RegularExpressions.Group) object in the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) object returned by the [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) property.</span></span> <span data-ttu-id="c5aa1-166">(컬렉션의 첫 번째 요소는 전체 일치를 나타냅니다.)</span><span class="sxs-lookup"><span data-stu-id="c5aa1-166">(The first element in the collection represents the entire match.)</span></span>
`[0-9]{0,3}` | <span data-ttu-id="c5aa1-167">10진수 0-9를 0~3개 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-167">Look for zero to three occurrences of the decimal digits 0 through 9.</span></span>
`(,[0-9]{3})*` | <span data-ttu-id="c5aa1-168">그룹 구분 기호 하나 다음에 세 개의&10;진수가 있는&0;개 이상의 일치 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-168">Look for zero or more occurrences of a group separator followed by three decimal digits.</span></span>
`\.` | <span data-ttu-id="c5aa1-169">단일 소수 구분 기호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-169">Look for a single occurrence of the decimal separator.</span></span>
`[0-9]+` | <span data-ttu-id="c5aa1-170">하나 이상의&10;진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-170">Look for one or more decimal digits.</span></span>
`(\.[0-9]+)?` | <span data-ttu-id="c5aa1-171">소수 구분 기호 다음에 하나 이상의&10;진수가 있는&0;개 이상의 일치 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-171">Look for zero or one occurrence of the decimal separator followed by at least one decimal digit.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c5aa1-172">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c5aa1-172">Related Topics</span></span>

<span data-ttu-id="c5aa1-173">제목</span><span class="sxs-lookup"><span data-stu-id="c5aa1-173">Title</span></span> | <span data-ttu-id="c5aa1-174">설명</span><span class="sxs-lookup"><span data-stu-id="c5aa1-174">Description</span></span>
----- | -----------
[<span data-ttu-id="c5aa1-175">정규식 언어 - 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="c5aa1-175">Regular expression language - quick reference</span></span>](quick-ref.md) | <span data-ttu-id="c5aa1-176">정규식을 정의하는 데 사용할 수 있는 문자, 연산자 및 생성자 집합에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-176">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
[<span data-ttu-id="c5aa1-177">정규식 개체 모델</span><span class="sxs-lookup"><span data-stu-id="c5aa1-177">The regular expression object model</span></span>](object-model.md) | <span data-ttu-id="c5aa1-178">정규식 클래스를 사용하는 방법을 보여 주는 코드 예제 및 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-178">Provides information and code examples that illustrate how to use the regular expression classes.</span></span>
[<span data-ttu-id="c5aa1-179">정규식 동작 정보</span><span class="sxs-lookup"><span data-stu-id="c5aa1-179">Details of regular expression behavior</span></span>](regex-behavior.md) | <span data-ttu-id="c5aa1-180">.NET 정규식의 기능 및 동작에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-180">Provides information about the capabilities and behavior of .NETregular expressions.</span></span>
[<span data-ttu-id="c5aa1-181">정규식 예제</span><span class="sxs-lookup"><span data-stu-id="c5aa1-181">Regular expression examples</span></span>](regex-examples.md) | <span data-ttu-id="c5aa1-182">정규식의 일반적인 사용을 보여 주는 코드 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa1-182">Provides code examples that illustrate typical uses of regular expressions.</span></span>


## <a name="reference"></a><span data-ttu-id="c5aa1-183">참조</span><span class="sxs-lookup"><span data-stu-id="c5aa1-183">Reference</span></span>

[<span data-ttu-id="c5aa1-184">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="c5aa1-184">System.Text.RegularExpressions</span></span>](xref:System.Text.RegularExpressions)

[<span data-ttu-id="c5aa1-185">System.Text.RegularExpressions.Regex</span><span class="sxs-lookup"><span data-stu-id="c5aa1-185">System.Text.RegularExpressions.Regex</span></span>](xref:System.Text.RegularExpressions.Regex)


