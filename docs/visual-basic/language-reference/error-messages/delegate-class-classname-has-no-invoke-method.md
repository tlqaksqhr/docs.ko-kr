---
title: 대리자 클래스 &#39; &lt;classname&gt; &#39; 에 Invoke 메서드가 없으므로 이러한 형식의 식은 메서드 호출의 대상일 수 없습니다
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: cc1abba46224772e733780800dd104dfc7ebe9ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588832"
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="c8129-102">대리자 클래스 &#39; &lt;classname&gt; &#39; 에 Invoke 메서드가 없으므로 이러한 형식의 식은 메서드 호출의 대상일 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="c8129-102">Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="c8129-103">에 대 한 호출 `Invoke` 때문에 실패 했습니다 대리자를 통해 `Invoke` 대리자 클래스에서 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c8129-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="c8129-104">**오류 ID:** BC30220</span><span class="sxs-lookup"><span data-stu-id="c8129-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c8129-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c8129-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="c8129-106">대리자 클래스의 인스턴스도 만들어졌는지 확인 한 `Dim` 문과 프로시저에 할당을 사용 하 여 대리자 인스턴스는 `AddressOf` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c8129-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="c8129-107">구현 합니다를 대리자 클래스를 구현 하는 코드는 `Invoke` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="c8129-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8129-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8129-108">See Also</span></span>  
 [<span data-ttu-id="c8129-109">대리자</span><span class="sxs-lookup"><span data-stu-id="c8129-109">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="c8129-110">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="c8129-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="c8129-111">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="c8129-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="c8129-112">Dim 문</span><span class="sxs-lookup"><span data-stu-id="c8129-112">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
