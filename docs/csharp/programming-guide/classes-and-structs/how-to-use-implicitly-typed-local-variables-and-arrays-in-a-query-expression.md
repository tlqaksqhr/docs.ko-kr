---
title: "방법: 쿼리 식에서 암시적으로 형식화된 지역 변수 및 배열 사용(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
caps.latest.revision: 15
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
ms.openlocfilehash: 60e22aacef05ae2fe1b5e7127396cc66f24661d3
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a><span data-ttu-id="89194-102">방법: 쿼리 식에서 암시적으로 형식화된 지역 변수 및 배열 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="89194-102">How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression (C# Programming Guide)</span></span>
<span data-ttu-id="89194-103">컴파일러에서 지역 변수의 형식을 확인하려는 경우 항상 암시적으로 형식화된 지역 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89194-103">You can use implicitly typed local variables whenever you want the compiler to determine the type of a local variable.</span></span> <span data-ttu-id="89194-104">쿼리 식에 자주 사용되는 무명 형식을 저장하려면 암시적으로 형식화된 지역 변수를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89194-104">You must use implicitly typed local variables to store anonymous types, which are often used in query expressions.</span></span> <span data-ttu-id="89194-105">다음 예제에서는 쿼리에서 암시적으로 형식화된 지역 변수의 선택적 및 필수 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89194-105">The following examples illustrate both optional and required uses of implicitly typed local variables in queries.</span></span>  
  
 <span data-ttu-id="89194-106">암시적으로 형식화된 지역 변수는 [var](../../../csharp/language-reference/keywords/var.md) 상황별 키워드를 사용하여 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="89194-106">Implicitly typed local variables are declared by using the [var](../../../csharp/language-reference/keywords/var.md) contextual keyword.</span></span> <span data-ttu-id="89194-107">자세한 내용은 [암시적으로 형식화된 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) 및 [암시적으로 형식화된 배열](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89194-107">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89194-108">예제</span><span class="sxs-lookup"><span data-stu-id="89194-108">Example</span></span>  
 <span data-ttu-id="89194-109">다음 예제에서는 `var` 키워드가 필요한 일반적인 시나리오로, 무명 형식의 시퀀스를 생성하는 쿼리 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89194-109">The following example shows a common scenario in which the `var` keyword is required: a query expression that produces a sequence of anonymous types.</span></span> <span data-ttu-id="89194-110">이 시나리오에서는 무명 형식의 형식 이름에 대한 액세스 권한이 없기 때문에 `foreach` 문의 쿼리 변수와 반복 변수가 모두 `var`을 사용하여 암시적으로 형식화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89194-110">In this scenario, both the query variable and the iteration variable in the `foreach` statement must be implicitly typed by using `var` because you do not have access to a type name for the anonymous type.</span></span> <span data-ttu-id="89194-111">무명 형식에 대한 자세한 내용은 [무명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89194-111">For more information about anonymous types, see [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
 <span data-ttu-id="89194-112">[!code-cs[csProgGuideLINQ#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="89194-112">[!code-cs[csProgGuideLINQ#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="89194-113">예제</span><span class="sxs-lookup"><span data-stu-id="89194-113">Example</span></span>  
 <span data-ttu-id="89194-114">다음 예제에서는 유사하지만 `var` 사용이 선택 사항인 상황에서 `var` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="89194-114">The following example uses the `var` keyword in a situation that is similar, but in which the use of `var` is optional.</span></span> <span data-ttu-id="89194-115">`student.LastName`이 문자열이기 때문에 쿼리를 실행하면 문자열 시퀀스가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="89194-115">Because `student.LastName` is a string, execution of the query returns a sequence of strings.</span></span> <span data-ttu-id="89194-116">따라서 `queryID`의 형식을 `var` 대신 `System.Collections.Generic.IEnumerable<string>`로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89194-116">Therefore, the type of `queryID` could be declared as `System.Collections.Generic.IEnumerable<string>` instead of `var`.</span></span> <span data-ttu-id="89194-117">`var` 키워드는 편의상 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="89194-117">Keyword `var` is used for convenience.</span></span> <span data-ttu-id="89194-118">예제에서 `foreach` 문의 반복 변수는 명시적으로 문자열로 형식화되었지만, 대신 `var`을 사용하여 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89194-118">In the example, the iteration variable in the `foreach` statement is explicitly typed as a string, but it could instead be declared by using `var`.</span></span> <span data-ttu-id="89194-119">반복 변수의 형식이 무명 형식이 아니기 때문에 `var` 사용은 요구 사항이 아니라 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="89194-119">Because the type of the iteration variable is not an anonymous type, the use of `var` is an option, not a requirement.</span></span> <span data-ttu-id="89194-120">`var` 자체는 형식이 아니라 형식을 유추하고 할당하도록 컴파일러에 지시하는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="89194-120">Remember, `var` itself is not a type, but an instruction to the compiler to infer and assign the type.</span></span>  
  
 <span data-ttu-id="89194-121">[!code-cs[csProgGuideLINQ#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="89194-121">[!code-cs[csProgGuideLINQ#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89194-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89194-122">See Also</span></span>  
 <span data-ttu-id="89194-123">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="89194-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="89194-124">[확장 메서드](../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span><span class="sxs-lookup"><span data-stu-id="89194-124">[Extension Methods](../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span></span>  
 <span data-ttu-id="89194-125">[LINQ(Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span><span class="sxs-lookup"><span data-stu-id="89194-125">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span></span>  
 <span data-ttu-id="89194-126">[var](../../../csharp/language-reference/keywords/var.md) </span><span class="sxs-lookup"><span data-stu-id="89194-126">[var](../../../csharp/language-reference/keywords/var.md) </span></span>  
 [<span data-ttu-id="89194-127">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="89194-127">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)

