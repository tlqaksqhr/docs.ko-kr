---
title: '&#39;가져오기&#39; 속성의 접근자 &#39; &lt;propertyname&gt; &#39; 는 액세스할 수 없습니다'
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: 0972c0909f8b07aa1c6700ec32d1a1ca55d00cc1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590207"
---
# <a name="39get39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a><span data-ttu-id="7da53-102">&#39;가져오기&#39; 속성의 접근자 &#39; &lt;propertyname&gt; &#39; 는 액세스할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="7da53-102">&#39;Get&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible</span></span>
<span data-ttu-id="7da53-103">문에서 속성에 대 한 액세스 권한이 없습니다 속성의 값을 검색 하려고 `Get` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7da53-103">A statement attempts to retrieve the value of a property when it does not have access to the property's `Get` procedure.</span></span>  
  
 <span data-ttu-id="7da53-104">경우는 [Get 문을](../../../visual-basic/language-reference/statements/get-statement.md) 수준 보다 더 제한적인 액세스로 표시 되 해당 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md), 속성 값을 읽지 다음과 같은 경우에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da53-104">If the [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to read the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="7da53-105">`Get` 문을 표시 되어 [개인](../../../visual-basic/language-reference/modifiers/private.md) 호출 하는 코드는 클래스 또는 속성이 정의 된 구조 외부입니다.</span><span class="sxs-lookup"><span data-stu-id="7da53-105">The `Get` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="7da53-106">`Get` 문을 표시 되어 [Protected](../../../visual-basic/language-reference/modifiers/protected.md) 클래스 또는 구조체 속성이 정의 되어 있는 디렉터리 또는 없습니다 파생된 클래스에서 호출 하는 코드는 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da53-106">The `Get` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="7da53-107">`Get` 문을 표시 되어 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 고 호출 코드에에서 없는 속성이 정의 된 동일한 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="7da53-107">The `Get` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="7da53-108">**오류 ID:** BC31103</span><span class="sxs-lookup"><span data-stu-id="7da53-108">**Error ID:** BC31103</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7da53-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7da53-109">To correct this error</span></span>  
  
-   <span data-ttu-id="7da53-110">속성을 정의 하는 소스 코드 제어를 사용 하도록 설정한 경우 선언을 고려는 `Get` 해당 속성과 같은 액세스 수준이 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7da53-110">If you have control of the source code defining the property, consider declaring the `Get` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="7da53-111">속성을 정의 하는 소스 코드 제어 없는 또는 제한 해야 하는 경우는 `Get` 프로시저 액세스 수준으로 속성 자체에 쉽게 액세스할 수 있는 코드 영역이 속성 값을 읽을 수 있는 문을 이동 하려고 보다는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7da53-111">If you do not have control of the source code defining the property, or you must restrict the `Get` procedure access level more than the property itself, try to move the statement that reads the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da53-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7da53-112">See Also</span></span>  
 [<span data-ttu-id="7da53-113">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="7da53-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="7da53-114">방법: 액세스 수준이 혼합된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="7da53-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
