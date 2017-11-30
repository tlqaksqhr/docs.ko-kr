---
title: "?? 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ??_CSharpKeyword
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1a49d36b8580812c08e9ee080a9602d9fc2027ba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="eb9ab-103">??</span><span class="sxs-lookup"><span data-stu-id="eb9ab-103">??</span></span> <span data-ttu-id="eb9ab-104">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="eb9ab-104">Operator (C# Reference)</span></span>
<span data-ttu-id="eb9ab-105">`??` 연산자는 null 병합 연산자라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb9ab-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="eb9ab-106">이 연산자는 피연산자가 null이 아닐 경우 왼쪽 피연산자를 반환하고 null일 경우 오른쪽 피연산자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eb9ab-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb9ab-107">설명</span><span class="sxs-lookup"><span data-stu-id="eb9ab-107">Remarks</span></span>  
 <span data-ttu-id="eb9ab-108">nullable 형식은 형식 도메인의 값을 나타낼 수 있거나 값을 정의하지 않을 수 있습니다(이 경우 값은 null).</span><span class="sxs-lookup"><span data-stu-id="eb9ab-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="eb9ab-109">사용할 수는 `??` (오른쪽 피연산자) 적절 한 값을 반환 하려면 연산자의 구문 표현이 왼쪽된 피연산자에 null 허용 형식이 있는 값이 null 인 경우.</span><span class="sxs-lookup"><span data-stu-id="eb9ab-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullable type whose value is null.</span></span> <span data-ttu-id="eb9ab-110">`??` 연산자를 사용하지 않고 nullable 값 형식을 nullable이 아닌 값 형식에 할당하려고 하면 컴파일 타임 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="eb9ab-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="eb9ab-111">캐스트를 사용할 때 nullable 값 형식이 현재 정의되어 있지 않으면 `InvalidOperationException` 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb9ab-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>  
  
 <span data-ttu-id="eb9ab-112">자세한 내용은 [Null 허용 형식](../../../csharp/programming-guide/nullable-types/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb9ab-112">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="eb9ab-113">?? 연산자의 결과는</span><span class="sxs-lookup"><span data-stu-id="eb9ab-113">The result of a ??</span></span> <span data-ttu-id="eb9ab-114">해당 두 인수가 모두 상수인 경우에도 상수로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb9ab-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb9ab-115">예제</span><span class="sxs-lookup"><span data-stu-id="eb9ab-115">Example</span></span>  
 [!code-csharp[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="eb9ab-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb9ab-116">See Also</span></span>  
 [<span data-ttu-id="eb9ab-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="eb9ab-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="eb9ab-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="eb9ab-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="eb9ab-119">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="eb9ab-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="eb9ab-120">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="eb9ab-120">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 <span data-ttu-id="eb9ab-121">[What Exactly Does ‘Lifted’ mean?](http://go.microsoft.com/fwlink/?LinkID=112382)(‘리프트’란 정확히 어떤 의미인가요?)</span><span class="sxs-lookup"><span data-stu-id="eb9ab-121">[What Exactly Does 'Lifted' mean?](http://go.microsoft.com/fwlink/?LinkID=112382)</span></span>
