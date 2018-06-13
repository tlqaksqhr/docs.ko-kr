---
title: 배열에서 문화권을 구분하지 않는 문자열 작업 수행
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET Framework], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4d732d64eecff72403c455c14b68c3aec1b5407
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572062"
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a><span data-ttu-id="84d10-102">배열에서 문화권을 구분하지 않는 문자열 작업 수행</span><span class="sxs-lookup"><span data-stu-id="84d10-102">Performing Culture-Insensitive String Operations in Arrays</span></span>
<span data-ttu-id="84d10-103"><xref:System.Array.Sort%2A?displayProperty=nameWithType> 및 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> 메서드의 오버로드는 기본적으로 <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> 속성을 사용하여 문화권 구분 정렬을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="84d10-103">Overloads of the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods perform culture-sensitive sorts by default using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="84d10-104">이러한 메서드에서 반환한 문화권 구분 결과는 정렬 순서의 차이로 인해 문화권에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d10-104">Culture-sensitive results returned by these methods can vary by culture due to differences in sort orders.</span></span> <span data-ttu-id="84d10-105">문화권 구분 동작을 제거하려면 `comparer` 매개 변수를 수락하는 이 메서드의 오버로드 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84d10-105">To eliminate culture-sensitive behavior, use one of the overloads of this method that accepts a `comparer` parameter.</span></span> <span data-ttu-id="84d10-106">`comparer` 매개 변수는 배열의 요소를 비교할 때 사용할 <xref:System.Collections.IComparer> 구현을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84d10-106">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing elements in the array.</span></span> <span data-ttu-id="84d10-107">매개 변수의 경우 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>를 사용하는 사용자 지정 고정 비교자 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84d10-107">For the parameter, specify a custom invariant comparer class that uses <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="84d10-108">사용자 지정 고정 비교자 클래스의 예제는 [컬렉션에서 문화권을 구분하지 않는 문자열 작업 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) 항목의 “SortedList 클래스 사용” 하위 항목에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84d10-108">An example of a custom invariant comparer class is provided in the "Using the SortedList Class" subtopic of the [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) topic.</span></span>  
  
 <span data-ttu-id="84d10-109">**참고** 비교 메서드에 **CultureInfo.InvariantCulture**를 전달하면 문화권을 구분하지 않는 비교가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="84d10-109">**Note** Passing **CultureInfo.InvariantCulture** to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="84d10-110">그러나 파일 경로, 레지스트리 키 및 환경 변수 등과 같은 비언어적 비교는 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84d10-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="84d10-111">비교 결과에 따라 보안 결정을 지원하지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84d10-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="84d10-112">비언어적 비교 또는 결과 기반 보안 의사 결정에 대한 지원의 경우는 응용 프로그램이 <xref:System.StringComparison> 값을 수락하는 비교 메서드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d10-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="84d10-113">그런 다음, 응용 프로그램이 <xref:System.StringComparison.Ordinal>을 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d10-113">The application should then pass <xref:System.StringComparison.Ordinal>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d10-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84d10-114">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [<span data-ttu-id="84d10-115">Culture의 영향을 받지 않는 문자열 작업 수행</span><span class="sxs-lookup"><span data-stu-id="84d10-115">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
