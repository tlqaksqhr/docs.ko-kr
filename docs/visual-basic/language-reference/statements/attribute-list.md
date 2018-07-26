---
title: 특성 목록(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 23f2004a34f5d6dc27c8263f6e66642dd32c6a5f
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936931"
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="eaf14-102">특성 목록(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eaf14-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="eaf14-103">선언 된 프로그래밍 요소에 적용할 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="eaf14-104">여러 특성은 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="eaf14-105">다음은 하나의 특성에 대 한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaf14-106">구문</span><span class="sxs-lookup"><span data-stu-id="eaf14-106">Syntax</span></span>  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="eaf14-107">요소</span><span class="sxs-lookup"><span data-stu-id="eaf14-107">Parts</span></span>  
|||
|---|---|
|`attributemodifier`|<span data-ttu-id="eaf14-108">소스 파일의 시작 부분에 적용 되는 특성에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="eaf14-109">일 수 있습니다 [어셈블리](../../../visual-basic/language-reference/modifiers/assembly.md) 하거나 [모듈](../../../visual-basic/language-reference/modifiers/module-keyword.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>|
|`attributename`| <span data-ttu-id="eaf14-110">필수.</span><span class="sxs-lookup"><span data-stu-id="eaf14-110">Required.</span></span> <span data-ttu-id="eaf14-111">특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-111">Name of the attribute.</span></span>|
|`attributearguments`|<span data-ttu-id="eaf14-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-112">Optional.</span></span> <span data-ttu-id="eaf14-113">이 특성에 대 한 위치 인수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="eaf14-114">여러 인수는 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-114">Multiple arguments are separated by commas.</span></span>|
|`attributeinitializer`|<span data-ttu-id="eaf14-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-115">Optional.</span></span> <span data-ttu-id="eaf14-116">이 특성에 대 한 변수 또는 속성 이니셜라이저 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="eaf14-117">여러 이니셜라이저는 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-117">Multiple initializers are separated by commas.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="eaf14-118">설명</span><span class="sxs-lookup"><span data-stu-id="eaf14-118">Remarks</span></span>  
 <span data-ttu-id="eaf14-119">거의 모든 프로그래밍 요소 (형식, 프로시저, 속성 및 등)에 하나 이상의 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="eaf14-120">특성에 어셈블리의 메타 데이터 표시 및 코드에 주석을 추가 하거나 특정 프로그래밍 요소를 사용 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="eaf14-121">Visual Basic 및.NET Framework에서 정의한 특성을 적용할 수 있습니다 하 고 사용자 지정 특성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="eaf14-122">특성을 사용 하는 경우에 대 한 자세한 내용은 참조 하세요. [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="eaf14-123">특성 이름에 대 한 자세한 내용은 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="eaf14-124">규칙</span><span class="sxs-lookup"><span data-stu-id="eaf14-124">Rules</span></span>  
  
-   <span data-ttu-id="eaf14-125">**배치 합니다.**</span><span class="sxs-lookup"><span data-stu-id="eaf14-125">**Placement.**</span></span> <span data-ttu-id="eaf14-126">대부분의 선언 된 프로그래밍 요소에 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="eaf14-127">하나 이상의 특성을 적용 하려면 배치를 *특성 블록* 요소 선언의 시작 부분에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="eaf14-128">특성 목록에서 각 항목에 적용 하려는 특성 한정자 및 특성의이 호출을 위해 사용 하는 인수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
-   <span data-ttu-id="eaf14-129">**꺾쇠 괄호입니다.**</span><span class="sxs-lookup"><span data-stu-id="eaf14-129">**Angle Brackets.**</span></span> <span data-ttu-id="eaf14-130">특성 목록에서 제공 하는 경우 묶어야 꺾쇠 괄호에서 ("`<`"및"`>`").</span><span class="sxs-lookup"><span data-stu-id="eaf14-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
-   <span data-ttu-id="eaf14-131">**선언의 일부입니다.**</span><span class="sxs-lookup"><span data-stu-id="eaf14-131">**Part of the Declaration.**</span></span> <span data-ttu-id="eaf14-132">특성에는 별도 문이 아닌 요소 선언의 일부 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="eaf14-133">줄 연속 시퀀스를 사용할 수 있습니다 (" `_`") 여러 소스 코드 줄에 선언문을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
-   <span data-ttu-id="eaf14-134">**한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="eaf14-134">**Modifiers.**</span></span> <span data-ttu-id="eaf14-135">특성 한정자 (`Assembly` 또는 `Module`) 소스 파일의 시작 부분에 있는 프로그래밍 요소에 적용 된 모든 특성에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="eaf14-136">특성 한정자 원본 파일의 시작 부분에 없는 요소에 적용 된 특성에 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
-   <span data-ttu-id="eaf14-137">**인수입니다.**</span><span class="sxs-lookup"><span data-stu-id="eaf14-137">**Arguments.**</span></span> <span data-ttu-id="eaf14-138">특성에 대 한 모든 위치 인수에는 모든 변수 또는 속성 이니셜라이저 앞에 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaf14-139">예</span><span class="sxs-lookup"><span data-stu-id="eaf14-139">Example</span></span>  
 <span data-ttu-id="eaf14-140">적용 하는 다음 예제는 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성의 기본 정의 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <span data-ttu-id="eaf14-141"><xref:System.Runtime.InteropServices.DllImportAttribute> 특성 사용된 하는 절차는 관리 되지 않는 동적 연결 라이브러리 (DLL)의 진입점을 나타낸다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-141"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="eaf14-142">특성 위치 인수로 DLL 이름 및 변수 이니셜라이저, 다른 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf14-142">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf14-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eaf14-143">See Also</span></span>  
 [<span data-ttu-id="eaf14-144">어셈블리</span><span class="sxs-lookup"><span data-stu-id="eaf14-144">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [<span data-ttu-id="eaf14-145">모듈 \<키워드></span><span class="sxs-lookup"><span data-stu-id="eaf14-145">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="eaf14-146">특성 개요</span><span class="sxs-lookup"><span data-stu-id="eaf14-146">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="eaf14-147">방법: 코드에서 문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="eaf14-147">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
