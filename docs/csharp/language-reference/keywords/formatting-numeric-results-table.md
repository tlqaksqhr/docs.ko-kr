---
title: "숫자 결과 형식 지정 표(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 16976f5a59bd4eb0eca29553aff87d4fe0b1d247
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="56c87-102">숫자 결과 형식 지정 표(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="56c87-102">Formatting Numeric Results Table (C# Reference)</span></span>
<span data-ttu-id="56c87-103"><xref:System.String.Format%2A?displayProperty=fullName> 메서드를 사용하거나 `String.Format`을 호출하는 <xref:System.Console.Write%2A?displayProperty=fullName> 또는 <xref:System.Console.WriteLine%2A?displayProperty=fullName> 메서드를 통해 숫자 결과의 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56c87-103">You can format numeric results by using the <xref:System.String.Format%2A?displayProperty=fullName> method, or through the <xref:System.Console.Write%2A?displayProperty=fullName> or <xref:System.Console.WriteLine%2A?displayProperty=fullName> method, which calls `String.Format`.</span></span> <span data-ttu-id="56c87-104">형식은 형식 문자열을 사용하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="56c87-104">The format is specified by using format strings.</span></span> <span data-ttu-id="56c87-105">다음 표에는 지원되는 표준 형식 문자열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56c87-105">The following table contains the supported standard format strings.</span></span> <span data-ttu-id="56c87-106">형식 문자열은 `Axx` 형식을 사용합니다. 여기서 `A`는 형식 지정자이고 `xx`는 전체 자릿수 지정자입니다.</span><span class="sxs-lookup"><span data-stu-id="56c87-106">The format string takes the following form: `Axx`, where `A` is the format specifier and `xx` is the precision specifier.</span></span> <span data-ttu-id="56c87-107">형식 지정자는 숫자 값에 적용되는 서식 형식을 제어하고, 전체 자릿수 지정자는 서식이 지정된 출력의 유효 자릿수 또는 소수 자릿수를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="56c87-107">The format specifier controls the type of formatting applied to the numeric value, and the precision specifier controls the number of significant digits or decimal places of the formatted output.</span></span> <span data-ttu-id="56c87-108">전체 자릿수 지정자의 값은 0에서 99 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="56c87-108">The value of the precision specifier ranges from 0 to 99.</span></span>  
  
 <span data-ttu-id="56c87-109">표준 및 사용자 지정 서식 문자열에 대한 자세한 내용은 [형식 서식 지정](../../../standard/base-types/formatting-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56c87-109">For more information about standard and custom formatting strings, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="56c87-110">`String.Format` 메서드에 대한 자세한 내용은 <xref:System.String.Format%2A?displayProperty=fullName>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="56c87-110">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=fullName>.</span></span>  
  
|<span data-ttu-id="56c87-111">형식 지정자</span><span class="sxs-lookup"><span data-stu-id="56c87-111">Format Specifier</span></span>|<span data-ttu-id="56c87-112">설명</span><span class="sxs-lookup"><span data-stu-id="56c87-112">Description</span></span>|<span data-ttu-id="56c87-113">예제</span><span class="sxs-lookup"><span data-stu-id="56c87-113">Examples</span></span>|<span data-ttu-id="56c87-114">출력</span><span class="sxs-lookup"><span data-stu-id="56c87-114">Output</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="56c87-115">C 또는 c</span><span class="sxs-lookup"><span data-stu-id="56c87-115">C or c</span></span>|<span data-ttu-id="56c87-116">통화</span><span class="sxs-lookup"><span data-stu-id="56c87-116">Currency</span></span>|<span data-ttu-id="56c87-117">Console.Write("{0:C}", 2.5);</span><span class="sxs-lookup"><span data-stu-id="56c87-117">Console.Write("{0:C}", 2.5);</span></span><br /><br /> <span data-ttu-id="56c87-118">Console.Write("{0:C}", -2.5);</span><span class="sxs-lookup"><span data-stu-id="56c87-118">Console.Write("{0:C}", -2.5);</span></span>|<span data-ttu-id="56c87-119">$2.50</span><span class="sxs-lookup"><span data-stu-id="56c87-119">$2.50</span></span><br /><br /> <span data-ttu-id="56c87-120">($2.50)</span><span class="sxs-lookup"><span data-stu-id="56c87-120">($2.50)</span></span>|  
|<span data-ttu-id="56c87-121">D 또는 d</span><span class="sxs-lookup"><span data-stu-id="56c87-121">D or d</span></span>|<span data-ttu-id="56c87-122">Decimal</span><span class="sxs-lookup"><span data-stu-id="56c87-122">Decimal</span></span>|<span data-ttu-id="56c87-123">Console.Write("{0:D5}", 25);</span><span class="sxs-lookup"><span data-stu-id="56c87-123">Console.Write("{0:D5}", 25);</span></span>|<span data-ttu-id="56c87-124">00025</span><span class="sxs-lookup"><span data-stu-id="56c87-124">00025</span></span>|  
|<span data-ttu-id="56c87-125">E 또는 e</span><span class="sxs-lookup"><span data-stu-id="56c87-125">E or e</span></span>|<span data-ttu-id="56c87-126">지수</span><span class="sxs-lookup"><span data-stu-id="56c87-126">Scientific</span></span>|<span data-ttu-id="56c87-127">Console.Write("{0:E}", 250000);</span><span class="sxs-lookup"><span data-stu-id="56c87-127">Console.Write("{0:E}", 250000);</span></span>|<span data-ttu-id="56c87-128">2.500000E+005</span><span class="sxs-lookup"><span data-stu-id="56c87-128">2.500000E+005</span></span>|  
|<span data-ttu-id="56c87-129">F 또는 f</span><span class="sxs-lookup"><span data-stu-id="56c87-129">F or f</span></span>|<span data-ttu-id="56c87-130">고정 소수점</span><span class="sxs-lookup"><span data-stu-id="56c87-130">Fixed-point</span></span>|<span data-ttu-id="56c87-131">Console.Write("{0:F2}", 25);</span><span class="sxs-lookup"><span data-stu-id="56c87-131">Console.Write("{0:F2}", 25);</span></span><br /><br /> <span data-ttu-id="56c87-132">Console.Write("{0:F0}", 25);</span><span class="sxs-lookup"><span data-stu-id="56c87-132">Console.Write("{0:F0}", 25);</span></span>|<span data-ttu-id="56c87-133">25.00</span><span class="sxs-lookup"><span data-stu-id="56c87-133">25.00</span></span><br /><br /> <span data-ttu-id="56c87-134">25</span><span class="sxs-lookup"><span data-stu-id="56c87-134">25</span></span>|  
|<span data-ttu-id="56c87-135">G 또는 g</span><span class="sxs-lookup"><span data-stu-id="56c87-135">G or g</span></span>|<span data-ttu-id="56c87-136">일반</span><span class="sxs-lookup"><span data-stu-id="56c87-136">General</span></span>|<span data-ttu-id="56c87-137">Console.Write("{0:G}", 2.5);</span><span class="sxs-lookup"><span data-stu-id="56c87-137">Console.Write("{0:G}", 2.5);</span></span>|<span data-ttu-id="56c87-138">2.5</span><span class="sxs-lookup"><span data-stu-id="56c87-138">2.5</span></span>|  
|<span data-ttu-id="56c87-139">N 또는 n</span><span class="sxs-lookup"><span data-stu-id="56c87-139">N or n</span></span>|<span data-ttu-id="56c87-140">수</span><span class="sxs-lookup"><span data-stu-id="56c87-140">Number</span></span>|<span data-ttu-id="56c87-141">Console.Write("{0:N}", 2500000);</span><span class="sxs-lookup"><span data-stu-id="56c87-141">Console.Write("{0:N}", 2500000);</span></span>|<span data-ttu-id="56c87-142">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="56c87-142">2,500,000.00</span></span>|  
|<span data-ttu-id="56c87-143">X 또는 x</span><span class="sxs-lookup"><span data-stu-id="56c87-143">X or x</span></span>|<span data-ttu-id="56c87-144">16진수</span><span class="sxs-lookup"><span data-stu-id="56c87-144">Hexadecimal</span></span>|<span data-ttu-id="56c87-145">Console.Write("{0:X}", 250);</span><span class="sxs-lookup"><span data-stu-id="56c87-145">Console.Write("{0:X}", 250);</span></span><br /><br /> <span data-ttu-id="56c87-146">Console.Write("{0:X}", 0xffff);</span><span class="sxs-lookup"><span data-stu-id="56c87-146">Console.Write("{0:X}", 0xffff);</span></span>|<span data-ttu-id="56c87-147">FA</span><span class="sxs-lookup"><span data-stu-id="56c87-147">FA</span></span><br /><br /> <span data-ttu-id="56c87-148">FFFF</span><span class="sxs-lookup"><span data-stu-id="56c87-148">FFFF</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56c87-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56c87-149">See Also</span></span>  
 <span data-ttu-id="56c87-150">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="56c87-150">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="56c87-151">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="56c87-151">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="56c87-152">[표준 숫자 형식 문자열](../../../standard/base-types/standard-numeric-format-strings.md) </span><span class="sxs-lookup"><span data-stu-id="56c87-152">[Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md) </span></span>  
 <span data-ttu-id="56c87-153">[형식 참조 테이블](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span><span class="sxs-lookup"><span data-stu-id="56c87-153">[Reference Tables for Types](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span></span>  
 [<span data-ttu-id="56c87-154">string</span><span class="sxs-lookup"><span data-stu-id="56c87-154">string</span></span>](../../../csharp/language-reference/keywords/string.md)

