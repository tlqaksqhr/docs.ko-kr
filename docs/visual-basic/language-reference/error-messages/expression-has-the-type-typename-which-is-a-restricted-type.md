---
title: 식에는 형식이 &#39; &lt;typename&gt; &#39; 제한 된 형식에서 상속 된 멤버에 액세스 하는 데 사용 될 수 없습니다 하며 &#39;개체&#39; 또는 &#39;ValueType&#39;
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 2ba2298da77ac31abc0b1b4ad84328be7bc6dbb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587575"
---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a><span data-ttu-id="beb4e-102">식에는 형식이 &#39; &lt;typename&gt; &#39; 제한 된 형식에서 상속 된 멤버에 액세스 하는 데 사용 될 수 없습니다 하며 &#39;개체&#39; 또는 &#39;ValueType&#39;</span><span class="sxs-lookup"><span data-stu-id="beb4e-102">Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39;</span></span>
<span data-ttu-id="beb4e-103">식을 공용 언어 런타임 (CLR) 하 여 boxed 수 없는 형식으로 계산 하지만 boxing을 필요로 하는 멤버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="beb4e-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="beb4e-104">*Boxing* 은 형식을 경우에 따라 `Object` 또는 <xref:System.ValueType>으로 변환하는 데 필요한 처리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="beb4e-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="beb4e-105">공용 언어 런타임에서 특정 구조 종류를 예를 들어 상자 없습니다 <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, 및 <xref:System.TypedReference>합니다.</span><span class="sxs-lookup"><span data-stu-id="beb4e-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="beb4e-106">이 식에서 상속 된 메서드를 호출 하려면 제한 된 형식을 사용 하려고 <xref:System.Object> 또는 <xref:System.ValueType>와 같은 <xref:System.Object.GetHashCode%2A> 또는 <xref:System.Object.ToString%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="beb4e-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="beb4e-107">이 메서드에 액세스 하려면 Visual Basic에서이 오류를 발생 시키는 암시적 boxing 변환을 시도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="beb4e-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="beb4e-108">**오류 ID:** BC31393</span><span class="sxs-lookup"><span data-stu-id="beb4e-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="beb4e-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="beb4e-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="beb4e-110">제시된 형식으로 계산되는 식을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="beb4e-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2.  <span data-ttu-id="beb4e-111">상속 된 메서드를 호출 하려고 하는 문의 일부가 찾습니다 <xref:System.Object> 또는 <xref:System.ValueType>합니다.</span><span class="sxs-lookup"><span data-stu-id="beb4e-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3.  <span data-ttu-id="beb4e-112">메서드 호출을 방지 하려면 문을 다시 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="beb4e-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb4e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="beb4e-113">See Also</span></span>  
 [<span data-ttu-id="beb4e-114">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="beb4e-114">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
