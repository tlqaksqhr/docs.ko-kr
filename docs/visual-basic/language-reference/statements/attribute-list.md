---
title: 특성 목록(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 35d031722a5eddd6adce5e32df62b86c500d305b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604076"
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="faf34-102">특성 목록(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="faf34-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="faf34-103">선언된 된 프로그래밍 요소에 적용할 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="faf34-104">여러 특성은 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="faf34-105">다음은 하나의 특성에 대 한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faf34-106">구문</span><span class="sxs-lookup"><span data-stu-id="faf34-106">Syntax</span></span>  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="faf34-107">요소</span><span class="sxs-lookup"><span data-stu-id="faf34-107">Parts</span></span>  
 `attributemodifier`  
 <span data-ttu-id="faf34-108">소스 파일의 시작 부분에 적용 되는 특성에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="faf34-109">수 [어셈블리](../../../visual-basic/language-reference/modifiers/assembly.md) 또는 [모듈](../../../visual-basic/language-reference/modifiers/module-keyword.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>  
  
 `attributename`  
 <span data-ttu-id="faf34-110">필수.</span><span class="sxs-lookup"><span data-stu-id="faf34-110">Required.</span></span> <span data-ttu-id="faf34-111">특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-111">Name of the attribute.</span></span>  
  
 `attributearguments`  
 <span data-ttu-id="faf34-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-112">Optional.</span></span> <span data-ttu-id="faf34-113">이 특성에 대 한 위치 인수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="faf34-114">인수가 여러 개이면 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-114">Multiple arguments are separated by commas.</span></span>  
  
 `attributeinitializer`  
 <span data-ttu-id="faf34-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-115">Optional.</span></span> <span data-ttu-id="faf34-116">이 특성에 대 한 이니셜라이저를 변수 또는 속성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="faf34-117">여러 이니셜라이저는 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-117">Multiple initializers are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faf34-118">설명</span><span class="sxs-lookup"><span data-stu-id="faf34-118">Remarks</span></span>  
 <span data-ttu-id="faf34-119">거의 모든 프로그래밍 요소 (형식, 프로시저, 속성, 등)에 하나 이상의 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="faf34-120">특성은 어셈블리의 메타 데이터에 나타날 있고 수 코드 주석을 추가 하거나 특정 프로그래밍 요소를 사용 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="faf34-121">Visual Basic 및.NET Framework에 정의 된 특성을 적용할 수 있으며 사용자 지정 특성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="faf34-122">특성을 사용 하는 시점에 대 한 자세한 내용은 참조 하십시오. [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="faf34-123">특성 이름에 대 한 자세한 내용은 참조 하십시오. [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="faf34-124">규칙</span><span class="sxs-lookup"><span data-stu-id="faf34-124">Rules</span></span>  
  
-   <span data-ttu-id="faf34-125">**배치 합니다.**</span><span class="sxs-lookup"><span data-stu-id="faf34-125">**Placement.**</span></span> <span data-ttu-id="faf34-126">가장 선언 된 프로그래밍 요소와 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="faf34-127">하나 이상의 특성을 적용 하려면 배치는 *특성 블록* 요소 선언의 시작 부분에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="faf34-128">특성 목록의 각 항목에에서는 한정자를 적용할 특성 및 특성의이 호출을 위해 사용 하는 인수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
-   <span data-ttu-id="faf34-129">**꺾쇠 괄호입니다.**</span><span class="sxs-lookup"><span data-stu-id="faf34-129">**Angle Brackets.**</span></span> <span data-ttu-id="faf34-130">특성 목록을 제공 하는 경우 묶어야 꺾쇠 괄호에서 ("`<`"및"`>`").</span><span class="sxs-lookup"><span data-stu-id="faf34-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
-   <span data-ttu-id="faf34-131">**선언의 일부입니다.**</span><span class="sxs-lookup"><span data-stu-id="faf34-131">**Part of the Declaration.**</span></span> <span data-ttu-id="faf34-132">특성은 별도 문이 요소 선언의 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="faf34-133">줄 연속 시퀀스를 사용할 수 있습니다 (" `_`") 여러 소스 코드 줄에 선언문을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
-   <span data-ttu-id="faf34-134">**한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="faf34-134">**Modifiers.**</span></span> <span data-ttu-id="faf34-135">특성 한정자 (`Assembly` 또는 `Module`) 소스 파일의 시작 부분에 프로그래밍 요소에 적용 된 모든 특성에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="faf34-136">소스 파일의 시작 부분에 없는 요소에 적용 된 특성에 특성 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
-   <span data-ttu-id="faf34-137">**인수입니다.**</span><span class="sxs-lookup"><span data-stu-id="faf34-137">**Arguments.**</span></span> <span data-ttu-id="faf34-138">모든 위치 인수는 특성에 대 한 모든 변수 또는 속성 이니셜라이저가 앞에 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="faf34-139">예제</span><span class="sxs-lookup"><span data-stu-id="faf34-139">Example</span></span>  
 <span data-ttu-id="faf34-140">다음 예제에서는 적용는 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성의 기본 정의에 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <span data-ttu-id="faf34-141"><xref:System.Runtime.InteropServices.DllImportAttribute> 특성 사용된 하는 프로시저는 관리 되지 않는 동적 연결 라이브러리 (DLL)의 진입점을 나타낸다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-141"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="faf34-142">특성에서 DLL 이름으로 위치 인수 및 변수 이니셜라이저로 기타 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="faf34-142">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faf34-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="faf34-143">See Also</span></span>  
 [<span data-ttu-id="faf34-144">어셈블리</span><span class="sxs-lookup"><span data-stu-id="faf34-144">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [<span data-ttu-id="faf34-145">모듈 \<키워드></span><span class="sxs-lookup"><span data-stu-id="faf34-145">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="faf34-146">특성 개요</span><span class="sxs-lookup"><span data-stu-id="faf34-146">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="faf34-147">방법: 코드에서 문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="faf34-147">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
