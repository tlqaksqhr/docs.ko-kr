---
title: "형식(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- types [C#]
- data types [C#], type system
ms.assetid: 16b984df-f417-4e02-b1e6-4589d4a614ea
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
ms.openlocfilehash: 2816a5dd86e71641198a340b3a72094dffc93bdf
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="types-c-reference"></a><span data-ttu-id="cce9c-102">형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="cce9c-102">Types (C# Reference)</span></span>
<span data-ttu-id="cce9c-103">C# 형식화 시스템에는 다음 범주가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cce9c-103">The C# typing system contains the following categories:</span></span>  
  
-   [<span data-ttu-id="cce9c-104">값 형식</span><span class="sxs-lookup"><span data-stu-id="cce9c-104">Value types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
  
-   [<span data-ttu-id="cce9c-105">참조 형식</span><span class="sxs-lookup"><span data-stu-id="cce9c-105">Reference types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [<span data-ttu-id="cce9c-106">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="cce9c-106">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
 <span data-ttu-id="cce9c-107">값 형식인 변수는 데이터를 저장하고, 참조 형식인 변수는 실제 데이터에 대한 참조를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cce9c-107">Variables that are value types store data, and those that are reference types store references to the actual data.</span></span> <span data-ttu-id="cce9c-108">참조 형식을 개체라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="cce9c-108">Reference types are also referred to as objects.</span></span> <span data-ttu-id="cce9c-109">포인터 형식은 [안전하지 않은](../../../csharp/language-reference/keywords/unsafe.md) 모드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce9c-109">Pointer types can be used only in [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode.</span></span>  
  
 <span data-ttu-id="cce9c-110">[boxing 및 unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)을 사용하여 값 형식을 참조 형식으로 변환한 다음 값 형식으로 다시 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce9c-110">It is possible to convert a value type to a reference type, and back again to a value type, by using [boxing and unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span> <span data-ttu-id="cce9c-111">boxed 값 형식을 제외하고 참조 형식을 값 형식으로 변환할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cce9c-111">With the exception of a boxed value type, you cannot convert a reference type to a value type.</span></span>  
  
 <span data-ttu-id="cce9c-112">이 섹션에서는 [void](../../../csharp/language-reference/keywords/void.md)도 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="cce9c-112">This section also introduces [void](../../../csharp/language-reference/keywords/void.md).</span></span>  
  
 <span data-ttu-id="cce9c-113">값 형식은 nullable이기도 하므로, 값이 아닌 추가 상태를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce9c-113">Value types are also nullable, which means they can store an additional non-value state.</span></span> <span data-ttu-id="cce9c-114">자세한 내용은 [Null 허용 형식](../../../csharp/programming-guide/nullable-types/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cce9c-114">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cce9c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cce9c-115">See Also</span></span>  
 <span data-ttu-id="cce9c-116">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="cce9c-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="cce9c-117">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cce9c-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="cce9c-118">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="cce9c-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="cce9c-119">[형식 참조 테이블](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span><span class="sxs-lookup"><span data-stu-id="cce9c-119">[Reference Tables for Types](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span></span>  
 <span data-ttu-id="cce9c-120">[캐스팅 및 형식 변환](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="cce9c-120">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 [<span data-ttu-id="cce9c-121">유형</span><span class="sxs-lookup"><span data-stu-id="cce9c-121">Types</span></span>](../../../csharp/programming-guide/types/index.md)

