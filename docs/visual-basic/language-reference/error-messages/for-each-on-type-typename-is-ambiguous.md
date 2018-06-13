---
title: '&#39;각&#39; 유형에 &#39; &lt;typename&gt; &#39; 의 여러 인스턴스를 구현 하기 때문에 모호 &#39;System.Collections.Generic.IEnumerable (Of T)&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 8c48a7134eb8da83fb418b9aa91d55dcbe8e8bcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590974"
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a><span data-ttu-id="5263a-102">&#39;각&#39; 유형에 &#39; &lt;typename&gt; &#39; 의 여러 인스턴스를 구현 하기 때문에 모호 &#39;System.Collections.Generic.IEnumerable (Of T)&#39;</span><span class="sxs-lookup"><span data-stu-id="5263a-102">&#39;For Each&#39; on type &#39;&lt;typename&gt;&#39; is ambiguous because the type implements multiple instantiations of &#39;System.Collections.Generic.IEnumerable(Of T)&#39;</span></span>
<span data-ttu-id="5263a-103">A `For Each` 에 둘 이상의 반복기 변수를 지정 하는 문을 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="5263a-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="5263a-104">반복기 변수를 구현 하는 형식 이어야 합니다는 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 인터페이스 중 하나에 `Collections` 의 네임 스페이스는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="5263a-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="5263a-105">둘 이상의 생성 된 제네릭 인터페이스를 각 구문에 대 한 다른 형식 인수를 사용 하 여 구현 하는 클래스에 대 한 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5263a-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="5263a-106">이 작업을 수행 하는 클래스에서 반복기 변수를 사용 하는 경우 해당 변수가 둘 이상의 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="5263a-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="5263a-107">이 경우 Visual Basic 호출할 메서드를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5263a-107">In such a case, Visual Basic cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="5263a-108">**오류 ID:** BC32096</span><span class="sxs-lookup"><span data-stu-id="5263a-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5263a-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="5263a-109">To correct this error</span></span>  
  
-   <span data-ttu-id="5263a-110">사용 하 여 [DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 또는 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md) 반복기 변수 형식을 정의 하는 인터페이스로 캐스팅할 수는 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 사용할 방법을 합니다.</span><span class="sxs-lookup"><span data-stu-id="5263a-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5263a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5263a-111">See Also</span></span>  
 [<span data-ttu-id="5263a-112">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="5263a-112">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="5263a-113">인터페이스</span><span class="sxs-lookup"><span data-stu-id="5263a-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
