---
title: "컬렉션 내에서 비교 및 정렬"
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
- sorting data, collections
- IComparable.CompareTo method
- Collections classes
- Equals method
- collections [.NET Framework], comparisons
ms.assetid: 5e4d3b45-97f0-423c-a65f-c492ed40e73b
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bb7092a2eae8d950f3709ea4fde63f6c7d5b32b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="comparisons-and-sorts-within-collections"></a><span data-ttu-id="d17a4-102">컬렉션 내에서 비교 및 정렬</span><span class="sxs-lookup"><span data-stu-id="d17a4-102">Comparisons and Sorts Within Collections</span></span>
<span data-ttu-id="d17a4-103"><xref:System.Collections> 클래스는 제거할 요소 검색, 키-값 쌍의 값 반환 등 컬렉션 관리와 관련된 거의 모든 프로세스에서 비교를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-103">The <xref:System.Collections> classes perform comparisons in almost all the processes involved in managing collections, whether searching for the element to remove or returning the value of a key-and-value pair.</span></span>  
  
 <span data-ttu-id="d17a4-104">컬렉션은 일반적으로 같음 비교자 및/또는 순서 비교자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-104">Collections typically utilize an equality comparer and/or an ordering comparer.</span></span> <span data-ttu-id="d17a4-105">비교에는 두 가지 구문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-105">Two constructs are used for comparisons.</span></span>  
  
<a name="BKMK_Checkingforequality"></a>   
## <a name="checking-for-equality"></a><span data-ttu-id="d17a4-106">같음 확인</span><span class="sxs-lookup"><span data-stu-id="d17a4-106">Checking for equality</span></span>  
 <span data-ttu-id="d17a4-107">`Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>, `Remove` 등의 메서드는 컬렉션 요소에 대해 같음 비교자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-107">Methods such as `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>, and `Remove` use an equality comparer for the collection elements.</span></span> <span data-ttu-id="d17a4-108">제네릭 컬렉션의 경우 다음 지침에 따라 항목이 같은지를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-108">If the collection is generic, than items are compared for equality according to the following guidelines:</span></span>  
  
-   <span data-ttu-id="d17a4-109">T 형식이 <xref:System.IEquatable%601> 제네릭 인터페이스를 구현하는 경우 같음 비교자는 해당 인터페이스의 <xref:System.IEquatable%601.Equals%2A> 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-109">If type T implements the <xref:System.IEquatable%601> generic interface, then the equality comparer is the <xref:System.IEquatable%601.Equals%2A> method of that interface.</span></span>  
  
-   <span data-ttu-id="d17a4-110">T 형식이 <xref:System.IEquatable%601>을 구현하지 않는 경우에는 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-110">If type T does not implement <xref:System.IEquatable%601>, <xref:System.Object.Equals%2A?displayProperty=nameWithType> is used.</span></span>  
  
 <span data-ttu-id="d17a4-111">또한 사전 컬렉션의 일부 생성자 오버로드는 키가 같은지를 비교하는 데 사용되는 <xref:System.Collections.Generic.IEqualityComparer%601> 구현을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-111">In addition, Some constructor overloads for dictionary collections accept an <xref:System.Collections.Generic.IEqualityComparer%601> implementation, which is used to compare keys for equality.</span></span> <span data-ttu-id="d17a4-112">예제를 보려면 <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A?displayProperty=nameWithType> 생성자를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d17a4-112">For an example, see the <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A?displayProperty=nameWithType> constructor.</span></span>  
  
<a name="BKMK_Determiningsortorder"></a>   
## <a name="determining-sort-order"></a><span data-ttu-id="d17a4-113">정렬 순서 결정</span><span class="sxs-lookup"><span data-stu-id="d17a4-113">Determining sort order</span></span>  
 <span data-ttu-id="d17a4-114">`BinarySearch` 및 `Sort` 와 같은 메서드는 컬렉션 요소에 대해 순서 비교자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-114">Methods such as `BinarySearch` and `Sort` use an ordering comparer for the collection elements.</span></span> <span data-ttu-id="d17a4-115">컬렉션의 요소를 비교할 수도 있고 특정 요소와 지정된 값을 비교할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-115">The comparisons can be between elements of the collection, or between an element and a specified value.</span></span> <span data-ttu-id="d17a4-116">개체를 비교하는 경우에는 `default comparer` 및 `explicit comparer`의 개념이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-116">For comparing objects, there is the concept of a `default comparer` and an `explicit comparer`.</span></span>  
  
 <span data-ttu-id="d17a4-117">기본 비교자는 비교 대상 개체 중 하나 이상을 사용하여 **IComparable** 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-117">The default comparer relies on at least one of the objects being compared to implement the **IComparable** interface.</span></span> <span data-ttu-id="d17a4-118">사용되는 모든 클래스에 대해 **IComparable** 을 목록 컬렉션의 값 또는 사전 컬렉션의 키로 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-118">It is a good practice to implement **IComparable** on all classes are used as values in a list collection or as keys in a dictionary collection.</span></span> <span data-ttu-id="d17a4-119">제네릭 컬렉션의 경우 다음 기준에 따라 같음 비교를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-119">For a generic collection, equality comparison is determined according to the following:</span></span>  
  
-   <span data-ttu-id="d17a4-120">T 형식이 <xref:System.IComparable%601?displayProperty=nameWithType> 제네릭 인터페이스를 구현하는 경우 기본 비교자는 해당 인터페이스의 <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-120">If type T implements the <xref:System.IComparable%601?displayProperty=nameWithType> generic interface, then the default comparer is the <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> method of that interface</span></span>  
  
-   <span data-ttu-id="d17a4-121">T 형식이 제네릭이 아닌 <xref:System.IComparable?displayProperty=nameWithType> 인터페이스를 구현하는 경우 기본 비교자는 해당 인터페이스의 <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-121">If type T implements the non-generic <xref:System.IComparable?displayProperty=nameWithType> interface, then the default comparer is the <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> method of that interface.</span></span>  
  
-   <span data-ttu-id="d17a4-122">T 형식이 두 인터페이스를 모두 구현하지 않는 경우에는 기본 비교자가 없으며 비교자 또는 비교 대리자를 명시적으로 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-122">If type T doesn’t implement either interface, then there is no default comparer, and a comparer or comparison delegate must be provided explicitly.</span></span>  
  
 <span data-ttu-id="d17a4-123">명시적 비교를 제공할 수 있도록 일부 메서드는 매개 변수로 **IComparer** 구현을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-123">To provide explicit comparisons, some methods accept an **IComparer** implementation as a parameter.</span></span> <span data-ttu-id="d17a4-124">예를 들어 <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> 메서드는 <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> 구현을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-124">For example, the <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> method accepts an <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> implementation.</span></span>  
  
 <span data-ttu-id="d17a4-125">시스템의 현재 문화권 설정은 컬렉션 내의 비교와 정렬에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-125">The current culture setting of the system can affect the comparisons and sorts within a collection.</span></span> <span data-ttu-id="d17a4-126">기본적으로 **Collections** 클래스의 비교 및 정렬은 문화권을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-126">By default, the comparisons and sorts in the **Collections** classes are culture-sensitive.</span></span> <span data-ttu-id="d17a4-127">문화권 설정을 무시하고 동일한 비교 및 정렬 결과가 반환되도록 하려면 <xref:System.Globalization.CultureInfo.InvariantCulture%2A> 를 허용하는 멤버 오버로드를 포함하여 <xref:System.Globalization.CultureInfo>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-127">To ignore the culture setting and therefore obtain consistent comparison and sorting results, use the <xref:System.Globalization.CultureInfo.InvariantCulture%2A> with member overloads that accept a <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="d17a4-128">자세한 내용은 [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) 및 [Performing Culture-Insensitive String Operations in Arrays](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d17a4-128">For more information, see [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) and [Performing Culture-Insensitive String Operations in Arrays](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).</span></span>  
  
<a name="BKMK_Equalityandsortexample"></a>   
## <a name="equality-and-sort-example"></a><span data-ttu-id="d17a4-129">같음 및 정렬 예제</span><span class="sxs-lookup"><span data-stu-id="d17a4-129">Equality and sort example</span></span>  
 <span data-ttu-id="d17a4-130">다음 코드에서는 간단한 비즈니스 개체에 대한 <xref:System.IEquatable%601> 및 <xref:System.IComparable%601> 의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-130">The following code demonstrates an implementation of <xref:System.IEquatable%601> and <xref:System.IComparable%601> on a simple business object.</span></span> <span data-ttu-id="d17a4-131">또한 개체를 목록에 저장하고 정렬할 때 <xref:System.Collections.Generic.List%601.Sort> 메서드를 호출하면 `Part` 형식에 대해 기본 비교자가 사용되며, 무명 메서드를 사용하여 <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> 메서드가 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="d17a4-131">In addition, when the object is stored in a list and sorted, you will see that calling the <xref:System.Collections.Generic.List%601.Sort> method results in the use of the default comparer for the `Part` type, and the <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> method implemented by using an anonymous method.</span></span>  
  
 [!code-csharp[System.Collections.Generic.List.Sort#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.collections.generic.list.sort/cs/program.cs#1)]
 [!code-vb[System.Collections.Generic.List.Sort#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.collections.generic.list.sort/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d17a4-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d17a4-132">See Also</span></span>  
 <xref:System.Collections.IComparer>  
 <xref:System.IEquatable%601>  
 <xref:System.Collections.Generic.IComparer%601>  
 <xref:System.IComparable>  
 <xref:System.IComparable%601>
