---
title: "식에는 형식이 &quot;&lt;typename&gt;&quot; 제한 된 형식 및 &quot; Object &quot; 또는 &quot;&quot;에서 상속 된 멤버에 액세스를 사용할 수 있는 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc31393
- vbc31393
dev_langs:
- VB
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
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
ms.openlocfilehash: b89f7e83bf596c52296a090563d0dd0403ace548
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a><span data-ttu-id="b2acd-102">식에는 형식이 '&lt;typename&gt;' 제한 된 유형의 이며 ' Object ' 또는 ''에서 상속 된 멤버 액세스에 사용할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="b2acd-102">Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39;</span></span>
<span data-ttu-id="b2acd-103">식을 공용 언어 런타임 (CLR) 하 여 boxed 없습니다 하는 형식으로 계산 되지만 boxing을 필요로 하는 멤버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acd-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="b2acd-104">*Boxing* 하는 형식을 변환 하는 데 필요한 처리를 말합니다 `Object` 또는 <xref:System.ValueType>.</xref:System.ValueType> 하는 경우에 따라</span><span class="sxs-lookup"><span data-stu-id="b2acd-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="b2acd-105">공용 언어 런타임에서 특정 구조 종류를 예를 들어 상자 없습니다 <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, 및 <xref:System.TypedReference>.</xref:System.TypedReference> </xref:System.RuntimeArgumentHandle> </xref:System.ArgIterator></span><span class="sxs-lookup"><span data-stu-id="b2acd-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="b2acd-106">사용 하 여 제한 된 형식에서 상속 된 메서드를 호출 합니다.이 식은 시도 <xref:System.Object>또는 <xref:System.ValueType>, <xref:System.Object.GetHashCode%2A>또는 <xref:System.Object.ToString%2A>.</xref:System.Object.ToString%2A> </xref:System.Object.GetHashCode%2A> 같은</xref:System.ValueType> </xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="b2acd-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="b2acd-107">이 메서드에 액세스 하려면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 이 오류가 발생 하는 암시적 boxing 변환을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acd-107">To access this method, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="b2acd-108">**오류 ID:** BC31393</span><span class="sxs-lookup"><span data-stu-id="b2acd-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b2acd-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b2acd-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="b2acd-110">제시된 형식으로 계산되는 식을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b2acd-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2.  <span data-ttu-id="b2acd-111"><xref:System.Object>또는 <xref:System.ValueType>.</xref:System.ValueType> </xref:System.Object> 에서 상속 된 메서드를 호출 하려고 하는 문의 부분을 찾습니다</span><span class="sxs-lookup"><span data-stu-id="b2acd-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3.  <span data-ttu-id="b2acd-112">메서드 호출을 방지 하는 문을 다시 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acd-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2acd-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2acd-113">See Also</span></span>  
 [<span data-ttu-id="b2acd-114">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="b2acd-114">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
