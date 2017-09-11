---
title: "&quot;&lt;classname&gt;&quot; CLS 호환 되지 않는다는 인터페이스 &quot;&lt;interfacename&gt;&quot; 그 구현 CLS 규격이 아닙니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40029
- vbc40029
dev_langs:
- VB
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
caps.latest.revision: 13
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
ms.openlocfilehash: d2819bf2dc76291cbaf7ca9215608a11b1a98b3a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="39ltclassnamegt39-is-not-cls-compliant-because-the-interface-39ltinterfacenamegt39-it-implements-is-not-cls-compliant"></a><span data-ttu-id="e99cc-102">'&lt;classname&gt;' CLS 호환 되지 않는다는 인터페이스 '&lt;interfacename&gt;' 그 구현 하는 CLS 규격이 아닙니다</span><span class="sxs-lookup"><span data-stu-id="e99cc-102">&#39;&lt;classname&gt;&#39; is not CLS-compliant because the interface &#39;&lt;interfacename&gt;&#39; it implements is not CLS-compliant</span></span>
<span data-ttu-id="e99cc-103">클래스 또는 인터페이스가 `<CLSCompliant(True)>` 로 표시 또는 표시되지 않은 형식을 구현하거나 해당 형식에서 파생될 때 `<CLSCompliant(False)>` 로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e99cc-103">A class or interface is marked as `<CLSCompliant(True)>` when it derives from or implements a type that is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="e99cc-104">클래스 또는 인터페이스와 호환 되도록는 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) CLS (), 전체 상속 계층 구조 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e99cc-104">For a class or interface to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), its entire inheritance hierarchy must be compliant.</span></span> <span data-ttu-id="e99cc-105">즉, 직접이든 간접이든 상속하는 모든 형식이 규격을 준수해야 한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="e99cc-105">That means every type from which it inherits, directly or indirectly, must be compliant.</span></span> <span data-ttu-id="e99cc-106">마찬가지로 클래스가 하나 이상의 인터페이스를 구현하는 경우 해당 상속 계층 전체가 모두 규격을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e99cc-106">Similarly, if a class implements one or more interfaces, they must all be compliant throughout their inheritance hierarchies.</span></span>  
  
 <span data-ttu-id="e99cc-107">적용 하는 경우는 <xref:System.CLSCompliantAttribute>특성의 프로그래밍 요소에 설정한 `isCompliant` 매개 변수를 `True` 또는 `False` 준수 여부를 나타냅니다.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="e99cc-107">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="e99cc-108">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e99cc-108">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="e99cc-109">적용 되지 않은 경우는 <xref:System.CLSCompliantAttribute>요소에 비호환 상태로 간주 됩니다.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="e99cc-109">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="e99cc-110">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="e99cc-110">By default, this message is a warning.</span></span> <span data-ttu-id="e99cc-111">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e99cc-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e99cc-112">**오류 ID:** BC40029</span><span class="sxs-lookup"><span data-stu-id="e99cc-112">**Error ID:** BC40029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e99cc-113">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e99cc-113">To correct this error</span></span>  
  
-   <span data-ttu-id="e99cc-114">CLS 규격이 필요하면 다른 상속 계층 구조에서 이 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e99cc-114">If you require CLS compliance, define this type within a different inheritance hierarchy or implementation scheme.</span></span>  
  
-   <span data-ttu-id="e99cc-115">제거 해야 합니다.이 형식은 현재 상속 계층 구조 나 구현 체계로 머물러야 하는 경우는 <xref:System.CLSCompliantAttribute>정의에서 표시 하거나 `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="e99cc-115">If you require that this type remain within its current inheritance hierarchy or implementation scheme, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e99cc-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e99cc-116">See Also</span></span>  
 [<span data-ttu-id="e99cc-117">\<통해 PAVE > CLS 규격 코드 작성</span><span class="sxs-lookup"><span data-stu-id="e99cc-117">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
