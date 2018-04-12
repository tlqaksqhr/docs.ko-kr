---
title: '이 &#39;의 첫 번째 문 새 하위 &#39; 명시적으로 호출 &#39; 이어야 합니다. MyBase.New &#39; 또는 &#39; MyClass.New &#39; 때문에 &#39; &lt;constructorname&gt;&#39; 기본 클래스 &#39;&lt; baseclassname&gt;&#39;의 형식이 &#39;&lt; derivedclassname&gt;&#39; 것으로 표시 됩니다: &#39;&lt; errormessage&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8882acd947251d85804fbefd54267ce078e31b95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a><span data-ttu-id="15e5a-102">이 &#39;의 첫 번째 문 새 하위 &#39; 명시적으로 호출 &#39; 이어야 합니다. MyBase.New &#39; 또는 &#39; MyClass.New &#39; 때문에 &#39; &lt;constructorname&gt;&#39; 기본 클래스 &#39;&lt; baseclassname&gt;&#39;의 형식이 &#39;&lt; derivedclassname&gt;&#39; 것으로 표시 됩니다: &#39;&lt; errormessage&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="15e5a-102">First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39;</span></span>
<span data-ttu-id="15e5a-103">클래스 생성자는 기본 클래스 생성자를 명시적으로 호출하지 않으며, 암시적 기본 클래스 생성자가 <xref:System.ObsoleteAttribute> 특성 및 지시문으로 표시되어 오류로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="15e5a-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="15e5a-104">파생 클래스 생성자가 기본 클래스 생성자를 호출하지 않는 경우 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 이 매개 변수가 없는 암시적 기본 클래스 생성자에 대한 암시적 호출을 생성하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="15e5a-104">When a derived class constructor does not call a base class constructor, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="15e5a-105">인수 없이 호출될 수 있는 기본 클래스에 액세스할 수 있는 생성자가 없는 경우 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 은 암시적 호출을 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15e5a-105">If there is no accessible constructor in the base class that can be called without arguments, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot generate an implicit call.</span></span> <span data-ttu-id="15e5a-106">이 경우 필요한 생성자는 <xref:System.ObsoleteAttribute> 특성으로 표시되어 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 이 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15e5a-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot call it.</span></span>  
  
 <span data-ttu-id="15e5a-107">프로그래밍 요소에 <xref:System.ObsoleteAttribute> 를 적용하여 더 이상 사용하지 않는 요소로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15e5a-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="15e5a-108">이렇게 하면 특성의 <xref:System.ObsoleteAttribute.IsError%2A> 속성을 `True` 또는 `False`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15e5a-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="15e5a-109">`True`로 설정하면 컴파일러가 요소를 사용하려는 시도를 오류로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="15e5a-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="15e5a-110">`False`로 설정하거나 기본값인 `False`로 두면 컴파일러가 요소를 사용하려는 시도가 있을 경우 경고를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="15e5a-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="15e5a-111">**오류 ID:** BC30920</span><span class="sxs-lookup"><span data-stu-id="15e5a-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="15e5a-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="15e5a-112">To correct this error</span></span>  
  
1.  <span data-ttu-id="15e5a-113">따옴표 붙은 오류 메시지를 검사하고 적절한 조치를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="15e5a-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2.  <span data-ttu-id="15e5a-114">`MyBase.New()` 또는 `MyClass.New()` 에 대한 호출을 파생 클래스에 `Sub New` 의 첫 번째 문으로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="15e5a-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15e5a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15e5a-115">See Also</span></span>  
 [<span data-ttu-id="15e5a-116">특성 개요</span><span class="sxs-lookup"><span data-stu-id="15e5a-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
