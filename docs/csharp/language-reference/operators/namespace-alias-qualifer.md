---
title: ':: 연산자(C# 참조)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6b4f1683e1250ed745e15ced88203ca942c75ff8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="120df-102">:: 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="120df-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="120df-103">네임스페이스 별칭 한정자(`::`)는 식별자를 조회하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="120df-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="120df-104">다음 예제와 같이 항상 두 식별자 사이에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="120df-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="120df-105">설명</span><span class="sxs-lookup"><span data-stu-id="120df-105">Remarks</span></span>  
 <span data-ttu-id="120df-106">네임스페이스 별칭 한정자는 `global`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="120df-106">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="120df-107">별칭이 지정된 네임스페이스가 아니라 전역 네임스페이스에서 조회를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="120df-107">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="120df-108">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="120df-108">For More Information</span></span>  
 <span data-ttu-id="120df-109">`::` 연산자를 사용하는 방법의 예는 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="120df-109">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="120df-110">방법: 전역 네임스페이스 별칭 사용</span><span class="sxs-lookup"><span data-stu-id="120df-110">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="120df-111">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="120df-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="120df-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="120df-112">See Also</span></span>  
 [<span data-ttu-id="120df-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="120df-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="120df-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="120df-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="120df-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="120df-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="120df-116">네임스페이스 키워드</span><span class="sxs-lookup"><span data-stu-id="120df-116">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="120df-117">. 연산자</span><span class="sxs-lookup"><span data-stu-id="120df-117">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
 [<span data-ttu-id="120df-118">extern alias</span><span class="sxs-lookup"><span data-stu-id="120df-118">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)
