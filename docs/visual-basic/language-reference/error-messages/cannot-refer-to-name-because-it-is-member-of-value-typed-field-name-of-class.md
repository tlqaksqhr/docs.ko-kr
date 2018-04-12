---
title: 참조할 수 없습니다. &#39; &lt;이름&gt;&#39; 값 형식 필드 &#39;의 구성원 이므로&lt; 이름&gt;&#39; 클래스 &#39;&lt; classname&gt;&#39; 있는 &#39; System.MarshalByRefObject &#39; 기본 클래스
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a84811b9f0e706cf3ebede09e07c03bd7e4cea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a><span data-ttu-id="66956-102">참조할 수 없습니다. &#39; &lt;이름&gt;&#39; 값 형식 필드 &#39;의 구성원 이므로&lt; 이름&gt;&#39; 클래스 &#39;&lt; classname&gt;&#39; 있는 &#39; System.MarshalByRefObject &#39; 기본 클래스</span><span class="sxs-lookup"><span data-stu-id="66956-102">Cannot refer to &#39;&lt;name&gt;&#39; because it is a member of the value-typed field &#39;&lt;name&gt;&#39; of class &#39;&lt;classname&gt;&#39; which has &#39;System.MarshalByRefObject&#39; as a base class</span></span>
<span data-ttu-id="66956-103">`System.MarshalByRefObject` 클래스를 사용 하면 응용 프로그램 도메인 경계를 넘어 개체에 대 한 원격 액세스를 지 원하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="66956-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="66956-104">형식에서 상속 해야 합니다는 `MarshalByRejectObject` 클래스 응용 프로그램 도메인 경계는 형식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66956-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="66956-105">개체의 멤버는 만든 응용 프로그램 도메인 외부에서 사용할 수 없기 때문에 개체의 상태는 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66956-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="66956-106">**오류 ID:** BC30310</span><span class="sxs-lookup"><span data-stu-id="66956-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="66956-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="66956-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="66956-108">참조 되는 멤버는 사용할 수 있는지 확인에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="66956-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="66956-109">와 함께 멤버를 명시적으로 한정 된 `Me` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="66956-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66956-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66956-110">See Also</span></span>  
 <xref:System.MarshalByRefObject>  
 [<span data-ttu-id="66956-111">Dim 문</span><span class="sxs-lookup"><span data-stu-id="66956-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
