---
title: "정규식에 대한 모범 사례"
description: "정규식에 대한 모범 사례"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 096fd614-91bf-4296-be24-12f62b062294
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: cf9c83de791fa4990a991689a26d4bbdd84cfe7d
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="best-practices-for-regular-expressions"></a><span data-ttu-id="1c380-104">정규식에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="1c380-104">Best practices for regular expressions</span></span>

<span data-ttu-id="1c380-105">.NET의 정규식 엔진은 리터럴 텍스트에 대한 비교 및 검색 대신 패턴 일치를 기반으로 텍스트를 처리하는 완벽한 기능을 갖춘 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-105">The regular expression engine in .NET is a powerful, full-featured tool that processes text based on pattern matches rather than on comparing and matching literal text.</span></span> <span data-ttu-id="1c380-106">대부분의 경우 신속하고 효율적인 방식으로 패턴 일치가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-106">In most cases, it performs pattern matching rapidly and efficiently.</span></span> <span data-ttu-id="1c380-107">하지만 일부 경우에는 정규식 엔진의 실행 속도가 매우 느리게 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-107">However, in some cases, the regular expression engine can appear to be very slow.</span></span> <span data-ttu-id="1c380-108">심한 경우에는 입력 크기가 비교적 적은데도 처리하는 데 시간이 몇 시간 또는 며칠씩 걸려서 응답이 멎은 것처럼 보일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-108">In extreme cases, it can even appear to stop responding as it processes a relatively small input over the course of hours or even days.</span></span> 

<span data-ttu-id="1c380-109">이 항목에서는 개발자가 자신의 정규식 성능을 최적화하기 위해 채택할 수 있는 몇 가지 모범 사례에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-109">This topic outlines some of the best practices that developers can adopt to ensure that their regular expressions achieve optimal performance.</span></span> <span data-ttu-id="1c380-110">여기에는 다음 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-110">It contains the following sections:</span></span>

* [<span data-ttu-id="1c380-111">입력 소스에 대한 고려</span><span class="sxs-lookup"><span data-stu-id="1c380-111">Consider the input source</span></span>](#consider-the-input-source)

* [<span data-ttu-id="1c380-112">적절한 개체 인스턴스화 처리</span><span class="sxs-lookup"><span data-stu-id="1c380-112">Handle object instantiation appropriately</span></span>](#handle-object-instantiation-appropriately)

* [<span data-ttu-id="1c380-113">역추적 수행</span><span class="sxs-lookup"><span data-stu-id="1c380-113">Take charge of backtracking</span></span>](#take-charge-of-backtracking)

* [<span data-ttu-id="1c380-114">시간 제한 값 사용</span><span class="sxs-lookup"><span data-stu-id="1c380-114">Use time-out values</span></span>](#use-time-out-values)

* [<span data-ttu-id="1c380-115">캡처는 필요한 경우에만</span><span class="sxs-lookup"><span data-stu-id="1c380-115">Capture only when necessary</span></span>](#capture-only-when-necessary)

* [<span data-ttu-id="1c380-116">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1c380-116">Related topics</span></span>](#related-topics)

## <a name="consider-the-input-source"></a><span data-ttu-id="1c380-117">입력 소스에 대한 고려</span><span class="sxs-lookup"><span data-stu-id="1c380-117">Consider the input source</span></span>

<span data-ttu-id="1c380-118">일반적으로 정규식은 제한되었거나 제한되지 않은 두 가지 유형의 입력을 받아들일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-118">In general, regular expressions can accept two types of input: constrained or unconstrained.</span></span> <span data-ttu-id="1c380-119">제한된 입력은 알려졌거나 신뢰할 수 있는 소스에서 만들어진 텍스트이며 미리 정의된 서식을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-119">Constrained input is text that originates from a known or reliable source and follows a predefined format.</span></span> <span data-ttu-id="1c380-120">제한되지 않은 입력은 웹 사용자와 같은 신뢰할 수 없는 소스에서 만들어진 텍스트이며 미리 정의되었거나 예상되는 서식을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-120">Unconstrained input is text that originates from an unreliable source, such as a web user, and may not follow a predefined or expected format.</span></span>

<span data-ttu-id="1c380-121">일반적으로 정규식 패턴은 유효한 입력과 일치하도록 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-121">Regular expression patterns are typically written to match valid input.</span></span> <span data-ttu-id="1c380-122">즉, 개발자는 일치시키려는 텍스트를 검사하고 이와 일치하는 정규식 패턴을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-122">That is, developers examine the text that they want to match and then write a regular expression pattern that matches it.</span></span> <span data-ttu-id="1c380-123">그런 다음 개발자는 이 패턴을 여러 가지 유효한 입력 항목으로 테스트하여 패턴 수정이나 추가 작업이 필요한지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-123">Developers then determine whether this pattern requires correction or further elaboration by testing it with multiple valid input items.</span></span> <span data-ttu-id="1c380-124">패턴이 가정된 모든 유효한 입력과 일치하면 패턴을 프로덕션에 사용 가능한 것으로 선언하고 출시 응용 프로그램에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-124">When the pattern matches all presumed valid inputs, it is declared to be production-ready and can be included in a released application.</span></span> <span data-ttu-id="1c380-125">이렇게 하면 제한된 입력과 일치하는지 검색하기 위해 사용하는 데 적합한 정규식 패턴을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-125">This makes a regular expression pattern suitable for matching constrained input.</span></span> <span data-ttu-id="1c380-126">하지만 이러한 패턴은 제한되지 않은 입력과 일치하는지 검색하는 데에는 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-126">However, it does not make it suitable for matching unconstrained input.</span></span>

<span data-ttu-id="1c380-127">제한되지 않은 입력과 일치하는지 확인하려면 정규식이 다음과 같은 세 가지 종류의 텍스트를 효율적으로 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-127">To match unconstrained input, a regular expression must be able to efficiently handle three kinds of text:</span></span>

<span data-ttu-id="1c380-128">• 정규식 패턴과 일치하는 텍스트</span><span class="sxs-lookup"><span data-stu-id="1c380-128">• Text that matches the regular expression pattern.</span></span>

<span data-ttu-id="1c380-129">• 정규식 패턴과 일치하지 않는 텍스트</span><span class="sxs-lookup"><span data-stu-id="1c380-129">• Text that does not match the regular expression pattern.</span></span>

<span data-ttu-id="1c380-130">• 정규식 패턴과 거의 일치하는 텍스트</span><span class="sxs-lookup"><span data-stu-id="1c380-130">• Text that nearly matches the regular expression pattern.</span></span>

<span data-ttu-id="1c380-131">마지막 텍스트 형식은 특히 제한된 입력을 처리하도록 작성된 정규식에서 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-131">The last text type is especially problematic for a regular expression that has been written to handle constrained input.</span></span> <span data-ttu-id="1c380-132">또한 이러한 정규식에 [역추적](backtracking.md)이 광범위하게 사용되는 경우에는 정규식 엔진이 겉보기에는 문제가 없는 텍스트를 처리하느라 비정상적으로 많은 시간(몇 시간 또는 며칠이 걸리는 경우도 있음)을 소비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-132">If that regular expression also relies on extensive [backtracking](backtracking.md), the regular expression engine can spend an inordinate amount of time (in some cases, many hours or days) processing seemingly innocuous text.</span></span> 

> [!WARNING]
> <span data-ttu-id="1c380-133">다음 예제에서는 과도한 역추적을 발생시키고 유효한 전자 메일 주소를 거부할 가능성이 있는 정규식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-133">The following example uses a regular expression that is prone to excessive backtracking and that is likely to reject valid email addresses.</span></span> <span data-ttu-id="1c380-134">전자 메일 유효성 검사 루틴에서 해당 정규식을 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-134">You should not use it in an email validation routine.</span></span> <span data-ttu-id="1c380-135">전자 메일 주소의 유효성을 검사하는 정규식은 [방법: 문자열이 유효한 전자 메일 형식인지 확인](verify-format.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c380-135">If you would like a regular expression that validates email addresses, see [How to: Verify that strings are in valid email format](verify-format.md).</span></span> 


<span data-ttu-id="1c380-136">예를 들어 전자 메일 주소 별칭의 유효성을 검증하기 위해 매우 자주 사용되지만 심각한 문제를 일으킬 수 있는 정규식을 하나 보여드리겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-136">For example, consider a very commonly used but extremely problematic regular expression for validating the alias of an email address.</span></span> <span data-ttu-id="1c380-137">정규식 `^[0-9A-Z]([-.\w]*[0-9A-Z])*$`는 한 개의 영숫자로 시작하고 이어지는 영숫자, 마침표 또는 하이픈이&0;개 이상으로 구성된 텍스트를 유효한 메일 주소로 처리하도록 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-137">The regular expression `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` is written to process what is considered to be a valid email address, which consists of an alphanumeric character, followed by zero or more characters that can be alphanumeric, periods, or hyphens.</span></span> <span data-ttu-id="1c380-138">정규식은 영숫자로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-138">The regular expression must end with an alphanumeric character.</span></span> <span data-ttu-id="1c380-139">하지만 다음 예제에서와 같이 이 정규식은 유효한 입력을 쉽게 처리할 수 있지만 거의 유효한 입력을 처리할 때는 성능이 매우 비효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-139">However, as the following example shows, although this regular expression handles valid input easily, its performance is very inefficient when it is processing nearly valid input.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      Stopwatch sw;    
      string[] addresses = { "AAAAAAAAAAA@contoso.com", 
                             "AAAAAAAAAAaaaaaaaaaa!@contoso.com" };
      // The following regular expression should not actually be used to 
      // validate an email address.
      string pattern = @"^[0-9A-Z]([-.\w]*[0-9A-Z])*$";
      string input; 

      foreach (var address in addresses) {
         string mailBox = address.Substring(0, address.IndexOf("@"));       
         int index = 0;
         for (int ctr = mailBox.Length - 1; ctr >= 0; ctr--) {
            index++;

            input = mailBox.Substring(ctr, index); 
            sw = Stopwatch.StartNew();
            Match m = Regex.Match(input, pattern, RegexOptions.IgnoreCase);
            sw.Stop();
            if (m.Success)
               Console.WriteLine("{0,2}. Matched '{1,25}' in {2}", 
                                 index, m.Value, sw.Elapsed);
            else                     
               Console.WriteLine("{0,2}. Failed  '{1,25}' in {2}", 
                                 index, input, sw.Elapsed);
         }
         Console.WriteLine();
      }
   }
}

// The example displays output similar to the following:
//     1. Matched '                        A' in 00:00:00.0007122
//     2. Matched '                       AA' in 00:00:00.0000282
//     3. Matched '                      AAA' in 00:00:00.0000042
//     4. Matched '                     AAAA' in 00:00:00.0000038
//     5. Matched '                    AAAAA' in 00:00:00.0000042
//     6. Matched '                   AAAAAA' in 00:00:00.0000042
//     7. Matched '                  AAAAAAA' in 00:00:00.0000042
//     8. Matched '                 AAAAAAAA' in 00:00:00.0000087
//     9. Matched '                AAAAAAAAA' in 00:00:00.0000045
//    10. Matched '               AAAAAAAAAA' in 00:00:00.0000045
//    11. Matched '              AAAAAAAAAAA' in 00:00:00.0000045
//    
//     1. Failed  '                        !' in 00:00:00.0000447
//     2. Failed  '                       a!' in 00:00:00.0000071
//     3. Failed  '                      aa!' in 00:00:00.0000071
//     4. Failed  '                     aaa!' in 00:00:00.0000061
//     5. Failed  '                    aaaa!' in 00:00:00.0000081
//     6. Failed  '                   aaaaa!' in 00:00:00.0000126
//     7. Failed  '                  aaaaaa!' in 00:00:00.0000359
//     8. Failed  '                 aaaaaaa!' in 00:00:00.0000414
//     9. Failed  '                aaaaaaaa!' in 00:00:00.0000758
//    10. Failed  '               aaaaaaaaa!' in 00:00:00.0001462
//    11. Failed  '              aaaaaaaaaa!' in 00:00:00.0002885
//    12. Failed  '             Aaaaaaaaaaa!' in 00:00:00.0005780
//    13. Failed  '            AAaaaaaaaaaa!' in 00:00:00.0011628
//    14. Failed  '           AAAaaaaaaaaaa!' in 00:00:00.0022851
//    15. Failed  '          AAAAaaaaaaaaaa!' in 00:00:00.0045864
//    16. Failed  '         AAAAAaaaaaaaaaa!' in 00:00:00.0093168
//    17. Failed  '        AAAAAAaaaaaaaaaa!' in 00:00:00.0185993
//    18. Failed  '       AAAAAAAaaaaaaaaaa!' in 00:00:00.0366723
//    19. Failed  '      AAAAAAAAaaaaaaaaaa!' in 00:00:00.1370108
//    20. Failed  '     AAAAAAAAAaaaaaaaaaa!' in 00:00:00.1553966
//    21. Failed  '    AAAAAAAAAAaaaaaaaaaa!' in 00:00:00.3223372
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim sw As Stopwatch    
      Dim addresses() As String = { "AAAAAAAAAAA@contoso.com", 
                                 "AAAAAAAAAAaaaaaaaaaa!@contoso.com" }
      ' The following regular expression should not actually be used to 
      ' validate an email address.
      Dim pattern As String = "^[0-9A-Z]([-.\w]*[0-9A-Z])*$"
      Dim input As String 

      For Each address In addresses
         Dim mailBox As String = address.Substring(0, address.IndexOf("@"))       
         Dim index As Integer = 0
         For ctr As Integer = mailBox.Length - 1 To 0 Step -1
            index += 1
            input = mailBox.Substring(ctr, index) 
            sw = Stopwatch.StartNew()
            Dim m As Match = Regex.Match(input, pattern, RegexOptions.IgnoreCase)
            sw.Stop()
            if m.Success Then
               Console.WriteLine("{0,2}. Matched '{1,25}' in {2}", 
                                 index, m.Value, sw.Elapsed)
            Else                     
               Console.WriteLine("{0,2}. Failed  '{1,25}' in {2}", 
                                 index, input, sw.Elapsed)
            End If                  
         Next
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays output similar to the following:
'     1. Matched '                        A' in 00:00:00.0007122
'     2. Matched '                       AA' in 00:00:00.0000282
'     3. Matched '                      AAA' in 00:00:00.0000042
'     4. Matched '                     AAAA' in 00:00:00.0000038
'     5. Matched '                    AAAAA' in 00:00:00.0000042
'     6. Matched '                   AAAAAA' in 00:00:00.0000042
'     7. Matched '                  AAAAAAA' in 00:00:00.0000042
'     8. Matched '                 AAAAAAAA' in 00:00:00.0000087
'     9. Matched '                AAAAAAAAA' in 00:00:00.0000045
'    10. Matched '               AAAAAAAAAA' in 00:00:00.0000045
'    11. Matched '              AAAAAAAAAAA' in 00:00:00.0000045
'    
'     1. Failed  '                        !' in 00:00:00.0000447
'     2. Failed  '                       a!' in 00:00:00.0000071
'     3. Failed  '                      aa!' in 00:00:00.0000071
'     4. Failed  '                     aaa!' in 00:00:00.0000061
'     5. Failed  '                    aaaa!' in 00:00:00.0000081
'     6. Failed  '                   aaaaa!' in 00:00:00.0000126
'     7. Failed  '                  aaaaaa!' in 00:00:00.0000359
'     8. Failed  '                 aaaaaaa!' in 00:00:00.0000414
'     9. Failed  '                aaaaaaaa!' in 00:00:00.0000758
'    10. Failed  '               aaaaaaaaa!' in 00:00:00.0001462
'    11. Failed  '              aaaaaaaaaa!' in 00:00:00.0002885
'    12. Failed  '             Aaaaaaaaaaa!' in 00:00:00.0005780
'    13. Failed  '            AAaaaaaaaaaa!' in 00:00:00.0011628
'    14. Failed  '           AAAaaaaaaaaaa!' in 00:00:00.0022851
'    15. Failed  '          AAAAaaaaaaaaaa!' in 00:00:00.0045864
'    16. Failed  '         AAAAAaaaaaaaaaa!' in 00:00:00.0093168
'    17. Failed  '        AAAAAAaaaaaaaaaa!' in 00:00:00.0185993
'    18. Failed  '       AAAAAAAaaaaaaaaaa!' in 00:00:00.0366723
'    19. Failed  '      AAAAAAAAaaaaaaaaaa!' in 00:00:00.1370108
'    20. Failed  '     AAAAAAAAAaaaaaaaaaa!' in 00:00:00.1553966
'    21. Failed  '    AAAAAAAAAAaaaaaaaaaa!' in 00:00:00.3223372
```

<span data-ttu-id="1c380-140">이 예제의 결과에서와 같이 정규식 엔진은 유효한 전자 메일 별칭의 경우 길이에 관계없이 거의 동일한 기간에 처리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-140">As the output from the example shows, the regular expression engine processes the valid email alias in about the same time interval regardless of its length.</span></span> <span data-ttu-id="1c380-141">반면에 문자 수가&5;개 더 많은 거의 유효한 전자 메일 주소의 경우 문자열에 포함된 각 추가 문자마다 처리 시간이 약 두 배로 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-141">On the other hand, when the nearly valid email address has more than five characters, processing time approximately doubles for each additional character in the string.</span></span> <span data-ttu-id="1c380-142">즉, 25개 문자로 구성된 거의 유효한 문자열을 처리하려면 한 시간 이상이 소요되고 거의 유효한 문자열의 문자 수가 33자인 경우 처리하는 데 거의 하루가 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-142">This means that a nearly valid 28-character string would take over an hour to process, and a nearly valid 33-character string would take nearly a day to process.</span></span> 

<span data-ttu-id="1c380-143">이 정규식은 패턴과 일치하는 입력의 형식만 고려하여 개발되었기 때문에 패턴과 일치하지 않는 입력은 고려하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-143">Because this regular expression was developed solely by considering the format of input to be matched, it fails to take account of input that does not match the pattern.</span></span> <span data-ttu-id="1c380-144">따라서 정규식 패턴과 거의 일치하는 제한되지 않은 입력의 경우 성능이 크게 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-144">This, in turn, can allow unconstrained input that nearly matches the regular expression pattern to significantly degrade performance.</span></span>

<span data-ttu-id="1c380-145">이 문제를 해결하기 위해서는 다음과 같이 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-145">To solve this problem, you can do the following:</span></span>

* <span data-ttu-id="1c380-146">패턴을 개발할 때, 특히 정규식이 제한되지 않은 입력을 처리하도록 디자인된 경우 역추적이 정규식 엔진의 성능에 어떤 영향을 줄 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-146">When developing a pattern, you should consider how backtracking might affect the performance of the regular expression engine, particularly if your regular expression is designed to process unconstrained input.</span></span> <span data-ttu-id="1c380-147">자세한 내용은 [역추적 수행](#take-charge-of-backtracking) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c380-147">For more information, see the [Take charge of backtracking](#take-charge-of-backtracking) section.</span></span>

* <span data-ttu-id="1c380-148">유효한 입력뿐만 아니라 유효하지 않은 입력과 거의 유효한 입력을 사용하여 정규식을 철저히 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-148">Thoroughly test your regular expression using invalid and near-valid input as well as valid input.</span></span> <span data-ttu-id="1c380-149">특정 정규식에 대한 입력을 무작위로 생성하려면 Microsoft Research에서 제공되는 정규식 탐색 도구인 [Rex](http://research.microsoft.com/en-us/projects/rex/)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-149">To generate input for a particular regular expression randomly, you can use [Rex](http://research.microsoft.com/en-us/projects/rex/), which is a regular expression exploration tool from Microsoft Research.</span></span>

## <a name="handle-object-instantiation-appropriately"></a><span data-ttu-id="1c380-150">적절한 개체 인스턴스화 처리</span><span class="sxs-lookup"><span data-stu-id="1c380-150">Handle object instantiation appropriately</span></span>

<span data-ttu-id="1c380-151">.NET 정규식 개체 모델의 핵심은 정규식 엔진을 나타내는 [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-151">At the heart of .NET’s regular expression object model is the [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) class, which represents the regular expression engine.</span></span> <span data-ttu-id="1c380-152">대체로 정규식 성능에 영향을 주는 가장 중요한 단일 요소는 [Regex](xref:System.Text.RegularExpressions.Regex) 엔진의 사용 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-152">Often, the single greatest factor that affects regular expression performance is the way in which the [Regex](xref:System.Text.RegularExpressions.Regex) engine is used.</span></span> <span data-ttu-id="1c380-153">정규식을 정의할 때는 정규식 엔진과 정규식 패턴을 긴밀히 연결하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-153">Defining a regular expression involves tightly coupling the regular expression engine with a regular expression pattern.</span></span> <span data-ttu-id="1c380-154">해당 생성자에 정규식 패턴을 전달하여 [Regex](xref:System.Text.RegularExpressions.Regex) 개체를 인스턴스화하거나 분석할 문자열과 함께 정규식 패턴을 전달하여 정적 메서드를 호출하든 간에 이러한 연결 프로세스는 필수적으로 비용이 클 수 밖에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-154">That coupling process, whether it involves instantiating a [Regex](xref:System.Text.RegularExpressions.Regex) object by passing its constructor a regular expression pattern or calling a static method by passing it the regular expression pattern along with the string to be analyzed, is by necessity an expensive one.</span></span>

<span data-ttu-id="1c380-155">정규식 엔진을 특정 정규식 패턴과 연결하고 엔진을 사용하여 여러 가지 방법으로 일치하는 텍스트를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-155">You can couple the regular expression engine with a particular regular expression pattern and then use the engine to match text in several ways:</span></span>

* <span data-ttu-id="1c380-156">[Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String))와 같은 정적 패턴 일치 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-156">You can call a static pattern-matching method, such as [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)).</span></span> <span data-ttu-id="1c380-157">이 방법에서는 정규식 개체를 인스턴스화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-157">This does not require instantiation of a regular expression object.</span></span>

* <span data-ttu-id="1c380-158">[Regex](xref:System.Text.RegularExpressions.Regex) 개체를 인스턴스화하고 해석된 정규식의 인스턴스 패턴 일치 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-158">You can instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object and call an instance pattern-matching method of an interpreted regular expression.</span></span> <span data-ttu-id="1c380-159">이 메서드는 정규식 엔진을 정규식 패턴에 바인딩하는 기본 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-159">This is the default method for binding the regular expression engine to a regular expression pattern.</span></span> <span data-ttu-id="1c380-160">이 메서드는 [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) 플래그를 포함하는 options 인수 없이 [Regex](xref:System.Text.RegularExpressions.Regex) 개체를 인스턴스화할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-160">It results when a [Regex](xref:System.Text.RegularExpressions.Regex) object is instantiated without an options argument that includes the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) flag.</span></span>

* <span data-ttu-id="1c380-161">[Regex](xref:System.Text.RegularExpressions.Regex) 개체를 인스턴스화하고 컴파일된 정규식의 인스턴스 패턴 일치 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-161">You can instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object and call an instance pattern-matching method of a compiled regular expression.</span></span> <span data-ttu-id="1c380-162">정규식 개체는 [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) 플래그를 포함하는 options 인수를 사용하여 [Regex](xref:System.Text.RegularExpressions.Regex) 개체를 인스턴스화할 때 컴파일되는 패턴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-162">Regular expression objects represent compiled patterns when a [Regex](xref:System.Text.RegularExpressions.Regex) object is instantiated with an options argument that includes the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) flag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c380-163">동일한 정규식을 메서드 호출에 반복해서 사용하거나 응용 프로그램에 정규식 개체가 광범위하게 사용될 경우 메서드 호출의 형태(정적, 해석, 컴파일)는 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-163">The form of the method call (static, interpreted, compiled) affects performance if the same regular expression is used repeatedly in method calls, or if an application makes extensive use of regular expression objects.</span></span>
 
### <a name="static-regular-expressions"></a><span data-ttu-id="1c380-164">정적 정규식</span><span class="sxs-lookup"><span data-stu-id="1c380-164">Static regular expressions</span></span>

<span data-ttu-id="1c380-165">정적 정규식 메서드는 동일한 정규식으로 정규식 개체를 반복해서 인스턴스화하기 위한 대안으로 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-165">Static regular expression methods are recommended as an alternative to repeatedly instantiating a regular expression object with the same regular expression.</span></span> <span data-ttu-id="1c380-166">정규식 개체에 사용되는 정규식 패턴과 달리 인스턴스 메서드 호출에 사용된 패턴으로부터 컴파일된 MSIL(Microsoft Intermediate Language)이나 작업 코드는 정규식 엔진에서 내부적으로 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-166">Unlike regular expression patterns used by regular expression objects, either the operation codes or the compiled Microsoft intermediate language (MSIL) from patterns used in instance method calls is cached internally by the regular expression engine.</span></span> 

<span data-ttu-id="1c380-167">예를 들어 메서드를 호출하여 사용자 입력의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-167">For example, you might call a method to validate user input.</span></span> <span data-ttu-id="1c380-168">이 예제에서 `IsValidCurrency` 메서드는 사용자가 통화 기호와 하나 이상의&10;진수를 입력했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-168">In this example, a method named `IsValidCurrency` checks whether the user has entered a currency symbol followed by at least one decimal digit.</span></span> <span data-ttu-id="1c380-169">다음 예제에서는 `IsValidCurrency` 메서드를 구현할 때 매우 비효율적인 형태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-169">A very inefficient implementation of the `IsValidCurrency` method is shown in the following example.</span></span> <span data-ttu-id="1c380-170">메서드를 호출할 때마다 [Regex](xref:System.Text.RegularExpressions.Regex) 개체가 동일한 패턴으로 다시 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-170">Note that each method call reinstantiates a [Regex](xref:System.Text.RegularExpressions.Regex) object with the same pattern.</span></span> <span data-ttu-id="1c380-171">결국 메서드를 호출할 때마다 정규식 패턴을 다시 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-171">This, in turn, means that the regular expression pattern must be recompiled each time the method is called.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class RegexLib
{
   public static bool IsValidCurrency(string currencyValue)
   {
      string pattern = @"\p{Sc}+\s*\d+";
      Regex currencyRegex = new Regex(pattern);
      return currencyRegex.IsMatch(currencyValue);
   }
}
```

```vb
Public Sub OKButton_Click(sender As Object, e As EventArgs) _ 
           Handles OKButton.Click

   If Not String.IsNullOrEmpty(sourceCurrency.Text) Then
      If RegexLib.IsValidCurrency(sourceCurrency.Text) Then
         PerformConversion()
      Else
         status.Text = "The source currency value is invalid."
      End If          
   End If
End Sub
```

<span data-ttu-id="1c380-172">이러한 비효율적인 코드는 정적 [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String)) 메서드 호출로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-172">You should replace this inefficient code with a call to the static [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String)) method.</span></span> <span data-ttu-id="1c380-173">따라서 패턴 일치 메서드를 호출할 때마다 [Regex](xref:System.Text.RegularExpressions.Regex) 개체를 인스턴스화할 필요가 없으며, 정규식 엔진은 캐시에서 컴파일된 버전의 정규식을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-173">This eliminates the need to instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object each time you want to call a pattern-matching method, and enables the regular expression engine to retrieve a compiled version of the regular expression from its cache.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class RegexLib
{
   public static bool IsValidCurrency(string currencyValue)
   {
      string pattern = @"\p{Sc}+\s*\d+";
      return Regex.IsMatch(currencyValue, pattern); 
   }
}
```

```vb
Imports System.Text.RegularExpressions

Public Module RegexLib
   Public Function IsValidCurrency(currencyValue As String) As Boolean
      Dim pattern As String = "\p{Sc}+\s*\d+"
      Return Regex.IsMatch(currencyValue, pattern)
   End Function
End Module
```

<span data-ttu-id="1c380-174">기본적으로 가장 최근에 사용된 15개의 정적 정규식 패턴이 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-174">By default, the last 15 most recently used static regular expression patterns are cached.</span></span> <span data-ttu-id="1c380-175">캐시된 정적 정규식이 대량으로 필요한 응용 프로그램의 경우 [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize) 속성을 설정하여 캐시 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-175">For applications that require a larger number of cached static regular expressions, the size of the cache can be adjusted by setting the [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize) property.</span></span>

<span data-ttu-id="1c380-176">이 예제에서 사용된 정규식 `\p{Sc}+\s*\d+`는 입력 문자열에 통화 기호와 한 자릿수 이상의 숫자가 포함되었는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-176">The regular expression `\p{Sc}+\s*\d+` that is used in this example verifies that the input string consists of a currency symbol and at least one decimal digit.</span></span> <span data-ttu-id="1c380-177">패턴은 다음 표와 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-177">The pattern is defined as shown in the following table.</span></span>

<span data-ttu-id="1c380-178">패턴</span><span class="sxs-lookup"><span data-stu-id="1c380-178">Pattern</span></span> | <span data-ttu-id="1c380-179">설명</span><span class="sxs-lookup"><span data-stu-id="1c380-179">Description</span></span>
------- | -----------
`\p{Sc}+` | <span data-ttu-id="1c380-180">유니코드 기호와 통화 범주에 속하는 하나 이상의 문자가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-180">Match one or more characters in the Unicode Symbol, Currency category.</span></span>
`\s*` | <span data-ttu-id="1c380-181">0개 이상의 공백 문자가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-181">Match zero or more white-space characters.</span></span>
`\d+` | <span data-ttu-id="1c380-182">하나 이상의&10;진수 숫자가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-182">Match one or more decimal digits.</span></span>
 
### <a name="interpreted-vs-compiled-regular-expressions"></a><span data-ttu-id="1c380-183">해석된 정규식 및 컴파일된 정규식</span><span class="sxs-lookup"><span data-stu-id="1c380-183">Interpreted vs. compiled regular expressions</span></span>

<span data-ttu-id="1c380-184">[RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) 옵션의 사양을 통해 정규식 엔진에 바인딩되지 않은 정규식 패턴은 해석된 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-184">Regular expression patterns that are not bound to the regular expression engine through the specification of the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) option are interpreted.</span></span> <span data-ttu-id="1c380-185">정규식 개체가 인스턴스화되면 정규식 엔진이 정규식을 작업 코드 집합으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-185">When a regular expression object is instantiated, the regular expression engine converts the regular expression to a set of operation codes.</span></span> <span data-ttu-id="1c380-186">인스턴스 메서드가 호출되면 이 작업 코드가 MSIL로 변환되고 JIT 컴파일러에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-186">When an instance method is called, the operation codes are converted to MSIL and executed by the JIT compiler.</span></span> <span data-ttu-id="1c380-187">마찬가지로 정적 정규식 메서드를 호출할 때 정규식을 캐시에서 찾을 수 없으면 정규식 엔진이 정규식을 작업 코드 집합으로 변환하고 이를 캐시에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-187">Similarly, when a static regular expression method is called and the regular expression cannot be found in the cache, the regular expression engine converts the regular expression to a set of operation codes and stores them in the cache.</span></span> <span data-ttu-id="1c380-188">그런 다음 이러한 작업 코드를 JIT 컴파일러가 실행할 수 있도록 MSIL로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-188">It then converts these operation codes to MSIL so that the JIT compiler can execute them.</span></span> <span data-ttu-id="1c380-189">해석된 정규식은 실행 시간을 늘리는 대신 시작 시간을 줄여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-189">Interpreted regular expressions reduce startup time at the cost of slower execution time.</span></span> <span data-ttu-id="1c380-190">따라서 해석된 정규식은 소규모 메서드 호출에서 정규식을 사용하거나 정규식 메서드에 대한 정확한 호출 수를 알 수 없지만 그래도 그 수가 적을 것으로 예상되는 경우에 사용하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-190">Because of this, they are best used when the regular expression is used in a small number of method calls, or if the exact number of calls to regular expression methods is unknown but is expected to be small.</span></span> <span data-ttu-id="1c380-191">메서드 호출 수가 늘어나면 느려진 실행 속도로 인해 줄어든 시작 시간의 성능 이점이 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-191">As the number of method calls increases, the performance gain from reduced startup time is outstripped by the slower execution speed.</span></span>

<span data-ttu-id="1c380-192">[RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) 옵션의 사양을 통해 정규식 엔진에 바인딩된 정규식 패턴은 컴파일된 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-192">Regular expression patterns that are bound to the regular expression engine through the specification of the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) option are compiled.</span></span> <span data-ttu-id="1c380-193">즉, 정규식 개체가 인스턴스화되거나 정적 정규식 메서드가 호출될 때 캐시에서 정규식을 찾을 수 없으면 정규식 엔진이 정규식을 중간 상태의 작업 코드 집합으로 변환하고 그런 다음 MSIL로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-193">This means that, when a regular expression object is instantiated, or when a static regular expression method is called and the regular expression cannot be found in the cache, the regular expression engine converts the regular expression to an intermediary set of operation codes, which it then converts to MSIL.</span></span> <span data-ttu-id="1c380-194">메서드를 호출하면 JIT가 이 MSIL을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-194">When a method is called, the JIT compiler executes the MSIL.</span></span> <span data-ttu-id="1c380-195">해석된 정규식과는 달리 컴파일된 정규식은 시작 시간이 늘어나지만 개별 패턴 일치 메서드의 실행 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-195">In contrast to interpreted regular expressions, compiled regular expressions increase startup time but execute individual pattern-matching methods faster.</span></span> <span data-ttu-id="1c380-196">따라서 정규식을 컴파일하여 얻을 수 있는 성능 이점은 정규식 메서드가 호출되는 횟수에 비례하여 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-196">As a result, the performance benefit that results from compiling the regular expression increases in proportion to the number of regular expression methods called.</span></span>

<span data-ttu-id="1c380-197">요약하면, 특정 정규식에 대한 정규식 메서드 호출이 비교적 적게 수행될 경우 해석된 정규식을 사용하는 것이 좋으며,</span><span class="sxs-lookup"><span data-stu-id="1c380-197">To summarize, we recommend that you use interpreted regular expressions when you call regular expression methods with a specific regular expression relatively infrequently.</span></span> <span data-ttu-id="1c380-198">특정 정규식에 대한 정규식 메서드 호출이 비교적 자주 수행될 경우 컴파일된 정규식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-198">You should use compiled regular expressions when you call regular expression methods with a specific regular expression relatively frequently.</span></span> <span data-ttu-id="1c380-199">해석된 정규식의 실행 속도 감소가 줄어든 시작 시간으로 인해 얻게 된 이점보다 더 커지거나, 컴파일된 정규식의 느려진 시작 시간이 빨라진 실행 속도의 이점보다 더 커지게 되는 정확한 임계점은 쉽게 결정할 수 없는 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-199">The exact threshold at which the slower execution speeds of interpreted regular expressions outweigh gains from their reduced startup time, or the threshold at which the slower startup times of compiled regular expressions outweigh gains from their faster execution speeds, is difficult to determine.</span></span> <span data-ttu-id="1c380-200">이러한 임계점은 정규식의 복잡성과 정규식으로 처리되는 특정 데이터를 비롯한 다양한 요소들에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-200">It depends on a variety of factors, including the complexity of the regular expression and the specific data that it processes.</span></span> <span data-ttu-id="1c380-201">특정 응용 프로그램 시나리오에서 해석된 정규식과 컴파일된 정규식 중 어느 쪽의 성능이 더 좋은지 확인하기 위해 [Stopwatch](xref:System.Diagnostics.Stopwatch) 클래스를 사용하여 각각의 실행 시간을 비교해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-201">To determine whether interpreted or compiled regular expressions offer the best performance for your particular application scenario, you can use the [Stopwatch](xref:System.Diagnostics.Stopwatch) class to compare their execution times.</span></span>

<span data-ttu-id="1c380-202">다음 예제에서는 Theodore Dreiser가 저술한 The Financier 책에서 처음&10;개의 문장을 읽을 때와 모든 문장을 읽을 때 컴파일된 정규식과 해석된 정규식의 성능 차이를 비교해서 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-202">The following example compares the performance of compiled and interpreted regular expressions when reading the first ten sentences and when reading all the sentences in the text of Theodore Dreiser's The Financier.</span></span> <span data-ttu-id="1c380-203">아래 예제의 결과에서와 같이 정규식 일치 메서드를&10;번만 호출할 경우에는 해석된 정규식이 컴파일된 정규식보다 나은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-203">As the output from the example shows, when only ten calls are made to regular expression matching methods, an interpreted regular expression offers better performance than a compiled regular expression.</span></span> <span data-ttu-id="1c380-204">하지만 호출 횟수가 많은 경우에는(아래 예에서는 13,000번 이상) 컴파일된 정규식이 더 나은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-204">However, a compiled regular expression offers better performance when a large number of calls (in this case, over 13,000) are made.</span></span> 

```csharp
using System;
using System.Diagnostics;
using System.IO;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]";
      Stopwatch sw;
      Match match;
      int ctr;

      StreamReader inFile = new StreamReader(@".\Dreiser_TheFinancier.txt");
      string input = inFile.ReadToEnd();
      inFile.Close();

      // Read first ten sentences with interpreted regex.
      Console.WriteLine("10 Sentences with Interpreted Regex:");
      sw = Stopwatch.StartNew();
      Regex int10 = new Regex(pattern, RegexOptions.Singleline);
      match = int10.Match(input);
      for (ctr = 0; ctr <= 9; ctr++) {
         if (match.Success)
            // Do nothing with the match except get the next match.
            match = match.NextMatch();
         else
            break;
      }
      sw.Stop();
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed);

      // Read first ten sentences with compiled regex.
      Console.WriteLine("10 Sentences with Compiled Regex:");
      sw = Stopwatch.StartNew();
      Regex comp10 = new Regex(pattern, 
                   RegexOptions.Singleline | RegexOptions.Compiled);
      match = comp10.Match(input);
      for (ctr = 0; ctr <= 9; ctr++) {
         if (match.Success)
            // Do nothing with the match except get the next match.
            match = match.NextMatch();
         else
            break;
      }
      sw.Stop();
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed);

      // Read all sentences with interpreted regex.
      Console.WriteLine("All Sentences with Interpreted Regex:");
      sw = Stopwatch.StartNew();
      Regex intAll = new Regex(pattern, RegexOptions.Singleline);
      match = intAll.Match(input);
      int matches = 0;
      while (match.Success) {
         matches++;
         // Do nothing with the match except get the next match.
         match = match.NextMatch();
      }
      sw.Stop();
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed);

      // Read all sentnces with compiled regex.
      Console.WriteLine("All Sentences with Compiled Regex:");
      sw = Stopwatch.StartNew();
      Regex compAll = new Regex(pattern, 
                      RegexOptions.Singleline | RegexOptions.Compiled);
      match = compAll.Match(input);
      matches = 0;
      while (match.Success) {
         matches++;
         // Do nothing with the match except get the next match.
         match = match.NextMatch();
      }
      sw.Stop();
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed);      
   }
}
// The example displays the following output:
//       10 Sentences with Interpreted Regex:
//          10 matches in 00:00:00.0047491
//       10 Sentences with Compiled Regex:
//          10 matches in 00:00:00.0141872
//       All Sentences with Interpreted Regex:
//          13,443 matches in 00:00:01.1929928
//       All Sentences with Compiled Regex:
//          13,443 matches in 00:00:00.7635869
//       
//       >compare1
//       10 Sentences with Interpreted Regex:
//          10 matches in 00:00:00.0046914
//       10 Sentences with Compiled Regex:
//          10 matches in 00:00:00.0143727
//       All Sentences with Interpreted Regex:
//          13,443 matches in 00:00:01.1514100
//       All Sentences with Compiled Regex:
//          13,443 matches in 00:00:00.7432921
```

```vb
Imports System.Diagnostics
Imports System.IO
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]"
      Dim sw As Stopwatch
      Dim match As Match
      Dim ctr As Integer

      Dim inFile As New StreamReader(".\Dreiser_TheFinancier.txt")
      Dim input As String = inFile.ReadToEnd()
      inFile.Close()

      ' Read first ten sentences with interpreted regex.
      Console.WriteLine("10 Sentences with Interpreted Regex:")
      sw = Stopwatch.StartNew()
      Dim int10 As New Regex(pattern, RegexOptions.SingleLine)
      match = int10.Match(input)
      For ctr = 0 To 9
         If match.Success Then
            ' Do nothing with the match except get the next match.
            match = match.NextMatch()
         Else
            Exit For
         End If
      Next
      sw.Stop()
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed)

      ' Read first ten sentences with compiled regex.
      Console.WriteLine("10 Sentences with Compiled Regex:")
      sw = Stopwatch.StartNew()
      Dim comp10 As New Regex(pattern, 
                   RegexOptions.SingleLine Or RegexOptions.Compiled)
      match = comp10.Match(input)
      For ctr = 0 To 9
         If match.Success Then
            ' Do nothing with the match except get the next match.
            match = match.NextMatch()
         Else
            Exit For
         End If
      Next
      sw.Stop()
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed)

      ' Read all sentences with interpreted regex.
      Console.WriteLine("All Sentences with Interpreted Regex:")
      sw = Stopwatch.StartNew()
      Dim intAll As New Regex(pattern, RegexOptions.SingleLine)
      match = intAll.Match(input)
      Dim matches As Integer = 0
      Do While match.Success
         matches += 1
         ' Do nothing with the match except get the next match.
         match = match.NextMatch()
      Loop
      sw.Stop()
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed)

      ' Read all sentnces with compiled regex.
      Console.WriteLine("All Sentences with Compiled Regex:")
      sw = Stopwatch.StartNew()
      Dim compAll As New Regex(pattern, 
                     RegexOptions.SingleLine Or RegexOptions.Compiled)
      match = compAll.Match(input)
      matches = 0
      Do While match.Success
         matches += 1
         ' Do nothing with the match except get the next match.
         match = match.NextMatch()
      Loop
      sw.Stop()
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed)      
   End Sub
End Module
' The example displays output like the following:
'       10 Sentences with Interpreted Regex:
'          10 matches in 00:00:00.0047491
'       10 Sentences with Compiled Regex:
'          10 matches in 00:00:00.0141872
'       All Sentences with Interpreted Regex:
'          13,443 matches in 00:00:01.1929928
'       All Sentences with Compiled Regex:
'          13,443 matches in 00:00:00.7635869
'       
'       >compare1
'       10 Sentences with Interpreted Regex:
'          10 matches in 00:00:00.0046914
'       10 Sentences with Compiled Regex:
'          10 matches in 00:00:00.0143727
'       All Sentences with Interpreted Regex:
'          13,443 matches in 00:00:01.1514100
'       All Sentences with Compiled Regex:
'          13,443 matches in 00:00:00.7432921
```

<span data-ttu-id="1c380-205">이 예제에 사용된 정규식 패턴 `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]`는 다음 표와 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-205">The regular expression pattern used in the example, `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]`, is defined as shown in the following table.</span></span>

<span data-ttu-id="1c380-206">패턴</span><span class="sxs-lookup"><span data-stu-id="1c380-206">Pattern</span></span> | <span data-ttu-id="1c380-207">설명</span><span class="sxs-lookup"><span data-stu-id="1c380-207">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="1c380-208">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-208">Begin the match at a word boundary.</span></span>
`\w+` | <span data-ttu-id="1c380-209">하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-209">Match one or more word characters.</span></span>
<span data-ttu-id="1c380-210">\`(\r?\n)</span><span class="sxs-lookup"><span data-stu-id="1c380-210">\`(\r?\n)</span></span>|<span data-ttu-id="1c380-211">,?\s)\`</span><span class="sxs-lookup"><span data-stu-id="1c380-211">,?\s)\`</span></span> | <span data-ttu-id="1c380-212">0개 이상의 캐리지 리턴과 이어지는 줄 바꿈 문자 또는&0;개 이상의 쉼표와 이어지는 공백 문자가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-212">Match either zero or one carriage return followed by a newline character, or zero or one comma followed by a white-space character.</span></span>
<span data-ttu-id="1c380-213">\`(\w+((\r?\n)</span><span class="sxs-lookup"><span data-stu-id="1c380-213">\`(\w+((\r?\n)</span></span>|<span data-ttu-id="1c380-214">,?\s))*\`</span><span class="sxs-lookup"><span data-stu-id="1c380-214">,?\s))*\`</span></span> | <span data-ttu-id="1c380-215">0개 이상의 캐리지 리턴과 줄 바꿈 문자 또는&0;개 이상의 쉼표와 공백 문자로 이어지는 한 글자 이상의 단어가 적어도 한 번 이상 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-215">Match zero or more occurrences of one or more word characters that are followed either by zero or one carriage return and a newline character, or by zero or one comma followed by a white-space character.</span></span>
`\w+` | <span data-ttu-id="1c380-216">하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-216">Match one or more word characters.</span></span>
`[.?:;!]` | <span data-ttu-id="1c380-217">마침표, 물음표, 콜론, 세미콜론 또는 느낌표가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-217">Match a period, question mark, colon, semicolon, or exclamation point.</span></span>
 
## <a name="take-charge-of-backtracking"></a><span data-ttu-id="1c380-218">역추적 수행</span><span class="sxs-lookup"><span data-stu-id="1c380-218">Take charge of backtracking</span></span>

<span data-ttu-id="1c380-219">일반적으로 정규식 엔진은 선형 진행을 통해 입력 문자열 내를 이동하면서 입력 문자열을 정규식 패턴과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-219">Ordinarily, the regular expression engine uses linear progression to move through an input string and compare it to a regular expression pattern.</span></span> <span data-ttu-id="1c380-220">하지만 정규식 패턴에 __*__, **+** 및 **?**와 같은 확정되지 않은 수량자가</span><span class="sxs-lookup"><span data-stu-id="1c380-220">However, when indeterminate quantifiers such as __*__, **+**, and **?**</span></span> <span data-ttu-id="1c380-221">사용될 경우 정규식 엔진은 일부 성공한 부분 일치를 포기하고, 전체 패턴이 일치하는 항목을 찾기 위해 이전에 저장한 상태로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-221">are used in a regular expression pattern, the regular expression engine may give up a portion of successful partial matches and return to a previously saved state in order to search for a successful match for the entire pattern.</span></span> <span data-ttu-id="1c380-222">이 프로세스를 역추적이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-222">This process is known as backtracking.</span></span>

> [!NOTE]
> <span data-ttu-id="1c380-223">역추적에 대한 자세한 내용은 [정규식 동작 정보](regex-behavior.md) 및 [정규식의 역추적](backtracking.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c380-223">For more information on backtracking, see [Details of regular expression behavior](regex-behavior.md) and [Backtracking in regular expressions](backtracking.md).</span></span>
 
<span data-ttu-id="1c380-224">역추적을 지원할 경우 정규식에 성능과 유연성이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-224">Support for backtracking gives regular expressions power and flexibility.</span></span> <span data-ttu-id="1c380-225">또한 정규식 개발자에게 정규식 엔진의 작동에 대한 제어 책임을 맡길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-225">It also places the responsibility for controlling the operation of the regular expression engine in the hands of regular expression developers.</span></span> <span data-ttu-id="1c380-226">개발자가 이러한 책임을 인식하지 못하는 경우가 많기 때문에 역추적을 오용하거나 과도하게 사용하여 정규식 성능이 저하되는 경우가 자주 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-226">Because developers are often not aware of this responsibility, their misuse of backtracking or reliance on excessive backtracking often plays the most significant role in degrading regular expression performance.</span></span> <span data-ttu-id="1c380-227">최악의 시나리오에서는 실행 시간이 입력 문자열에 있는 추가 문자마다 두 배씩 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-227">In a worst-case scenario, execution time can double for each additional character in the input string.</span></span> <span data-ttu-id="1c380-228">실제로 역추적을 과도하게 사용할 경우에는 입력이 정규식 패턴과 거의 일치할 경우 프로그래밍 면에서 무한 루프를 만드는 것과 동일한 결과를 가져올 수 있으며 정규식 엔진이 비교적 간단한 입력 문자열이라도 처리하는 데 몇 시간 또는 심지어 며칠이 걸릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-228">In fact, by using backtracking excessively, it is easy to create the programmatic equivalent of an endless loop if input nearly matches the regular expression pattern; the regular expression engine may take hours or even days to process a relatively short input string.</span></span>

<span data-ttu-id="1c380-229">역추적이 일치하는 문자열 검색에 반드시 필요하지 않더라도 응용 프로그램에서 역추적을 사용하기 위해 성능상의 이점을 포기하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-229">Often, applications pay a performance penalty for using backtracking despite the fact that backtracking is not essential for a match.</span></span> <span data-ttu-id="1c380-230">예를 들어 `\b\p{Lu}\w*\b`는 다음 표와 같이 대문자로 시작하는 모든 단어를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-230">For example, the regular expression `\b\p{Lu}\w*\b` matches all words that begin with an uppercase character, as the following table shows.</span></span>

<span data-ttu-id="1c380-231">패턴</span><span class="sxs-lookup"><span data-stu-id="1c380-231">Pattern</span></span> | <span data-ttu-id="1c380-232">설명</span><span class="sxs-lookup"><span data-stu-id="1c380-232">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="1c380-233">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-233">Begin the match at a word boundary.</span></span>
`\p{Lu}` | <span data-ttu-id="1c380-234">대문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-234">Match an uppercase character.</span></span>
`\w*` | <span data-ttu-id="1c380-235">0개 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-235">Match zero or more word characters.</span></span>
`\b` | <span data-ttu-id="1c380-236">단어 경계에서 일치 항목 찾기를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-236">End the match at a word boundary.</span></span>
 
<span data-ttu-id="1c380-237">단어 경계는 단어 문자 또는 단어 문자의 일부와 동일하지 않으므로 정규식 엔진이 단어 문자를 찾을 때 단어 경계를 벗어날 가능성은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-237">Because a word boundary is not the same as, or a subset of, a word character, there is no possibility that the regular expression engine will cross a word boundary when matching word characters.</span></span> <span data-ttu-id="1c380-238">즉, 이 정규식의 경우 역추적은 전반적인 문자열 검색 성능에 전혀 기여할 수 없으며, 정규식 엔진이 각각의 단어 문자에 대해 성공한 예비 검색에 대한 상태를 강제로 저장해야 하기 때문에 성능 저하만 유발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-238">This means that for this regular expression, backtracking can never contribute to the overall success of any match -- it can only degrade performance, because the regular expression engine is forced to save its state for each successful preliminary match of a word character.</span></span>

<span data-ttu-id="1c380-239">역추적이 필수가 아니라고 판단될 경우에는 **(?>**_subexpression_**)** 언어 요소를 사용하여 역추적을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-239">If you determine that backtracking is not necessary, you can disable it by using the **(?>**_subexpression_**)** language element.</span></span> <span data-ttu-id="1c380-240">다음 예제에서는 두 개의 정규식을 사용하여 입력 문자열의 구문을 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-240">The following example parses an input string by using two regular expressions.</span></span> <span data-ttu-id="1c380-241">첫 번째 정규식인 `\b\p{Lu}\w*\b`에는 역추적이 사용되고,</span><span class="sxs-lookup"><span data-stu-id="1c380-241">The first, `\b\p{Lu}\w*\b`, relies on backtracking.</span></span> <span data-ttu-id="1c380-242">두 번째 정규식인 `\b\p{Lu}(?>\w*)\b`에는 역추적이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-242">The second, `\b\p{Lu}(?>\w*)\b`, disables backtracking.</span></span> <span data-ttu-id="1c380-243">아래 예제의 결과에서와 같이 두 정규식 모두 동일한 결과를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-243">As the output from the example shows, they both produce the same result.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This this word Sentence name Capital";
      string pattern = @"\b\p{Lu}\w*\b";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);

      Console.WriteLine();

      pattern = @"\b\p{Lu}(?>\w*)\b";   
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       This
//       Sentence
//       Capital
//       
//       This
//       Sentence
//       Capital
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This this word Sentence name Capital"
      Dim pattern As String = "\b\p{Lu}\w*\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
      Console.WriteLine()

      pattern = "\b\p{Lu}(?>\w*)\b"   
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       This
'       Sentence
'       Capital
'       
'       This
'       Sentence
'       Capital
```

<span data-ttu-id="1c380-244">많은 경우에 정규식 패턴을 입력 텍스트에 일치시키기 위해서는 역추적이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-244">In many cases, backtracking is essential for matching a regular expression pattern to input text.</span></span> <span data-ttu-id="1c380-245">그러나 과도한 역추적은 심각한 성능 저하를 가져오고 응용 프로그램이 응답을 멈춘 것과 같은 인상을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-245">However, excessive backtracking can severely degrade performance and create the impression that an application has stopped responding.</span></span> <span data-ttu-id="1c380-246">특히 수량자가 중첩되어 있고 외부 하위 식과 일치하는 텍스트가 내부 하위 식과 일치하는 텍스트의 하위 집합인 경우 문제가 더 심각해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-246">In particular, this happens when quantifiers are nested and the text that matches the outer subexpression is a subset of the text that matches the inner subexpression.</span></span> 

> [!WARNING]
> <span data-ttu-id="1c380-247">과도한 역추적을 방지하는 것 외에도 과도한 역추적이 정규식 성능을 심각하게 저하시키지 않도록 시간 제한 기능을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-247">In addition to avoiding excessive backtracking, you should use the timeout feature to ensure that excessive backtracking does not severely degrade regular expression performance.</span></span> <span data-ttu-id="1c380-248">자세한 내용은 [시간 제한 값 사용](#use-time-out-values) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c380-248">For more information, see the [Use time-out values](#use-time-out-values) section.</span></span>
 
<span data-ttu-id="1c380-249">예를 들어 정규식 패턴 `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$`는 영숫자 문자가 한 개 이상 포함된 부품 번호를 확인하기 위한 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-249">For example, the regular expression pattern `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` is intended to match a part number that consists of at least one alphanumeric character.</span></span> <span data-ttu-id="1c380-250">마지막 문자는 영숫자여야 하지만 영숫자 문자, 하이픈, 밑줄 또는 마침표가 추가될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-250">Any additional characters can consist of an alphanumeric character, a hyphen, an underscore, or a period, though the last character must be alphanumeric.</span></span> <span data-ttu-id="1c380-251">달러 기호는 부품 번호의 종료 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-251">A dollar sign terminates the part number.</span></span> <span data-ttu-id="1c380-252">수량자가 중첩되어 있고 하위 식 `[0-9A-Z]`가 하위 식 `[-.\w]*`의 하위 집합이기 때문에 일부 경우에는 이 정규식 패턴으로 인해 성능이 극히 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-252">In some cases, this regular expression pattern can exhibit extremely poor performance because quantifiers are nested, and because the subexpression `[0-9A-Z]` is a subset of the subexpression `[-.\w]*`.</span></span>

<span data-ttu-id="1c380-253">이러한 경우 중첩된 수량자를 제거하고 외부 하위 식을 길이가&0;인 lookahead 또는 lookbehind 어설션으로 바꿔서 정규식 성능을 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-253">In these cases, you can optimize regular expression performance by removing the nested quantifiers and replacing the outer subexpression with a zero-width lookahead or lookbehind assertion.</span></span> <span data-ttu-id="1c380-254">Lookahead 및 lookbehind 어설션은 앵커이므로 입력 문자열에서 포인터를 이동하지는 않지만 대신 이전 또는 이후 부분을 조회하여 지정된 조건이 충족되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-254">Lookahead and lookbehind assertions are anchors; they do not move the pointer in the input string, but instead look ahead or behind to check whether a specified condition is met.</span></span> <span data-ttu-id="1c380-255">예를 들어 부품 번호 정규식은 `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`로 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-255">For example, the part number regular expression can be rewritten as `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`.</span></span> <span data-ttu-id="1c380-256">이 정규식 패턴은 다음 표에서와 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-256">This regular expression pattern is defined as shown in the following table.</span></span>

<span data-ttu-id="1c380-257">패턴</span><span class="sxs-lookup"><span data-stu-id="1c380-257">Pattern</span></span> | <span data-ttu-id="1c380-258">설명</span><span class="sxs-lookup"><span data-stu-id="1c380-258">Description</span></span>
------- | -----------
`^` | <span data-ttu-id="1c380-259">입력 문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-259">Begin the match at the beginning of the input string.</span></span>
`[0-9A-Z]` | <span data-ttu-id="1c380-260">일치하는 영숫자 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-260">Match an alphanumeric character.</span></span> <span data-ttu-id="1c380-261">부품 번호는 적어도 이 문자 이상으로 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-261">The part number must consist of at least this character.</span></span>
`[-.\w]*` | <span data-ttu-id="1c380-262">단어 문자, 하이픈 또는 마침표로 구성된&0;개 이상의 일치 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-262">Match zero or more occurrences of any word character, hyphen, or period.</span></span>
<span data-ttu-id="1c380-263">\`\$]</span><span class="sxs-lookup"><span data-stu-id="1c380-263">\`\$]</span></span> | <span data-ttu-id="1c380-264">달러 기호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-264">Match a dollar sign.</span></span>
`(?<=[0-9A-Z])` | <span data-ttu-id="1c380-265">종료 문자인 달러 기호의 앞 부분을 조회하여 이전 문자가 영숫자인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-265">Look ahead of the ending dollar sign to ensure that the previous character is alphanumeric.</span></span>
<span data-ttu-id="1c380-266">`$` 입력 문자열의 끝 부분에서 찾기를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-266">`$` End the match at the end of the input string.</span></span>
 
<span data-ttu-id="1c380-267">다음 예제에서는 이 정규식을 사용하여 부품 번호가 포함될 수 있는 배열을 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-267">The following example illustrates the use of this regular expression to match an array containing possible part numbers.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$";
      string[] partNos = { "A1C$", "A4", "A4$", "A1603D$", "A1603D#" };

      foreach (var input in partNos) {
         Match match = Regex.Match(input, pattern);
         if (match.Success)
            Console.WriteLine(match.Value);
         else
            Console.WriteLine("Match not found.");
      }      
   }
}
// The example displays the following output:
//       A1C$
//       Match not found.
//       A4$
//       A1603D$
//       Match not found.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$"
      Dim partNos() As String = { "A1C$", "A4", "A4$", "A1603D$", 
                                  "A1603D#" }

      For Each input As String In partNos
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine(match.Value)
         Else
            Console.WriteLine("Match not found.")
         End If
      Next      
   End Sub
End Module
' The example displays the following output:
'       A1C$
'       Match not found.
'       A4$
'       A1603D$
'       Match not found.
```

<span data-ttu-id="1c380-268">.NET의 정규식 언어에는 중첩된 수량자를 제거하는 데 사용할 수 있는 다음과 같은 언어 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-268">The regular expression language in .NET includes the following language elements that you can use to eliminate nested quantifiers.</span></span> <span data-ttu-id="1c380-269">자세한 내용은 [정규식의 그룹화 구문](grouping.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c380-269">For more information, see [Grouping constructs in regular expressions](grouping.md).</span></span>

<span data-ttu-id="1c380-270">언어 요소</span><span class="sxs-lookup"><span data-stu-id="1c380-270">Language element</span></span> | <span data-ttu-id="1c380-271">설명</span><span class="sxs-lookup"><span data-stu-id="1c380-271">Description</span></span>
---------------- | ----------- 
<span data-ttu-id="1c380-272">**(?**=_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="1c380-272">**(?**=_subexpression_**)**</span></span> | <span data-ttu-id="1c380-273">너비가&0;인 긍정 lookahead입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-273">Zero-width positive lookahead.</span></span> <span data-ttu-id="1c380-274">*subexpression*이 입력 문자열과 일치하는지 확인하기 위해 현재 위치의 앞부분을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-274">Look ahead of the current position to determine whether *subexpression* matches the input string.</span></span>
<span data-ttu-id="1c380-275">**(?!**_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="1c380-275">**(?!**_subexpression_**)**</span></span> | <span data-ttu-id="1c380-276">너비가&0;인 부정 lookahead입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-276">Zero-width negative lookahead.</span></span> <span data-ttu-id="1c380-277">*subexpression*이 입력 문자열과 일치하지 않는지 확인하기 위해 현재 위치의 앞부분을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-277">Look ahead of the current position to determine whether *subexpression* does not match the input string.</span></span>
<span data-ttu-id="1c380-278">**(?<**=_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="1c380-278">**(?<**=_subexpression_**)**</span></span> | <span data-ttu-id="1c380-279">너비가&0;인 긍정 lookbehind입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-279">Zero-width positive lookbehind.</span></span> <span data-ttu-id="1c380-280">*subexpression*이 입력 문자열과 일치하는지 확인하기 위해 현재 위치의 뒷부분을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-280">Look behind the current position to determine whether *subexpression* matches the input string.</span></span>
<span data-ttu-id="1c380-281">**(?<!**_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="1c380-281">**(?<!**_subexpression_**)**</span></span> | <span data-ttu-id="1c380-282">너비가&0;인 부정 lookbehind입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-282">Zero-width negative lookbehind.</span></span> <span data-ttu-id="1c380-283">*subexpression*이 입력 문자열과 일치하지 않는지 확인하기 위해 현재 위치의 뒷부분을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-283">Look behind the current position to determine whether *subexpression* does not match the input string.</span></span>
 
## <a name="use-time-out-values"></a><span data-ttu-id="1c380-284">시간 제한 값 사용</span><span class="sxs-lookup"><span data-stu-id="1c380-284">Use time-out values</span></span>

<span data-ttu-id="1c380-285">정규식이 정규식 패턴과 거의 일치하는 입력을 처리할 경우 정규식 성능에 크게 영향을 주는 과도한 역추적이 사용되는 경우로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-285">If your regular expressions processes input that nearly matches the regular expression pattern, it can often rely on excessive backtracking, which impacts its performance significantly.</span></span> <span data-ttu-id="1c380-286">거의 일치하는 입력에 대해 정규식 역추적 및 테스트 사용을 신중하게 고려하는 것은 물론 과도한 역추적으로 발생할 영향을 최소화하려면 항상 시간 제한 값을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-286">In addition to carefully considering your use of backtracking and testing the regular expression against near-matching input, you should always set a time-out value to ensure that the impact of excessive backtracking, if it occurs, is minimized.</span></span>

<span data-ttu-id="1c380-287">정규식 시간 제한 간격은 정규식 엔진이 시간 초과되기 전에 하나의 일치 항목을 찾는 기간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-287">The regular expression time-out interval defines the period of time that the regular expression engine will look for a single match before it times out.</span></span> <span data-ttu-id="1c380-288">기본 시간 제한 간격은 정규식이 시간 초과되지 않음을 의미하는 [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-288">The default time-out interval is [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout), which means that the regular expression will not time out.</span></span> <span data-ttu-id="1c380-289">다음과 같이 이 값을 재정의하고 시간 제한 간격을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-289">You can override this value and define a time-out interval as follows:</span></span> 

* <span data-ttu-id="1c380-290">[Regex(String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) 생성자를 호출하여 [Regex](xref:System.Text.RegularExpressions.Regex) 개체를 인스턴스화할 때 시간 제한 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-290">By providing a time-out value when you instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object by calling the [Regex(String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) constructor.</span></span>

* <span data-ttu-id="1c380-291">*matchTimeout* 매개 변수를 포함하는 정적 패턴 일치 메서드(예: [Regex.Match(String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) 또는 [Regex.Replace(String, String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)))를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-291">By calling a static pattern matching method, such as [Regex.Match(String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) or [Regex.Replace(String, String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)), that includes a *matchTimeout* parameter.</span></span>

<span data-ttu-id="1c380-292">시간 제한 간격을 정의하고 그 간격의 끝에서 일치 항목을 찾을 수 없는 경우 정규식 메서드에서 [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException) 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-292">If you have defined a time-out interval and a match is not found at the end of that interval, the regular expression method throws a [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException) exception.</span></span> <span data-ttu-id="1c380-293">예외 처리기에서 더 긴 시간 제한 간격으로 일치를 다시 시도하거나, 일치 시도를 중단하고 일치 항목이 없다고 가정하거나, 일치 시도를 중단하고 나중에 분석하기 위해 예외 정보를 로그에 기록할지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-293">In your exception handler, you can choose to retry the match with a longer time-out interval, abandon the match attempt and assume that there is no match, or abandon the match attempt and log the exception information for future analysis.</span></span>

<span data-ttu-id="1c380-294">다음 예제에서는 텍스트 문서의 단어 수 및 단어의 문자 평균 수를 계산하기 위해 350밀리초의 시간 제한 간격으로 정규식을 인스턴스화하는 `GetWordData` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-294">The following example defines a `GetWordData` method that instantiates a regular expression with a time-out interval of 350 milliseconds to calculate the number of words and average number of characters in a word in a text document.</span></span> <span data-ttu-id="1c380-295">작업 시간 제한이 일치할 경우 시간 제한 간격은 350밀리초로 증가되며 [Regex](xref:System.Text.RegularExpressions.Regex) 개체를 다시 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-295">If the matching operation times out, the time-out interval is increased by 350 milliseconds and the [Regex](xref:System.Text.RegularExpressions.Regex) object is re-instantiated.</span></span> <span data-ttu-id="1c380-296">새 시간 제한 간격이 1초 초과할 경우 메서드는 호출자에게 예외를 다시 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-296">If the new time-out interval exceeds 1 second, the method re-throws the exception to the caller.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      RegexUtilities util = new RegexUtilities();
      string title = "Doyle - The Hound of the Baskervilles.txt";
      try {
         var info = util.GetWordData(title);
         Console.WriteLine("Words:               {0:N0}", info.Item1);
         Console.WriteLine("Average Word Length: {0:N2} characters", info.Item2); 
      }
      catch (IOException e) {
         Console.WriteLine("IOException reading file '{0}'", title);
         Console.WriteLine(e.Message);
      }
      catch (RegexMatchTimeoutException e) {
         Console.WriteLine("The operation timed out after {0:N0} milliseconds", 
                           e.MatchTimeout.TotalMilliseconds);
      }
   }
}

public class RegexUtilities
{
   public Tuple<int, double> GetWordData(string filename)
   { 
      const int MAX_TIMEOUT = 1000;   // Maximum timeout interval in milliseconds.
      const int INCREMENT = 350;      // Milliseconds increment of timeout.

      List<string> exclusions = new List<string>( new string[] { "a", "an", "the" });
      int[] wordLengths = new int[29];        // Allocate an array of more than ample size.
      string input = null;
      StreamReader sr = null;
      try { 
         sr = new StreamReader(filename);
         input = sr.ReadToEnd();
      }
      catch (FileNotFoundException e) {
         string msg = String.Format("Unable to find the file '{0}'", filename);
         throw new IOException(msg, e);
      }
      catch (IOException e) {
         throw new IOException(e.Message, e);
      }
      finally {
         if (sr != null) sr.Close(); 
      }

      int timeoutInterval = INCREMENT;
      bool init = false;
      Regex rgx = null;
      Match m = null;
      int indexPos = 0;  
      do {
         try {
            if (! init) {
               rgx = new Regex(@"\b\w+\b", RegexOptions.None, 
                               TimeSpan.FromMilliseconds(timeoutInterval));
               m = rgx.Match(input, indexPos);
               init = true;
            }
            else { 
               m = m.NextMatch();
            }
            if (m.Success) {    
               if ( !exclusions.Contains(m.Value.ToLower()))
                  wordLengths[m.Value.Length]++;

               indexPos += m.Length + 1;   
            }
         }
         catch (RegexMatchTimeoutException e) {
            if (e.MatchTimeout.TotalMilliseconds < MAX_TIMEOUT) {
               timeoutInterval += INCREMENT;
               init = false;
            }
            else {
               // Rethrow the exception.
               throw; 
            }   
         }          
      } while (m.Success);

      // If regex completed successfully, calculate number of words and average length.
      int nWords = 0; 
      long totalLength = 0;

      for (int ctr = wordLengths.GetLowerBound(0); ctr <= wordLengths.GetUpperBound(0); ctr++) {
         nWords += wordLengths[ctr];
         totalLength += ctr * wordLengths[ctr];
      }
      return new Tuple<int, double>(nWords, totalLength/nWords);
   }
}
```

```vb
Imports System.Collections.Generic
Imports System.IO
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim util As New RegexUtilities()
      Dim title As String = "Doyle - The Hound of the Baskervilles.txt"
      Try
         Dim info = util.GetWordData(title)
         Console.WriteLine("Words:               {0:N0}", info.Item1)
         Console.WriteLine("Average Word Length: {0:N2} characters", info.Item2) 
      Catch e As IOException
         Console.WriteLine("IOException reading file '{0}'", title)
         Console.WriteLine(e.Message)
      Catch e As RegexMatchTimeoutException
         Console.WriteLine("The operation timed out after {0:N0} milliseconds", 
                           e.MatchTimeout.TotalMilliseconds)
      End Try
   End Sub
End Module

Public Class RegexUtilities
   Public Function GetWordData(filename As String) As Tuple(Of Integer, Double) 
      Const MAX_TIMEOUT As Integer = 1000  ' Maximum timeout interval in milliseconds.
      Const INCREMENT As Integer = 350     ' Milliseconds increment of timeout.

      Dim exclusions As New List(Of String)({"a", "an", "the" })
      Dim wordLengths(30) As Integer        ' Allocate an array of more than ample size.
      Dim input As String = Nothing
      Dim sr As StreamReader = Nothing
      Try 
         sr = New StreamReader(filename)
         input = sr.ReadToEnd()
      Catch e As FileNotFoundException
         Dim msg As String = String.Format("Unable to find the file '{0}'", filename)
         Throw New IOException(msg, e)
      Catch e As IOException
         Throw New IOException(e.Message, e)
      Finally
         If sr IsNot Nothing Then sr.Close() 
      End Try

      Dim timeoutInterval As Integer = INCREMENT
      Dim init As Boolean = False
      Dim rgx As Regex = Nothing
      Dim m As Match = Nothing
      Dim indexPos As Integer = 0  
      Do
         Try
            If Not init Then
               rgx = New Regex("\b\w+\b", RegexOptions.None, 
                               TimeSpan.FromMilliseconds(timeoutInterval))
               m = rgx.Match(input, indexPos)
               init = True
            Else 
               m = m.NextMatch()
            End If
            If m.Success Then    
               If Not exclusions.Contains(m.Value.ToLower()) Then
                  wordLengths(m.Value.Length) += 1
               End If
               indexPos += m.Length + 1   
            End If
         Catch e As RegexMatchTimeoutException
            If e.MatchTimeout.TotalMilliseconds < MAX_TIMEOUT Then
               timeoutInterval += INCREMENT
               init = False
            Else
               ' Rethrow the exception.
               Throw 
            End If   
         End Try          
      Loop While m.Success

      ' If regex completed successfully, calculate number of words and average length.
      Dim nWords As Integer
      Dim totalLength As Long

      For ctr As Integer = wordLengths.GetLowerBound(0) To wordLengths.GetUpperBound(0)
         nWords += wordLengths(ctr)
         totalLength += ctr * wordLengths(ctr)
      Next
      Return New Tuple(Of Integer, Double)(nWords, totalLength/nWords)
   End Function
End Class
```

## <a name="capture-only-when-necessary"></a><span data-ttu-id="1c380-297">캡처는 필요한 경우에만</span><span class="sxs-lookup"><span data-stu-id="1c380-297">Capture only when necessary</span></span>

<span data-ttu-id="1c380-298">.NET의 정규식은 정규식 패턴을 하나 이상의 하위 식으로 그룹화할 수 있게 해주는 다양한 그룹화 구문을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-298">Regular expressions in .NET support a number of grouping constructs, which let you group a regular expression pattern into one or more subexpressions.</span></span> <span data-ttu-id="1c380-299">.NET 정규식 언어에서 가장 일반적으로 사용되는 그룹화 구문은 번호가 매겨진 캡처링 그룹을 정의하는 **(**_subexpression_**)**과 명명된 캡처링 그룹을 정의하는 **(?<*_name_**>**_subexpression_**)**입니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-299">The most commonly used grouping constructs in .NET regular expression language are **(**_subexpression_**)**, which defines a numbered capturing group, and **(?<*_name_**>**_subexpression_**)**, which defines a named capturing group.</span></span> <span data-ttu-id="1c380-300">그룹화 구문은 역참조를 만들고 수량자가 적용되는 하위 식을 정의하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-300">Grouping constructs are essential for creating backreferences and for defining a subexpression to which a quantifier is applied.</span></span> 

<span data-ttu-id="1c380-301">하지만 이러한 언어 요소를 사용하려면 비용이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-301">However, the use of these language elements has a cost.</span></span> <span data-ttu-id="1c380-302">이 언어 요소를 사용할 경우 [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) 속성으로 반환된 [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) 개체에 최근의 명명되지 않은 캡처 또는 명명된 캡처가 채워집니다. 또는 단일 그룹화 구문으로 입력 문자열에서 여러 부분 문자열이 캡처된 경우 특정 캡처링 그룹의 [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) 속성으로 반환된 [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) 개체에 여러 [Capture](xref:System.Text.RegularExpressions.Capture) 개체가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-302">They cause the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) object returned by the [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) property to be populated with the most recent unnamed or named captures, and if a single grouping construct has captured multiple substrings in the input string, they also populate the [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) object returned by the [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) property of a particular capturing group with multiple [Capture](xref:System.Text.RegularExpressions.Capture) objects.</span></span>

<span data-ttu-id="1c380-303">그룹화 구문은 종종 수량자를 정규식에 적용할 수 있도록 정규식에서만 사용되며, 이러한 하위 식으로 캡처된 그룹은 이후에 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-303">Often, grouping constructs are used in a regular expression only so that quantifiers can be applied to them, and the groups captured by these subexpressions are not subsequently used.</span></span> <span data-ttu-id="1c380-304">예를 들어 정규식 `\b(\w+[;,]?\s?)+[.?!]`는 전체 문장을 캡처하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-304">For example, the regular expression `\b(\w+[;,]?\s?)+[.?!]` is designed to capture an entire sentence.</span></span> <span data-ttu-id="1c380-305">다음 표에서는 이 정규식 패턴에 포함된 언어 요소와, 이 언어 요소가 [Match](xref:System.Text.RegularExpressions.Match) 개체의 [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) 및 [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) 컬렉션에 미치는 영향에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-305">The following table describes the language elements in this regular expression pattern and their effect on the [Match](xref:System.Text.RegularExpressions.Match) object's [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) and [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) collections.</span></span>

<span data-ttu-id="1c380-306">패턴</span><span class="sxs-lookup"><span data-stu-id="1c380-306">Pattern</span></span> | <span data-ttu-id="1c380-307">설명</span><span class="sxs-lookup"><span data-stu-id="1c380-307">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="1c380-308">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-308">Begin the match at a word boundary.</span></span>
`\w+` | <span data-ttu-id="1c380-309">하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-309">Match one or more word characters.</span></span>
`[;,]?` | <span data-ttu-id="1c380-310">0개 또는 한 개의 쉼표 또는 세미콜론을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-310">Match zero or one comma or semicolon.</span></span>
`\s?` | <span data-ttu-id="1c380-311">0번 이상 나오는 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-311">Match zero or one white-space character.</span></span>
`(\w+[;,]?\s?)+` | <span data-ttu-id="1c380-312">쉼표 또는 세미콜론과 공백 문자가 이어질 수 있는 하나 이상의 단어 문자와 한 번 이상 일치하는 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-312">Match one or more occurrences of one or more word characters followed by an optional comma or semicolon followed by an optional white-space character.</span></span> <span data-ttu-id="1c380-313">이 언어 요소는 정규식 엔진이 문장의 끝에 도달할 때까지 선택적인 구두점 기호로 이어지는 여러 단어 문자의 조합(즉, 단어)이 반복될 수 있도록 하는 데 필수적인 첫 번째 캡처링 그룹을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-313">This defines the first capturing group, which is necessary so that the combination of multiple word characters (that is, a word) followed by an optional punctuation symbol will be repeated until the regular expression engine reaches the end of a sentence.</span></span>
`[.?!]` | <span data-ttu-id="1c380-314">마침표, 물음표 또는 느낌표를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-314">Match a period, question mark, or exclamation point.</span></span>
 
<span data-ttu-id="1c380-315">다음 예제와 같이 일치 항목이 발견되면 [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) 및 [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) 개체에 일치 항목에서 캡처한 항목이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-315">As the following example shows, when a match is found, both the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) and [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) objects are populated with captures from the match.</span></span> <span data-ttu-id="1c380-316">이 경우 캡처링 그룹 `(\w+[;,]?\s?)`가 있으므로 **+** 수량자를 적용하여 정규식 패턴이 문장의 각 단어와 일치하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-316">In this case, the capturing group `(\w+[;,]?\s?)` exists so that the **+** quantifier can be applied to it, which enables the regular expression pattern to match each word in a sentence.</span></span> <span data-ttu-id="1c380-317">그렇지 않으면 문장에서 일치하는 마지막 단어를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-317">Otherwise, it would match the last word in a sentence.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is one sentence. This is another.";
      string pattern = @"\b(\w+[;,]?\s?)+[.?!]";

      foreach (Match match in Regex.Matches(input, pattern)) {
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index);
         int grpCtr = 0;
         foreach (Group grp in match.Groups) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index);
            int capCtr = 0;
            foreach (Capture cap in grp.Captures) {
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index);
               capCtr++;
            }
            grpCtr++;
         }          
         Console.WriteLine();        
      }
   }
}
// The example displays the following output:
//       Match: 'This is one sentence.' at index 0.
//          Group 0: 'This is one sentence.' at index 0.
//             Capture 0: 'This is one sentence.' at 0.
//          Group 1: 'sentence' at index 12.
//             Capture 0: 'This ' at 0.
//             Capture 1: 'is ' at 5.
//             Capture 2: 'one ' at 8.
//             Capture 3: 'sentence' at 12.
//       
//       Match: 'This is another.' at index 22.
//          Group 0: 'This is another.' at index 22.
//             Capture 0: 'This is another.' at 22.
//          Group 1: 'another' at index 30.
//             Capture 0: 'This ' at 22.
//             Capture 1: 'is ' at 27.
//             Capture 2: 'another' at 30.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is one sentence. This is another."
      Dim pattern As String = "\b(\w+[;,]?\s?)+[.?!]"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index)
         Dim grpCtr As Integer = 0
         For Each grp As Group In match.Groups
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index)
            Dim capCtr As Integer = 0
            For Each cap As Capture In grp.Captures
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index)
               capCtr += 1
            Next
            grpCtr += 1
         Next          
         Console.WriteLine()        
      Next    
   End Sub
End Module
' The example displays the following output:
'       Match: 'This is one sentence.' at index 0.
'          Group 0: 'This is one sentence.' at index 0.
'             Capture 0: 'This is one sentence.' at 0.
'          Group 1: 'sentence' at index 12.
'             Capture 0: 'This ' at 0.
'             Capture 1: 'is ' at 5.
'             Capture 2: 'one ' at 8.
'             Capture 3: 'sentence' at 12.
'       
'       Match: 'This is another.' at index 22.
'          Group 0: 'This is another.' at index 22.
'             Capture 0: 'This is another.' at 22.
'          Group 1: 'another' at index 30.
'             Capture 0: 'This ' at 22.
'             Capture 1: 'is ' at 27.
'             Capture 2: 'another' at 30.
```

<span data-ttu-id="1c380-318">수량자를 언어 요소에 적용하기 위해서만 하위 식을 사용하고 캡처한 텍스트에는 관심이 없을 경우 그룹 캡처를 비활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-318">When you use subexpressions only to apply quantifiers to them, and you are not interested in the captured text, you should disable group captures.</span></span> <span data-ttu-id="1c380-319">예를 들어 **(?:**_subexpression_**)** 언어 요소는 적용할 대상 그룹이 일치하는 부분 문자열을 캡처하지 못하도록 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-319">For example, the **(?:**_subexpression_**)** language element prevents the group to which it applies from capturing matched substrings.</span></span> <span data-ttu-id="1c380-320">다음 예제에서 이전 예의 정규식 패턴은 `\b(?:\w+[;,]?\s?)+[.?!]`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-320">In the following example, the regular expression pattern from the previous example is changed to `\b(?:\w+[;,]?\s?)+[.?!]`.</span></span> <span data-ttu-id="1c380-321">출력과 같이 정규식 엔진이 [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) 및 [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) 컬렉션을 채우지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-321">As the output shows, it prevents the regular expression engine from populating the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) and [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) collections.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is one sentence. This is another.";
      string pattern = @"\b(?:\w+[;,]?\s?)+[.?!]";

      foreach (Match match in Regex.Matches(input, pattern)) {
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index);
         int grpCtr = 0;
         foreach (Group grp in match.Groups) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index);
            int capCtr = 0;
            foreach (Capture cap in grp.Captures) {
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index);
               capCtr++;
            }
            grpCtr++;
         }          
         Console.WriteLine();        
      }
   }
}
// The example displays the following output:
//       Match: 'This is one sentence.' at index 0.
//          Group 0: 'This is one sentence.' at index 0.
//             Capture 0: 'This is one sentence.' at 0.
//       
//       Match: 'This is another.' at index 22.
//          Group 0: 'This is another.' at index 22.
//             Capture 0: 'This is another.' at 22.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is one sentence. This is another."
      Dim pattern As String = "\b(?:\w+[;,]?\s?)+[.?!]"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index)
         Dim grpCtr As Integer = 0
         For Each grp As Group In match.Groups
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index)
            Dim capCtr As Integer = 0
            For Each cap As Capture In grp.Captures
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index)
               capCtr += 1
            Next
            grpCtr += 1
         Next          
         Console.WriteLine()        
      Next    
   End Sub
End Module
' The example displays the following output:
'       Match: 'This is one sentence.' at index 0.
'          Group 0: 'This is one sentence.' at index 0.
'             Capture 0: 'This is one sentence.' at 0.
'       
'       Match: 'This is another.' at index 22.
'          Group 0: 'This is another.' at index 22.
'             Capture 0: 'This is another.' at 22.
```

<span data-ttu-id="1c380-322">다음 방법 중 하나로 캡처를 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-322">You can disable captures in one of the following ways:</span></span>

* <span data-ttu-id="1c380-323">**(?:**_subexpression_**)** 언어 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-323">Use the **(?:**_subexpression_**)** language element.</span></span> <span data-ttu-id="1c380-324">이 요소는 적용된 그룹에서 일치하는 부분 문자열을 캡처하지 않도록 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-324">This element prevents the capture of matched substrings in the group to which it applies.</span></span> <span data-ttu-id="1c380-325">중첩된 그룹에서 부분 문자열의 캡처는 비활성화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-325">It does not disable substring captures in any nested groups.</span></span>

* <span data-ttu-id="1c380-326">[RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-326">Use the [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) option.</span></span> <span data-ttu-id="1c380-327">이 옵션은 정규식 패턴에서 모든 명명되지 않은 캡처 또는 암시적인 캡처를 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-327">It disables all unnamed or implicit captures in the regular expression pattern.</span></span> <span data-ttu-id="1c380-328">이 옵션을 사용하면 **(?<**_name_**>**_subexpression_**)** 언어 요소로 정의된 명명된 그룹과 일치하는 부분 문자열만 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-328">When you use this option, only substrings that match named groups defined with the **(?<**_name_**>**_subexpression_**)** language element can be captured.</span></span> <span data-ttu-id="1c380-329">[ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) 플래그는 [Regex](xref:System.Text.RegularExpressions.Regex) 클래스 생성자의 options 매개 변수에 전달하거나 [Regex](xref:System.Text.RegularExpressions.Regex) 정적 일치 메서드의 options 매개 변수에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-329">The [ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) flag can be passed to the options parameter of a [Regex](xref:System.Text.RegularExpressions.Regex) class constructor or to the options parameter of a [Regex](xref:System.Text.RegularExpressions.Regex) static matching method.</span></span>

* <span data-ttu-id="1c380-330">**(?imnsx)** 언어 요소에서 **n** 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-330">Use the **n** option in the **(?imnsx)** language element.</span></span> <span data-ttu-id="1c380-331">이 옵션은 정규식 패턴에서 요소가 나타나는 지점으로부터 모든 명명되지 않은 캡처 또는 암시적인 캡처를 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-331">This option disables all unnamed or implicit captures from the point in the regular expression pattern at which the element appears.</span></span> <span data-ttu-id="1c380-332">패턴의 끝에 도달하거나 **(-n)** 옵션으로 명명되지 않은 캡처 또는 암시적인 캡처를 사용할 수 있을 때까지 캡처가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-332">Captures are disabled either until the end of the pattern or until the **(-n)** option enables unnamed or implicit captures.</span></span> <span data-ttu-id="1c380-333">자세한 내용은 [정규식의 기타 구문](miscellaneous.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c380-333">For more information, see [Miscellaneous constructs in regular expressions](miscellaneous.md).</span></span>

* <span data-ttu-id="1c380-334">**(?imnsx:**_subexpression_**)** 언어 요소에서 **n** 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-334">Use the **n** option in the **(?imnsx:**_subexpression_**)** language element.</span></span> <span data-ttu-id="1c380-335">이 옵션은 *subexpression*에서 명명되지 않은 캡처 또는 암시적인 캡처를 모두 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-335">This option disables all unnamed or implicit captures in *subexpression*.</span></span> <span data-ttu-id="1c380-336">명명되지 않은 또는 암시적인 중첩된 캡처링 그룹에 의한 캡처도 함께 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-336">Captures by any unnamed or implicit nested capturing groups are disabled as well.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1c380-337">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1c380-337">Related topics</span></span>

<span data-ttu-id="1c380-338">제목</span><span class="sxs-lookup"><span data-stu-id="1c380-338">Title</span></span> | <span data-ttu-id="1c380-339">설명</span><span class="sxs-lookup"><span data-stu-id="1c380-339">Description</span></span>
----- | ----------- 
[<span data-ttu-id="1c380-340">정규식 동작 정보</span><span class="sxs-lookup"><span data-stu-id="1c380-340">Details of regular expression behavior</span></span>](regex-behavior.md) | <span data-ttu-id="1c380-341">.NET의 정규식 엔진 구현에 대해 자세히 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-341">Examines the implementation of the regular expression engine in .NET.</span></span> <span data-ttu-id="1c380-342">이 항목에서는 정규식의 유연성에 중점을 두고 정규식 엔진의 효율성과 성능에 대한 개발자의 책임에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-342">The topic focuses on the flexibility of regular expressions and explains the developer's responsibility for ensuring the efficient and robust operation of the regular expression engine.</span></span>
[<span data-ttu-id="1c380-343">정규식의 역추적</span><span class="sxs-lookup"><span data-stu-id="1c380-343">Backtracking in regular expressions</span></span>](backtracking.md) | <span data-ttu-id="1c380-344">역추적의 정의 및 역추적이 정규식 성능에 미치는 영향에 대해 설명하고 역추적 대신 사용할 수 있는 언어 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-344">Explains what backtracking is and how it affects regular expression performance, and examines language elements that provide alternatives to backtracking.</span></span>
[<span data-ttu-id="1c380-345">정규식 언어 - 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="1c380-345">Regular expression language - quick reference</span></span>](quick-ref.md) | <span data-ttu-id="1c380-346">.NET의 정규식 언어 요소에 대해 설명하고 각 언어 요소에 대한 자세한 설명서 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c380-346">Describes the elements of the regular expression language in .NET and provides links to detailed documentation for each language element.</span></span>
 


