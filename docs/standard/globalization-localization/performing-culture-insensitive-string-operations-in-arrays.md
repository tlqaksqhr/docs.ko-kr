---
title: "배열에서 문화권을 구분하지 않는 문자열 작업 수행"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET Framework], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1b4e040ed379cdbf43fbe8b2c4379fdd4dc781f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a><span data-ttu-id="5d625-102">배열에서 문화권을 구분하지 않는 문자열 작업 수행</span><span class="sxs-lookup"><span data-stu-id="5d625-102">Performing Culture-Insensitive String Operations in Arrays</span></span>
<span data-ttu-id="5d625-103">오버 로드는 <xref:System.Array.Sort%2A?displayProperty=nameWithType> 및 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> 메서드 기본을 사용 하 여 문화권 구분 정렬을 수행는 <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5d625-103">Overloads of the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods perform culture-sensitive sorts by default using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="5d625-104">이러한 메서드에서 반환 하는 문화권 구분 결과의 정렬 순서 차이 때문에 문화권 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d625-104">Culture-sensitive results returned by these methods can vary by culture due to differences in sort orders.</span></span> <span data-ttu-id="5d625-105">문화권 구분 하는 동작을 제거 하려면는이 메서드의 오버 로드 중 하나를 사용는 `comparer` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d625-105">To eliminate culture-sensitive behavior, use one of the overloads of this method that accepts a `comparer` parameter.</span></span> <span data-ttu-id="5d625-106">`comparer` 매개 변수를 지정 된 <xref:System.Collections.IComparer> 배열의 요소를 비교할 때 사용할 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="5d625-106">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing elements in the array.</span></span> <span data-ttu-id="5d625-107">매개 변수를 사용 하는 사용자 정의 고정 비교자 클래스를 지정 합니다. <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="5d625-107">For the parameter, specify a custom invariant comparer class that uses <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5d625-108">"SortedList 클래스를 사용 하 여" 하위 항목에는 고정 사용자 지정 비교자 클래스의 예제를 보려면는 [컬렉션의 문화권을 구분 하지 않는 문자열 작업 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="5d625-108">An example of a custom invariant comparer class is provided in the "Using the SortedList Class" subtopic of the [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) topic.</span></span>  
  
 <span data-ttu-id="5d625-109">**참고** 전달 **CultureInfo.InvariantCulture** 메서드 비교에 문화권을 구분 하지 않는 비교를 수행지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d625-109">**Note** Passing **CultureInfo.InvariantCulture** to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="5d625-110">그러나 파일 경로, 레지스트리 키 및 환경 변수 등과 같은 비언어적 비교는 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d625-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="5d625-111">비교 결과에 따라 보안 결정을 지원하지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d625-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="5d625-112">비 언어적 비교 또는 결과 기반 보안 결정에 대 한 지원에 대 한 응용 프로그램을 허용 하는 비교 메서드를 사용 해야는 <xref:System.StringComparison> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5d625-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="5d625-113">응용 프로그램을 다음으로 전달할지 <xref:System.StringComparison.Ordinal>합니다.</span><span class="sxs-lookup"><span data-stu-id="5d625-113">The application should then pass <xref:System.StringComparison.Ordinal>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d625-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d625-114">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [<span data-ttu-id="5d625-115">Culture의 영향을 받지 않는 문자열 작업 수행</span><span class="sxs-lookup"><span data-stu-id="5d625-115">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
