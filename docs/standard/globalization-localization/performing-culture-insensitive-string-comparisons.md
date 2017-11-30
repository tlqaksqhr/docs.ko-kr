---
title: "문화권을 구분하지 않는 문자열 비교 수행"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- String.CompareTo method
- String.Compare method
- string comparison [.NET Framework], culture-insensitive
- strings [.NET Framework], comparing
- culture-insensitive string operations, comparisons
- culture parameter
ms.assetid: abae50ef-32f7-4a50-a540-fd256fd1aed0
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 980b4ac515deaaedb1ab7e240e8f110a5fd0d51c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-string-comparisons"></a><span data-ttu-id="749c4-102">문화권을 구분하지 않는 문자열 비교 수행</span><span class="sxs-lookup"><span data-stu-id="749c4-102">Performing Culture-Insensitive String Comparisons</span></span>
<span data-ttu-id="749c4-103">기본적으로 <xref:System.String.Compare%2A?displayProperty=nameWithType> 메서드는 문화권 구분 및 대/소문자 구분 비교 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-103">By default, the <xref:System.String.Compare%2A?displayProperty=nameWithType> method performs culture-sensitive and case-sensitive comparisons.</span></span> <span data-ttu-id="749c4-104">이 메서드에는 사용할 문화권을 지정할 수 있는 `culture` 매개 변수와 사용할 비교 규칙을 지정할 수 있는 `comparisonType` 매개 변수를 제공하는 몇 가지 오버로드도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-104">This method also includes several overloads that provide a `culture` parameter that lets you specify the culture to use, and a `comparisonType` parameter that lets you specify the comparison rules to use.</span></span> <span data-ttu-id="749c4-105">기본 오버로드 대신 이러한 메서드를 호출하면 특정 메서드 호출에서 사용되는 규칙에 대한 모든 모호성이 제거되고 특정 비교가 문화권을 구분하는지 여부가 명확히 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-105">Calling these methods instead of the default overload removes any ambiguity about the rules used in a particular method call, and makes it clear whether a particular comparison is culture-sensitive or culture-insensitive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="749c4-106"><xref:System.String.CompareTo%2A?displayProperty=nameWithType> 메서드의 두 오버로드는 문화권 구분 비교와 대/소문자 구분 비교를 수행합니다. 이 메서드를 사용하여 문화권을 구분하지 않는 비교를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-106">Both overloads of the <xref:System.String.CompareTo%2A?displayProperty=nameWithType> method perform culture-sensitive and case-sensitive comparisons; you cannot use this method to perform culture-insensitive comparisons.</span></span> <span data-ttu-id="749c4-107">코드의 명확성을 위해 <xref:System.String.Compare%2A?displayProperty=nameWithType> 메서드를 대신 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-107">For code clarity, we recommend that you use the <xref:System.String.Compare%2A?displayProperty=nameWithType> method instead.</span></span>  
  
 <span data-ttu-id="749c4-108">문화권 구분 작업의 경우 <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType> 또는 <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType> 열거형 값을 `comparisonType` 매개 변수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-108">For culture-sensitive operations, specify the <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType> or <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType> enumeration value as the `comparisonType` parameter.</span></span> <span data-ttu-id="749c4-109">현재 문화권이 아닌 지정된 된 문화권을 사용 하 여 문화권 구분 비교를 지정 하려는 경우는 <xref:System.Globalization.CultureInfo> 해당 문화권을 나타내는 개체의 `culture` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-109">If you want to perform a culture-sensitive comparison using a designated culture other than the current culture, specify the <xref:System.Globalization.CultureInfo> object that represents that culture as the `culture` parameter.</span></span>  
  
 <span data-ttu-id="749c4-110"><xref:System.String.Compare%2A?displayProperty=nameWithType> 메서드에서 지원하는 문화권을 구분하지 않는 문자열 비교는 언어적(고정 문화권의 정렬 규칙 기반)이거나 비언어적(문자열에 있는 문자의 서수 값 기반)입니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-110">The culture-insensitive string comparisons supported by the <xref:System.String.Compare%2A?displayProperty=nameWithType> method are either linguistic (based on the sorting conventions of the invariant culture) or non-linguistic (based on the ordinal value of the characters in the string).</span></span> <span data-ttu-id="749c4-111">대부분의 문화권을 구분하지 않는 문자열 비교는 비언어적입니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-111">Most culture-insensitive string comparisons are non-linguistic.</span></span> <span data-ttu-id="749c4-112">이러한 비교의 경우 <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> 또는 <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> 열거형 값을 `comparisonType` 매개 변수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-112">For these comparisons, specify the <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> or <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> enumeration value as the `comparisonType` parameter.</span></span> <span data-ttu-id="749c4-113">예를 들어 사용자 이름 또는 암호 비교와 같은 보안 결정이 문자열 비교의 결과를 기반으로 하는 경우 결과가 특정 문화권 또는 언어 규칙의 영향을 받지 않도록 작업이 문화권을 구분하지 않고 비언어적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-113">For example, if a security decision (such as a user name or password comparison) is based on the result of a string comparison, the operation should be culture-insensitive and non-linguistic to ensure that the result is not affected by the conventions of a particular culture or language.</span></span>  
  
 <span data-ttu-id="749c4-114">여러 문화권의 언어적으로 관련된 문자열을 일관성 있게 처리하려면 문화권을 구분하지 않는 언어적 문자열 비교를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-114">Use culture-insensitive linguistic string comparison if you want to handle linguistically relevant strings from multiple cultures in a consistent way.</span></span> <span data-ttu-id="749c4-115">예를 들어 응용 프로그램에서 목록 상자에 여러 문자 집합을 사용하는 단어를 표시하는 경우 현재 문화권에 관계없이 동일한 순서로 단어를 표시하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-115">For example, if your application displays words that use multiple character sets in a list box, you might want to display words in the same order regardless of the current culture.</span></span> <span data-ttu-id="749c4-116">문화권을 구분하지 않는 언어적 비교의 경우 .NET Framework에서는 영어의 언어적 규칙을 기반으로 하는 고정 문화권을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-116">For culture-insensitive linguistic comparisons, the .NET Framework defines an invariant culture that is based on the linguistic conventions of English.</span></span> <span data-ttu-id="749c4-117">문화권을 구분하지 않는 언어적 비교를 수행하려면 <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> 또는 <xref:System.StringComparison.InvariantCultureIgnoreCase?displayProperty=nameWithType>를 `comparisonType` 매개 변수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-117">To perform a culture-insensitive linguistic comparison, specify <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> or <xref:System.StringComparison.InvariantCultureIgnoreCase?displayProperty=nameWithType> as the `comparisonType` parameter.</span></span>  
  
 <span data-ttu-id="749c4-118">다음 예제에서는 문화권을 구분하지 않는 비언어적 문자열 비교를 두 가지 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-118">The following example performs two culture-insensitive, non-linguistic string comparisons.</span></span> <span data-ttu-id="749c4-119">첫 번째 비교는 대/소문자를 구분하지만 두 번째 비교는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-119">The first is case-sensitive, but the second is not.</span></span>  
  
 [!code-csharp[Conceptual.Strings.CultureInsensitiveComparison#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.cultureinsensitivecomparison/cs/cultureinsensitive1.cs#1)]
 [!code-vb[Conceptual.Strings.CultureInsensitiveComparison#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.cultureinsensitivecomparison/vb/cultureinsensitive1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="749c4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="749c4-120">See Also</span></span>  
 <xref:System.String.Compare%2A?displayProperty=nameWithType>  
 <xref:System.String.CompareTo%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="749c4-121">Culture의 영향을 받지 않는 문자열 작업 수행</span><span class="sxs-lookup"><span data-stu-id="749c4-121">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)  
 [<span data-ttu-id="749c4-122">문자열 사용에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="749c4-122">Best Practices for Using Strings</span></span>](../../../docs/standard/base-types/best-practices-strings.md)
