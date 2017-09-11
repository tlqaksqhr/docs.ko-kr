---
title: "대리자 클래스&lt;classname&gt;&quot;에 Invoke 메서드가 있으므로 이러한 종류의 식을 메서드 호출의 대상일 수 없습니다 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
dev_langs:
- VB
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 10
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
ms.openlocfilehash: 54cd62bc2b4cafa89873728ba4e5b31c46f1aab1
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="11727-102">대리자 클래스&lt;classname&gt;'에 Invoke 메서드가 있으므로 이러한 종류의 식을 메서드 호출의 대상일 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="11727-102">Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="11727-103">에 대 한 호출 `Invoke` 때문에 실패 했습니다 대리자를 통해 `Invoke` 대리자 클래스에서 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="11727-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="11727-104">**오류 ID:** BC30220</span><span class="sxs-lookup"><span data-stu-id="11727-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="11727-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="11727-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="11727-106">대리자 클래스의 인스턴스는으로 만들어졌는지 확인 한 `Dim` 문과 사용 하 여 대리자 인스턴스에 프로시저를 할당 되어 있는지는 `AddressOf` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="11727-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="11727-107">대리자 클래스를 구현 하는 코드를 찾아 구현 하는지 확인은 `Invoke` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="11727-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11727-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11727-108">See Also</span></span>  
 <span data-ttu-id="11727-109">[대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="11727-109">[Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="11727-110"> [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="11727-110"> [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="11727-111"> [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="11727-111"> [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="11727-112"> [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="11727-112"> [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>
