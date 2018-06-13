---
title: '&#39;&lt;elementname&gt; &#39; 가 사용 되지 않습니다 (Visual Basic 경고)'
ms.date: 07/20/2015
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
ms.openlocfilehash: 4dc2d0b8eace9bc411a344b4f2c4c79f7e09ac22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586772"
---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a><span data-ttu-id="81b74-102">&#39;&lt;elementname&gt; &#39; 가 사용 되지 않습니다 (Visual Basic 경고)</span><span class="sxs-lookup"><span data-stu-id="81b74-102">&#39;&lt;elementname&gt;&#39; is obsolete (Visual Basic Warning)</span></span>
<span data-ttu-id="81b74-103">문에서 경고로 처리하는 <xref:System.ObsoleteAttribute> 특성 및 지시문으로 표시된 프로그래밍 요소에 액세스하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="81b74-103">A statement attempts to access a programming element which has been marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as a warning.</span></span>  
  
 <span data-ttu-id="81b74-104">프로그래밍 요소에 <xref:System.ObsoleteAttribute> 를 적용하여 더 이상 사용하지 않는 요소로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b74-104">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="81b74-105">이렇게 하면 특성의 <xref:System.ObsoleteAttribute.IsError%2A> 속성을 `True` 또는 `False`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b74-105">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="81b74-106">`True`로 설정하면 컴파일러가 요소를 사용하려는 시도를 오류로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="81b74-106">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="81b74-107">`False`로 설정하거나 기본값인 `False`로 두면 컴파일러가 요소를 사용하려는 시도가 있을 경우 경고를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="81b74-107">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="81b74-108"><xref:System.ObsoleteAttribute.IsError%2A> 의 <xref:System.ObsoleteAttribute> 속성이 `False`이므로 이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="81b74-108">By default, this message is a warning, because the <xref:System.ObsoleteAttribute.IsError%2A> property of <xref:System.ObsoleteAttribute> is `False`.</span></span> <span data-ttu-id="81b74-109">경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="81b74-109">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="81b74-110">**오류 ID:** BC40008</span><span class="sxs-lookup"><span data-stu-id="81b74-110">**Error ID:** BC40008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="81b74-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="81b74-111">To correct this error</span></span>  
  
-   <span data-ttu-id="81b74-112">소스 코드 참조에서 요소 이름의 철자가 맞는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="81b74-112">Ensure that the source-code reference is spelling the element name correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b74-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81b74-113">See Also</span></span>  
 [<span data-ttu-id="81b74-114">특성 개요</span><span class="sxs-lookup"><span data-stu-id="81b74-114">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
