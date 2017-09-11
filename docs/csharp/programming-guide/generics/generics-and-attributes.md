---
title: "제네릭 및 특성(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: 13
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
ms.openlocfilehash: 5136ae928a3a4b6f8ec4d86100d695f958d55858
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="4e885-102">제네릭 및 특성(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4e885-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="4e885-103">제네릭 형식에 특성을 적용하는 방법은 제네릭이 아닌 형식의 경우와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="4e885-104">특성 적용에 대한 자세한 내용은 [특성](../../../csharp/programming-guide/concepts/attributes/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e885-104">For more information on applying attributes, see [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="4e885-105">사용자 지정 특성은 형식 인수가 제공되지 않는 개방형 제네릭 형식 및 모든 형식 매개 변수에 인수를 제공하는 폐쇄형으로 생성된 제네릭 형식만 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="4e885-106">다음 예에서는 이러한 사용자 지정 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-106">The following examples use this custom attribute:</span></span>  
  
 <span data-ttu-id="4e885-107">[!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4e885-107">[!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]</span></span>  
  
 <span data-ttu-id="4e885-108">특성은 개방형 제네릭 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-108">An attribute can reference an open generic type:</span></span>  
  
 <span data-ttu-id="4e885-109">[!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4e885-109">[!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]</span></span>  
  
 <span data-ttu-id="4e885-110">적절한 수의 쉼표를 사용하여 여러 형식 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-110">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="4e885-111">이 예제에서 `GenericClass2`는 두 개의 형식 매개 변수를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-111">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 <span data-ttu-id="4e885-112">[!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="4e885-112">[!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]</span></span>  
  
 <span data-ttu-id="4e885-113">특성은 폐쇄형으로 생성된 제네릭 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-113">An attribute can reference a closed constructed generic type:</span></span>  
  
 <span data-ttu-id="4e885-114">[!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="4e885-114">[!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]</span></span>  
  
 <span data-ttu-id="4e885-115">제네릭 형식 매개 변수를 참조하는 특성은 컴파일 시간 오류를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-115">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 <span data-ttu-id="4e885-116">[!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="4e885-116">[!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]</span></span>  
  
 <span data-ttu-id="4e885-117">제네릭 형식은 <xref:System.Attribute>에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-117">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 <span data-ttu-id="4e885-118">[!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="4e885-118">[!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]</span></span>  
  
 <span data-ttu-id="4e885-119">런타임에 제네릭 형식 또는 형식 매개 변수에 대한 정보를 얻으려면 <xref:System.Reflection>의 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-119">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="4e885-120">자세한 내용은 [제네릭 및 리플렉션](../../../csharp/programming-guide/generics/generics-and-reflection.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e885-120">For more information, see [Generics and Reflection](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e885-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e885-121">See Also</span></span>  
 <span data-ttu-id="4e885-122">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4e885-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4e885-123">[제네릭](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="4e885-123">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 [<span data-ttu-id="4e885-124">특성</span><span class="sxs-lookup"><span data-stu-id="4e885-124">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)

