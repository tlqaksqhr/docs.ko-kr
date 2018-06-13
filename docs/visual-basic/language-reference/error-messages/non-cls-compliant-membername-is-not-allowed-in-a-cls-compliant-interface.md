---
title: 비 CLS 규격 &lt;membername&gt; CLS 규격 인터페이스에서는 허용 되지 않습니다
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: ee533df5e06352034b24651b9173a88d090da0a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594148"
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="1f78a-102">비 CLS 규격 &lt;membername&gt; CLS 규격 인터페이스에서는 허용 되지 않습니다</span><span class="sxs-lookup"><span data-stu-id="1f78a-102">Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="1f78a-103">속성, 프로시저 또는 인터페이스의 이벤트로 표시 되어 `<CLSCompliant(True)>` 인터페이스 자체로 표시 되 면 `<CLSCompliant(False)>` 되거나 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f78a-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="1f78a-104">과 호환 되도록 인터페이스는 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS) 모든 해당 멤버 규정을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f78a-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="1f78a-105"><xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1f78a-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="1f78a-106">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f78a-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="1f78a-107">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f78a-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="1f78a-108">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="1f78a-108">By default, this message is a warning.</span></span> <span data-ttu-id="1f78a-109">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f78a-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="1f78a-110">**오류 ID:** BC40033</span><span class="sxs-lookup"><span data-stu-id="1f78a-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1f78a-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1f78a-111">To correct this error</span></span>  
  
-   <span data-ttu-id="1f78a-112">CLS 규격이 필요 하 고 인터페이스의 소스 코드에 대 한 제어 하지 않는 경우 표시할 인터페이스 `<CLSCompliant(True)>` 모든 해당 멤버 호환 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="1f78a-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
-   <span data-ttu-id="1f78a-113">CLS 규격이 필요 하 고 인터페이스의 소스 코드를 제어할 수 없는 경우 또는 규격이 되려면 맞지 않을 경우 다른 인터페이스 내에서이 멤버를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f78a-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
-   <span data-ttu-id="1f78a-114">이 멤버는 현재 인터페이스 내에 유지 하려면, 제거는 <xref:System.CLSCompliantAttribute> 해당 정의에서 표시 하거나 `<CLSCompliant(False)>`합니다.</span><span class="sxs-lookup"><span data-stu-id="1f78a-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f78a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f78a-115">See Also</span></span>  
 [<span data-ttu-id="1f78a-116">Interface 문</span><span class="sxs-lookup"><span data-stu-id="1f78a-116">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 
