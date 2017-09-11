---
title: "각&quot; 형식의 &quot; for &quot;&lt;typename&gt;&quot; 형식은 &quot;System.Collections.Generic.IEnumerable (Of T)&quot;의 여러 인스턴스를 구현 하기 때문에 모호 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32096
- bc32096
dev_langs:
- VB
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 783c741a8acb0d27ef6ff5c52939bd12a026ba74
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a><span data-ttu-id="69d0c-102">각' 형식의 ' for '&lt;typename&gt;' 형식은 'System.Collections.Generic.IEnumerable (Of T)'의 여러 인스턴스를 구현 하기 때문에 모호</span><span class="sxs-lookup"><span data-stu-id="69d0c-102">&#39;For Each&#39; on type &#39;&lt;typename&gt;&#39; is ambiguous because the type implements multiple instantiations of &#39;System.Collections.Generic.IEnumerable(Of T)&#39;</span></span>
<span data-ttu-id="69d0c-103">A `For Each` 에 둘 이상의 반복기 변수를 지정 하는 문을 <xref:System.Collections.IEnumerable.GetEnumerator%2A>메서드.</xref:System.Collections.IEnumerable.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="69d0c-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="69d0c-104">반복기 변수를 구현 하는 형식 이어야 합니다는 <xref:System.Collections.IEnumerable?displayProperty=fullName>또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>인터페이스 중 하나에 `Collections` 의 네임 스페이스는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> </xref:System.Collections.IEnumerable?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="69d0c-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=fullName> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> interface in one of the `Collections` namespaces of the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="69d0c-105">둘 이상의 생성 된 제네릭 인터페이스를 각 구문에 대 한 다른 형식 인수를 사용 하 여 구현 하는 클래스에 대 한 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="69d0c-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="69d0c-106">이 작업을 수행 하는 클래스에서 반복기 변수에 사용 되는 경우 해당 변수가 둘 이상의 <xref:System.Collections.IEnumerable.GetEnumerator%2A>메서드.</xref:System.Collections.IEnumerable.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="69d0c-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="69d0c-107">이 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 호출할 메서드를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69d0c-107">In such a case, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="69d0c-108">**오류 ID:** BC32096</span><span class="sxs-lookup"><span data-stu-id="69d0c-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="69d0c-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="69d0c-109">To correct this error</span></span>  
  
-   <span data-ttu-id="69d0c-110">사용 하 여 [DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 또는 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md) 반복기 변수 형식을 정의 하는 인터페이스를 캐스팅 하는 <xref:System.Collections.IEnumerable.GetEnumerator%2A>메서드를 사용 하려는.</xref:System.Collections.IEnumerable.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="69d0c-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69d0c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69d0c-111">See Also</span></span>  
 <span data-ttu-id="69d0c-112">[각각에 대해... Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="69d0c-112">[For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="69d0c-113"> [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)</span><span class="sxs-lookup"><span data-stu-id="69d0c-113"> [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)</span></span>
