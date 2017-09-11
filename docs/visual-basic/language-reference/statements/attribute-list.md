---
title: "특성 목록 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: 18
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
ms.sourcegitcommit: dc1c456c71efb3cc6e60a8fdc77384e65975f110
ms.openlocfilehash: 6aea239e2e0d8a266b8eb6ba2876fb109e077c46
ms.contentlocale: ko-kr
ms.lasthandoff: 05/15/2017

---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="c4097-102">특성 목록(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4097-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="c4097-103">선언된 된 프로그래밍 요소에 적용할 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="c4097-104">여러 특성은 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="c4097-105">다음은 하나의 특성에 대 한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4097-106">구문</span><span class="sxs-lookup"><span data-stu-id="c4097-106">Syntax</span></span>  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="c4097-107">요소</span><span class="sxs-lookup"><span data-stu-id="c4097-107">Parts</span></span>  
 `attributemodifier`  
 <span data-ttu-id="c4097-108">소스 파일의 시작 부분에 적용 되는 특성에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="c4097-109">수 [어셈블리](../../../visual-basic/language-reference/modifiers/assembly.md) 또는 [모듈](../../../visual-basic/language-reference/modifiers/module-keyword.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>  
  
 `attributename`  
 <span data-ttu-id="c4097-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="c4097-110">Required.</span></span> <span data-ttu-id="c4097-111">특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-111">Name of the attribute.</span></span>  
  
 `attributearguments`  
 <span data-ttu-id="c4097-112">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="c4097-112">Optional.</span></span> <span data-ttu-id="c4097-113">이 특성에 대 한 인수를 위치 인수 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="c4097-114">인수가 여러 개이면 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-114">Multiple arguments are separated by commas.</span></span>  
  
 `attributeinitializer`  
 <span data-ttu-id="c4097-115">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="c4097-115">Optional.</span></span> <span data-ttu-id="c4097-116">이 특성에 대 한 이니셜라이저를 변수 또는 속성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="c4097-117">여러 이니셜라이저는 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-117">Multiple initializers are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4097-118">설명</span><span class="sxs-lookup"><span data-stu-id="c4097-118">Remarks</span></span>  
 <span data-ttu-id="c4097-119">거의 모든 프로그래밍 요소 (형식, 프로시저, 속성 및 등)에 하나 이상의 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="c4097-120">특성 어셈블리의 메타 데이터에 나타나며 사용자 코드 주석을 추가 하거나 특정 프로그래밍 요소를 사용 하는 방법을 지정 보시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="c4097-121">Visual Basic과.NET Framework에서 정의 된 특성을 적용할 수 및 사용자 지정 특성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="c4097-122">특성을 사용 하는 경우에 대 한 자세한 내용은 참조 하십시오. [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="c4097-123">특성 이름에 대 한 자세한 내용은 참조 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="c4097-124">규칙</span><span class="sxs-lookup"><span data-stu-id="c4097-124">Rules</span></span>  
  
-   <span data-ttu-id="c4097-125">**배치 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c4097-125">**Placement.**</span></span> <span data-ttu-id="c4097-126">프로그래밍 요소와 가장 선언 된 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="c4097-127">하나 이상의 특성을 적용 하려면 배치는 *특성 블록* 요소 선언의 시작 부분에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="c4097-128">특성 목록에 있는 각 항목 한정자를 적용 하려는 특성 및 특성의이 호출을 위해 사용 하는 인수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
-   <span data-ttu-id="c4097-129">**꺾쇠 괄호입니다.**</span><span class="sxs-lookup"><span data-stu-id="c4097-129">**Angle Brackets.**</span></span> <span data-ttu-id="c4097-130">특성 목록을 제공 하는 경우 묶어야 꺾쇠 괄호에서 ("`<`"및"`>`").</span><span class="sxs-lookup"><span data-stu-id="c4097-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
-   <span data-ttu-id="c4097-131">**선언의 일부입니다.**</span><span class="sxs-lookup"><span data-stu-id="c4097-131">**Part of the Declaration.**</span></span> <span data-ttu-id="c4097-132">특성에는 별도 문이 아닌 요소 선언의 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="c4097-133">줄 연속 시퀀스를 사용할 수 있습니다 (" `_`") 여러 소스 코드 줄에 선언문을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
-   <span data-ttu-id="c4097-134">**한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="c4097-134">**Modifiers.**</span></span> <span data-ttu-id="c4097-135">특성 한정자 (`Assembly` 또는 `Module`)는 소스 파일의 시작 부분에 있는 프로그래밍 요소에 적용 된 모든 특성에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="c4097-136">한정자 특성은 소스 파일의 시작 부분에 포함 되지 않는 요소에 적용 된 특성에 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
-   <span data-ttu-id="c4097-137">**인수입니다.**</span><span class="sxs-lookup"><span data-stu-id="c4097-137">**Arguments.**</span></span> <span data-ttu-id="c4097-138">모든 위치 인수는 특성에 대 한 모든 변수 또는 속성 이니셜라이저 앞에 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4097-139">예제</span><span class="sxs-lookup"><span data-stu-id="c4097-139">Example</span></span>  
 <span data-ttu-id="c4097-140">다음 예제에서는 적용는 <xref:System.Runtime.InteropServices.DllImportAttribute>특성의 기본 정의에 `Function` 절차.</xref:System.Runtime.InteropServices.DllImportAttribute></span><span class="sxs-lookup"><span data-stu-id="c4097-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 <span data-ttu-id="c4097-141">[!code-vb[VbVbalrStatements #&1;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c4097-141">[!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]</span></span>  
  
 <span data-ttu-id="c4097-142"><xref:System.Runtime.InteropServices.DllImportAttribute>특성 사용된 하는 절차는 관리 되지 않는 동적 연결 라이브러리 (DLL)의 진입점을 나타낸다는 것을 나타냅니다.</xref:System.Runtime.InteropServices.DllImportAttribute></span><span class="sxs-lookup"><span data-stu-id="c4097-142"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="c4097-143">특성 위치 인수로 DLL 이름과 변수 이니셜라이저, 다른 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c4097-143">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4097-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4097-144">See Also</span></span>  
 <span data-ttu-id="c4097-145">[어셈블리](../../../visual-basic/language-reference/modifiers/assembly.md) </span><span class="sxs-lookup"><span data-stu-id="c4097-145">[Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) </span></span>  
<span data-ttu-id="c4097-146"> [모듈 \<키워드 >](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span><span class="sxs-lookup"><span data-stu-id="c4097-146"> [Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span></span>  
<span data-ttu-id="c4097-147"> [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="c4097-147"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="c4097-148"> [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="c4097-148"> [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span></span>

