---
title: "?? 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ??_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
caps.latest.revision: 17
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
ms.openlocfilehash: 86e50b97d7ded8adc74f031faf026b69ccdd0c87
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="c6dd1-103">??</span><span class="sxs-lookup"><span data-stu-id="c6dd1-103">??</span></span> <span data-ttu-id="c6dd1-104">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c6dd1-104">Operator (C# Reference)</span></span>
<span data-ttu-id="c6dd1-105">`??` 연산자는 null 병합 연산자라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6dd1-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="c6dd1-106">이 연산자는 피연산자가 null이 아닐 경우 왼쪽 피연산자를 반환하고 null일 경우 오른쪽 피연산자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c6dd1-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6dd1-107">설명</span><span class="sxs-lookup"><span data-stu-id="c6dd1-107">Remarks</span></span>  
 <span data-ttu-id="c6dd1-108">nullable 형식은 형식 도메인의 값을 나타낼 수 있거나 값을 정의하지 않을 수 있습니다(이 경우 값은 null).</span><span class="sxs-lookup"><span data-stu-id="c6dd1-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="c6dd1-109">왼쪽 연산자에 값이 null인 null 허용 형식이 있는 경우 `??` 연산자의 구문 표현을 사용하여 적절한 값을 반환할 수 있습니다(오른쪽 피연산자).</span><span class="sxs-lookup"><span data-stu-id="c6dd1-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullible type whose value is null.</span></span> <span data-ttu-id="c6dd1-110">`??` 연산자를 사용하지 않고 nullable 값 형식을 nullable이 아닌 값 형식에 할당하려고 하면 컴파일 타임 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c6dd1-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="c6dd1-111">캐스트를 사용할 때 nullable 값 형식이 현재 정의되어 있지 않으면 `InvalidOperationException` 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6dd1-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>  
  
 <span data-ttu-id="c6dd1-112">자세한 내용은 [Null 허용 형식](../../../csharp/programming-guide/nullable-types/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6dd1-112">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="c6dd1-113">?? 연산자의 결과는</span><span class="sxs-lookup"><span data-stu-id="c6dd1-113">The result of a ??</span></span> <span data-ttu-id="c6dd1-114">해당 두 인수가 모두 상수인 경우에도 상수로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6dd1-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6dd1-115">예제</span><span class="sxs-lookup"><span data-stu-id="c6dd1-115">Example</span></span>  
 <span data-ttu-id="c6dd1-116">[!code-cs[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c6dd1-116">[!code-cs[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6dd1-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6dd1-117">See Also</span></span>  
 <span data-ttu-id="c6dd1-118">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c6dd1-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c6dd1-119">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c6dd1-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c6dd1-120">[C# 연산자](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="c6dd1-120">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="c6dd1-121">[Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="c6dd1-121">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 <span data-ttu-id="c6dd1-122">[What Exactly Does ‘Lifted’ mean?](http://go.microsoft.com/fwlink/?LinkID=112382)(‘리프트’란 정확히 어떤 의미인가요?)</span><span class="sxs-lookup"><span data-stu-id="c6dd1-122">[What Exactly Does 'Lifted' mean?](http://go.microsoft.com/fwlink/?LinkID=112382)</span></span>

