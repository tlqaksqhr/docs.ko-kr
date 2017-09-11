---
title: "[] 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '[]_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
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
ms.openlocfilehash: b49d41af0dd4dc34b1b74c62ce8779aa31d69f77
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="6825d-102">[] 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="6825d-102">[] Operator (C# Reference)</span></span>
<span data-ttu-id="6825d-103">대괄호(`[]`)는 배열, 인덱서 및 특성에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6825d-103">Square brackets (`[]`) are used for arrays, indexers, and attributes.</span></span> <span data-ttu-id="6825d-104">포인터에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6825d-104">They can also be used with pointers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6825d-105">설명</span><span class="sxs-lookup"><span data-stu-id="6825d-105">Remarks</span></span>  
 <span data-ttu-id="6825d-106">배열 형식은 뒤에 `[]`가 오는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6825d-106">An array type is a type followed by `[]`:</span></span>  
  
 <span data-ttu-id="6825d-107">[!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6825d-107">[!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="6825d-108">배열의 요소에 액세스하려면 원하는 요소의 인덱스를 대괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="6825d-108">To access an element of an array, the index of the desired element is enclosed in brackets:</span></span>  
  
 <span data-ttu-id="6825d-109">[!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6825d-109">[!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]</span></span>  
  
 <span data-ttu-id="6825d-110">배열 인덱스가 범위를 벗어나면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="6825d-110">An exception is thrown if an array index is out of range.</span></span>  
  
 <span data-ttu-id="6825d-111">배열 인덱싱 연산자를 오버로드할 수는 없습니다. 그러나 형식에서 하나 이상의 매개 변수를 사용하는 속성 및 인덱서를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6825d-111">The array indexing operator cannot be overloaded; however, types can define indexers, and properties that take one or more parameters.</span></span> <span data-ttu-id="6825d-112">인덱서 매개 변수는 배열 인덱스와 마찬가지로 대괄호에 묶여 있지만 인덱서 매개 변수는 정수여야 하는 배열 인덱스와 달리 임의 형식으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6825d-112">Indexer parameters are enclosed in square brackets, just like array indexes, but indexer parameters can be declared to be of any type, unlike array indexes, which must be integral.</span></span>  
  
 <span data-ttu-id="6825d-113">예를 들어 .NET Framework에서는 임의 형식의 키와 값을 연결하는 `Hashtable` 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6825d-113">For example, the .NET Framework defines a `Hashtable` type that associates keys and values of arbitrary type:</span></span>  
  
 <span data-ttu-id="6825d-114">[!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="6825d-114">[!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]</span></span>  
  
 <span data-ttu-id="6825d-115">대괄호는 [특성](../../../csharp/programming-guide/concepts/attributes/index.md)을 지정하는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6825d-115">Square brackets are also used to specify [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md):</span></span>  
  
 <span data-ttu-id="6825d-116">[!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="6825d-116">[!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]</span></span>  
  
 <span data-ttu-id="6825d-117">대괄호를 사용하여 포인터를 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6825d-117">You can use square brackets to index off a pointer:</span></span>  
  
 <span data-ttu-id="6825d-118">[!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="6825d-118">[!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]</span></span>  
  
 <span data-ttu-id="6825d-119">범위 검사는 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6825d-119">No bounds checking is performed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6825d-120">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="6825d-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6825d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6825d-121">See Also</span></span>  
 <span data-ttu-id="6825d-122">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6825d-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6825d-123">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6825d-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6825d-124">[C# 연산자](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="6825d-124">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="6825d-125">[배열](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="6825d-125">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="6825d-126">[인덱서](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="6825d-126">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="6825d-127">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="6825d-127">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 [<span data-ttu-id="6825d-128">fixed 문</span><span class="sxs-lookup"><span data-stu-id="6825d-128">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)

