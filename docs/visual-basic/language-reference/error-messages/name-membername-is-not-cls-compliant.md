---
title: "이름 &lt;membername&gt; CLS 규격이 아닙니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ba0dda520e37b27f9b7ad3c214508ee370162598
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a><span data-ttu-id="1f002-102">이름 &lt;membername&gt; CLS 규격이 아닙니다</span><span class="sxs-lookup"><span data-stu-id="1f002-102">Name &lt;membername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="1f002-103">로 어셈블리 표시 되어 `<CLSCompliant(True)>` 밑줄로 시작 하는 이름 가진 멤버를 노출 하지만 (`_`).</span><span class="sxs-lookup"><span data-stu-id="1f002-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="1f002-104">프로그래밍 요소를 준수 해야 하지만 하나 이상의 밑줄을 포함할 수 있습니다는 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS) 시작 하지 않아야 밑줄로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f002-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="1f002-105">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f002-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="1f002-106"><xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1f002-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="1f002-107">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f002-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="1f002-108">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f002-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="1f002-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="1f002-109">By default, this message is a warning.</span></span> <span data-ttu-id="1f002-110">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f002-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="1f002-111">**오류 ID:** BC40031</span><span class="sxs-lookup"><span data-stu-id="1f002-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1f002-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1f002-112">To correct this error</span></span>  
  
-   <span data-ttu-id="1f002-113">소스 코드를 제어할 경우 밑줄로 시작 하지 않는 멤버 이름을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f002-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
-   <span data-ttu-id="1f002-114">멤버 이름은 변경 되지 않고 유지, 필요한 경우 제거 된 <xref:System.CLSCompliantAttribute> 해당 정의에서 표시 하거나 `<CLSCompliant(False)>`합니다.</span><span class="sxs-lookup"><span data-stu-id="1f002-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="1f002-115">어셈블리도 표시할 수 있습니다 `<CLSCompliant(True)>`합니다.</span><span class="sxs-lookup"><span data-stu-id="1f002-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f002-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f002-116">See Also</span></span>  
 [<span data-ttu-id="1f002-117">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="1f002-117">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="1f002-118">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="1f002-118">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  

