---
title: .NET의 제네릭 컬렉션
ms.date: 02/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET], collections
- generic collections [.NET]
- generic types [.NET]
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 829ef35d2e26f67ea956a0838d93b9667ad58df4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="generic-collections-in-net"></a><span data-ttu-id="a9053-102">.NET의 제네릭 컬렉션</span><span class="sxs-lookup"><span data-stu-id="a9053-102">Generic Collections in .NET</span></span>

 <span data-ttu-id="a9053-103">.NET 클래스 라이브러리는 <xref:System.Collections.Generic> 및 <xref:System.Collections.ObjectModel> 네임스페이스에서 다양한 제네릭 컬렉션 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-103">The .NET class library provides a number of generic collection classes in the <xref:System.Collections.Generic> and <xref:System.Collections.ObjectModel> namespaces.</span></span> <span data-ttu-id="a9053-104">이러한 클래스에 대한 자세한 내용은 [일반적으로 사용되는 컬렉션 형식](../../../docs/standard/collections/commonly-used-collection-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9053-104">For more detailed information about these classes, see [Commonly Used Collection Types](../../../docs/standard/collections/commonly-used-collection-types.md).</span></span>  
  
### <a name="systemcollectionsgeneric"></a><span data-ttu-id="a9053-105">System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="a9053-105">System.Collections.Generic</span></span>  
 <span data-ttu-id="a9053-106">대부분의 제네릭 컬렉션 형식은 제네릭이 아닌 형식과 직접적인 연관이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-106">Many of the generic collection types are direct analogs of nongeneric types.</span></span> <span data-ttu-id="a9053-107"><xref:System.Collections.Generic.Dictionary%602>는 <xref:System.Collections.Hashtable>의 제네릭 버전으로, <xref:System.Collections.DictionaryEntry> 대신 제네릭 구조체인 <xref:System.Collections.Generic.KeyValuePair%602>를 열거형에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-107"><xref:System.Collections.Generic.Dictionary%602> is a generic version of <xref:System.Collections.Hashtable>; it uses the generic structure <xref:System.Collections.Generic.KeyValuePair%602> for enumeration instead of <xref:System.Collections.DictionaryEntry>.</span></span>  
  
 <span data-ttu-id="a9053-108"><xref:System.Collections.Generic.List%601>은 <xref:System.Collections.ArrayList>의 제네릭 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-108"><xref:System.Collections.Generic.List%601> is a generic version of <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="a9053-109">제네릭이 아닌 버전에 해당하는 제네릭 <xref:System.Collections.Generic.Queue%601> 및 <xref:System.Collections.Generic.Stack%601> 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-109">There are generic <xref:System.Collections.Generic.Queue%601> and <xref:System.Collections.Generic.Stack%601> classes that correspond to the nongeneric versions.</span></span>  
  
 <span data-ttu-id="a9053-110"><xref:System.Collections.Generic.SortedList%602>의 제네릭 버전과 제네릭이 아닌 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-110">There are generic and nongeneric versions of <xref:System.Collections.Generic.SortedList%602>.</span></span> <span data-ttu-id="a9053-111">두 버전은 모두 사전과 목록의 하이브리드입니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-111">Both versions are hybrids of a dictionary and a list.</span></span> <span data-ttu-id="a9053-112"><xref:System.Collections.Generic.SortedDictionary%602> 제네릭 클래스는 순수 사전이며 제네릭이 아닌 대응 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-112">The <xref:System.Collections.Generic.SortedDictionary%602> generic class is a pure dictionary and has no nongeneric counterpart.</span></span>  
  
 <span data-ttu-id="a9053-113"><xref:System.Collections.Generic.LinkedList%601> 제네릭 클래스는 연결된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-113">The <xref:System.Collections.Generic.LinkedList%601> generic class is a true linked list.</span></span> <span data-ttu-id="a9053-114">제네릭이 아닌 대응 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-114">It has no nongeneric counterpart.</span></span>  
  
### <a name="systemcollectionsobjectmodel"></a><span data-ttu-id="a9053-115">System.Collections.ObjectModel</span><span class="sxs-lookup"><span data-stu-id="a9053-115">System.Collections.ObjectModel</span></span>  
 <span data-ttu-id="a9053-116"><xref:System.Collections.ObjectModel.Collection%601> 제네릭 클래스는 고유한 제네릭 컬렉션 형식을 파생시키기 위한 기본 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-116">The <xref:System.Collections.ObjectModel.Collection%601> generic class provides a base class for deriving your own generic collection types.</span></span> <span data-ttu-id="a9053-117"><xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 클래스는 <xref:System.Collections.Generic.IList%601> 제네릭 인터페이스를 구현하는 형식에서 읽기 전용 컬렉션을 생성하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-117">The <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class provides an easy way to produce a read-only collection from any type that implements the <xref:System.Collections.Generic.IList%601> generic interface.</span></span> <span data-ttu-id="a9053-118"><xref:System.Collections.ObjectModel.KeyedCollection%602> 제네릭 클래스는 고유한 키를 포함하는 개체를 저장하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-118">The <xref:System.Collections.ObjectModel.KeyedCollection%602> generic class provides a way to store objects that contain their own keys.</span></span>  
  
## <a name="other-generic-types"></a><span data-ttu-id="a9053-119">기타 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="a9053-119">Other Generic Types</span></span>  
 <span data-ttu-id="a9053-120"><xref:System.Nullable%601> 제네릭 구조체를 통해 `null`이 할당될 수 있는 것처럼 값 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-120">The <xref:System.Nullable%601> generic structure allows you to use value types as if they could be assigned `null`.</span></span> <span data-ttu-id="a9053-121">이 기능은 값 형식을 포함하는 필드가 누락될 수 있는 데이터베이스 쿼리를 사용할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-121">This can be useful when working with database queries, where fields that contain value types can be missing.</span></span> <span data-ttu-id="a9053-122">제네릭 형식 매개 변수는 임의의 값 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-122">The generic type parameter can be any value type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9053-123">C# 및 Visual Basic에서는 언어에 nullable 형식에 대한 구문이 있기 때문에 명시적으로 <xref:System.Nullable%601>을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-123">In C# and Visual Basic, it is not necessary to use <xref:System.Nullable%601> explicitly because the language has syntax for nullable types.</span></span> <span data-ttu-id="a9053-124">[Nullable 형식(C# 프로그래밍 가이드)](../../csharp/programming-guide/nullable-types/index.md) 및 [Nullable 값 형식(Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9053-124">See [Nullable types (C# Programming Guide)](../../csharp/programming-guide/nullable-types/index.md) and [Nullable value types (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span></span> 
  
 <span data-ttu-id="a9053-125"><xref:System.ArraySegment%601> 제네릭 구조체는 0부터 시작하는 임의 형식의 1차원 배열 내에서 요소 범위를 구분하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-125">The <xref:System.ArraySegment%601> generic structure provides a way to delimit a range of elements within a one-dimensional, zero-based array of any type.</span></span> <span data-ttu-id="a9053-126">제네릭 형식 매개 변수는 배열 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-126">The generic type parameter is the type of the array's elements.</span></span>  
  
 <span data-ttu-id="a9053-127">이벤트가 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서 사용되는 이벤트 처리 패턴을 따르는 경우 <xref:System.EventHandler%601> 제네릭 대리자를 사용하면 이벤트를 처리할 대리자 형식을 선언할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-127">The <xref:System.EventHandler%601> generic delegate eliminates the need to declare a delegate type to handle events, if your event follows the event-handling pattern used by the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="a9053-128">예를 들어 이벤트 데이터를 저장할 <xref:System.EventArgs>에서 파생된 `MyEventArgs` 클래스를 만들었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-128">For example, suppose you have created a `MyEventArgs` class, derived from <xref:System.EventArgs>, to hold the data for your event.</span></span> <span data-ttu-id="a9053-129">그런 다음 이벤트를 다음과 같이 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9053-129">You can then declare the event as follows:</span></span>  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="a9053-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9053-130">See Also</span></span>  
 <xref:System.Collections.Generic?displayProperty=nameWithType>  
 <xref:System.Collections.ObjectModel?displayProperty=nameWithType>  
 [<span data-ttu-id="a9053-131">제네릭</span><span class="sxs-lookup"><span data-stu-id="a9053-131">Generics</span></span>](../../../docs/standard/generics/index.md)  
 [<span data-ttu-id="a9053-132">배열과 목록을 조작하기 위한 제네릭 대리자</span><span class="sxs-lookup"><span data-stu-id="a9053-132">Generic Delegates for Manipulating Arrays and Lists</span></span>](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)  
 [<span data-ttu-id="a9053-133">제네릭 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9053-133">Generic Interfaces</span></span>](../../../docs/standard/generics/interfaces.md)
