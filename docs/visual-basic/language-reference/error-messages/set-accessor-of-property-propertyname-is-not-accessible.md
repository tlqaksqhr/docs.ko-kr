---
title: '&#39; 설정 &#39; 접근자 속성 &#39; &lt;propertyname&gt;&#39; 액세스할 수 없으면'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9256a09b719ad3890e1d7c2cc23ffb0d40eec62f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a><span data-ttu-id="9b402-102">&#39; 설정 &#39; 접근자 속성 &#39; &lt;propertyname&gt;&#39; 액세스할 수 없으면</span><span class="sxs-lookup"><span data-stu-id="9b402-102">&#39;Set&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible</span></span>
<span data-ttu-id="9b402-103">문에서 속성에 대 한 액세스 권한이 없습니다 속성의 값을 저장 하려고 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="9b402-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="9b402-104">경우는 [Set 문을](../../../visual-basic/language-reference/statements/set-statement.md) 수준 보다 더 제한적인 액세스로 표시 되 해당 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md), 속성 값을 설정 하는 다음과 같은 경우에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b402-104">If the [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="9b402-105">`Set` 문을 표시 되어 [개인](../../../visual-basic/language-reference/modifiers/private.md) 호출 하는 코드는 클래스 또는 속성이 정의 된 구조 외부입니다.</span><span class="sxs-lookup"><span data-stu-id="9b402-105">The `Set` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="9b402-106">`Set` 문을 표시 되어 [Protected](../../../visual-basic/language-reference/modifiers/protected.md) 클래스 또는 구조체 속성이 정의 되어 있는 디렉터리 또는 없습니다 파생된 클래스에서 호출 하는 코드는 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b402-106">The `Set` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="9b402-107">`Set` 문을 표시 되어 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 고 호출 코드에에서 없는 속성이 정의 된 동일한 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="9b402-107">The `Set` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="9b402-108">**오류 ID:** BC31102</span><span class="sxs-lookup"><span data-stu-id="9b402-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9b402-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="9b402-109">To correct this error</span></span>  
  
-   <span data-ttu-id="9b402-110">속성을 정의 하는 소스 코드 제어를 사용 하도록 설정한 경우 선언을 고려는 `Set` 해당 속성과 같은 액세스 수준이 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="9b402-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="9b402-111">속성을 정의 하는 소스 코드 제어 없는 또는 제한 해야 하는 경우는 `Set` 프로시저 액세스 수준 속성 값에 쉽게 액세스할 수 있는 코드의 영역을 설정 하는 문을 이동 하는 속성 자체 보다는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9b402-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b402-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b402-112">See Also</span></span>  
 [<span data-ttu-id="9b402-113">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="9b402-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="9b402-114">방법: 액세스 수준이 혼합된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="9b402-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
