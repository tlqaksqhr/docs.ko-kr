---
title: "&quot;&lt;elementname&gt;&quot;은 (는) 사용 되지 않습니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40008
- bc40008
dev_langs:
- VB
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
caps.latest.revision: 12
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
ms.openlocfilehash: 77708f052f7aec7a5da2b24605ba3bd794f83979
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a><span data-ttu-id="d8936-102">'&lt;elementname&gt;'은 (는) 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8936-102">&#39;&lt;elementname&gt;&#39; is obsolete (Visual Basic Warning)</span></span>
<span data-ttu-id="d8936-103">문이 있는 것으로 표시 된 프로그래밍 요소에 액세스 하려고 시도 <xref:System.ObsoleteAttribute>특성 및 경고로 처리 하는 지시문.</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="d8936-103">A statement attempts to access a programming element which has been marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as a warning.</span></span>  
  
 <span data-ttu-id="d8936-104">모든 프로그래밍 요소에 <xref:System.ObsoleteAttribute>합니다.</xref:System.ObsoleteAttribute> 적용 하 여 더 이상 사용 중인 것으로 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8936-104">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="d8936-105">이 작업을 수행 하는 경우에 특성을 설정할 수 있습니다 <xref:System.ObsoleteAttribute.IsError%2A>속성을 `True` 또는 `False`.</xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="d8936-105">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="d8936-106">`True`로 설정하면 컴파일러가 요소를 사용하려는 시도를 오류로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d8936-106">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="d8936-107">`False`로 설정하거나 기본값인 `False`로 두면 컴파일러가 요소를 사용하려는 시도가 있을 경우 경고를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d8936-107">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="d8936-108">기본적으로이 메시지는 경고, 때문에 <xref:System.ObsoleteAttribute.IsError%2A>속성 <xref:System.ObsoleteAttribute>는 `False`.</xref:System.ObsoleteAttribute> </xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="d8936-108">By default, this message is a warning, because the <xref:System.ObsoleteAttribute.IsError%2A> property of <xref:System.ObsoleteAttribute> is `False`.</span></span> <span data-ttu-id="d8936-109">경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8936-109">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d8936-110">**오류 ID:** BC40008</span><span class="sxs-lookup"><span data-stu-id="d8936-110">**Error ID:** BC40008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d8936-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d8936-111">To correct this error</span></span>  
  
-   <span data-ttu-id="d8936-112">소스 코드 참조에서 요소 이름의 철자가 맞는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d8936-112">Ensure that the source-code reference is spelling the element name correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8936-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8936-113">See Also</span></span>  
 [<span data-ttu-id="d8936-114">특성 개요</span><span class="sxs-lookup"><span data-stu-id="d8936-114">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

