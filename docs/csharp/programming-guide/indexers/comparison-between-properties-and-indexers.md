---
title: "속성 및 인덱서 비교(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4bb2de1cfdcf4a8a7c847dfabe8d69124a4adf90
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="e2f61-102">속성 및 인덱서 비교(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e2f61-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="e2f61-103">인덱서는 속성과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-103">Indexers are like properties.</span></span> <span data-ttu-id="e2f61-104">다음 표에 나와 있는 차이점을 제외하면 속성 접근자에 대해 정의된 모든 규칙이 인덱서 접근자에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="e2f61-105">속성</span><span class="sxs-lookup"><span data-stu-id="e2f61-105">Property</span></span>|<span data-ttu-id="e2f61-106">인덱서</span><span class="sxs-lookup"><span data-stu-id="e2f61-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="e2f61-107">공용 데이터 멤버인 것처럼 메서드를 호출할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="e2f61-108">개체 자체에 배열 표기법을 사용하여 개체의 내부 컬렉션 요소에 액세스할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="e2f61-109">단순한 이름을 통해 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-109">Accessed through a simple name.</span></span>|<span data-ttu-id="e2f61-110">인덱스를 통해 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="e2f61-111">정적 또는 인스턴스 멤버일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="e2f61-112">인스턴스 멤버여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="e2f61-113">속성의 [get](../../../csharp/language-reference/keywords/get.md) 접근자에는 매개 변수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-113">A [get](../../../csharp/language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="e2f61-114">인덱서의 `get` 접근자에는 인덱서와 동일한 형식 매개 변수 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="e2f61-115">속성의 [set](../../../csharp/language-reference/keywords/set.md) 접근자에는 암시적 `value` 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-115">A [set](../../../csharp/language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="e2f61-116">인덱서의 `set` 접근자에는 인덱서와 동일한 형식 매개 변수 목록이 있으며 [value](../../../csharp/language-reference/keywords/value.md) 매개 변수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../../csharp/language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="e2f61-117">[자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)을 사용하여 약식 구문을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-117">Supports shortened syntax with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="e2f61-118">약식 구문을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2f61-118">Does not support shortened syntax.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2f61-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2f61-119">See Also</span></span>  
 <span data-ttu-id="e2f61-120">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e2f61-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e2f61-121">[인덱서](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="e2f61-121">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 [<span data-ttu-id="e2f61-122">속성</span><span class="sxs-lookup"><span data-stu-id="e2f61-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

