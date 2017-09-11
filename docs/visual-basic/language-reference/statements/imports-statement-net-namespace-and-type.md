---
title: "Imports 문 (.NET Namespace 및 형식) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Imports
- imports
dev_langs:
- VB
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
caps.latest.revision: 40
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
ms.openlocfilehash: af177874c3278efd348b53a2b74b4d49d6628c61
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="af48e-102">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="af48e-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="af48e-103">형식 이름을 네임 스페이스 한정자 없이 참조할 수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af48e-104">구문</span><span class="sxs-lookup"><span data-stu-id="af48e-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="af48e-105">요소</span><span class="sxs-lookup"><span data-stu-id="af48e-105">Parts</span></span>  
  
|<span data-ttu-id="af48e-106">용어</span><span class="sxs-lookup"><span data-stu-id="af48e-106">Term</span></span>|<span data-ttu-id="af48e-107">정의</span><span class="sxs-lookup"><span data-stu-id="af48e-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="af48e-108">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="af48e-108">Optional.</span></span> <span data-ttu-id="af48e-109">*가져오기 별칭* 또는 코드를 참조할 수 있는 이름을 `namespace` 정규화 문자열 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="af48e-110">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="af48e-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="af48e-111">Required.</span></span> <span data-ttu-id="af48e-112">가져오고 있는 네임 스페이스의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="af48e-113">중첩 될 수 있습니다 문자열로 네임 스페이스의 모든 수준에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="af48e-114">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="af48e-114">Optional.</span></span> <span data-ttu-id="af48e-115">네임 스페이스에 선언 된 프로그래밍 요소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="af48e-116">모든 컨테이너 요소를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af48e-117">주의</span><span class="sxs-lookup"><span data-stu-id="af48e-117">Remarks</span></span>  
 <span data-ttu-id="af48e-118">`Imports` 문이 지정된 된 네임 스페이스를 직접 참조할 수에 포함 된 형식을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="af48e-119">단일 네임 스페이스 이름 또는 중첩 된 네임 스페이스의 문자열을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="af48e-120">각 중첩 된 네임 스페이스는 마침표로 다음 수준의 네임 스페이스에서 (`.`) 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="af48e-121">각 소스 파일에는 개수에 제한 없이 포함 될 수 있습니다 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="af48e-122">이러한 옵션 선언 같은 따라야는 `Option Strict` 않으며 문 앞에 야 프로그래밍 요소 선언와 같은 `Module` 또는 `Class` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="af48e-123">사용할 수 있습니다 `Imports` 파일 수준에만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="af48e-124">즉, 가져오기에 대 한 선언 컨텍스트는 소스 파일 이어야 하며 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스, 프로시저 또는 차단 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="af48e-125">`Imports` 문을 해도 다른 프로젝트 및 어셈블리에서 요소를 프로젝트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="af48e-126">가져오기 참조 설정 대신을 가지 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="af48e-127">만 이미 프로젝트에 사용할 수 있는 이름을 정규화 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="af48e-128">자세한 내용은 "포함 된 요소를 가져오는"의 참조 [선언 된 요소에 대 한 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af48e-129">암시적으로 정의할 수 `Imports` 문에서 사용 하 여는 [프로젝트 디자이너 (Visual Basic), 참조 페이지](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="af48e-130">자세한 내용은 참조 [하는 방법: 추가 또는 제거 가져온 네임 스페이스 (Visual Basic)](http://msdn.microsoft.com/library/44cebec3-0ea0-47c2-8406-4edeab6a997e)합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](http://msdn.microsoft.com/library/44cebec3-0ea0-47c2-8406-4edeab6a997e).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="af48e-131">Import 별칭</span><span class="sxs-lookup"><span data-stu-id="af48e-131">Import Aliases</span></span>  
 <span data-ttu-id="af48e-132">*가져오기 별칭* 형식 또는 네임 스페이스에 대 한 별칭을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="af48e-133">Import 별칭은 하나 이상의 네임 스페이스에 선언 되어 있는 동일한 이름의 항목을 사용 해야 할 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="af48e-134">자세한 내용 및 예에 "요소 이름 한정" 참조 [선언 된 요소에 대 한 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="af48e-135">동일한 이름의 모듈 수준에서 멤버 선언 하면 안 `aliasname`합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="af48e-136">Visual Basic 컴파일러를 사용 하면 `aliasname` 선언 된 멤버에 대해서만 하 고 더 이상 가져오기 별칭으로 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="af48e-137">XML 네임 스페이스 접두사를 가져오기 위한 가져오기 별칭을 선언 하는 데 사용 되는 구문은 사용 그렇게, 되지만 결과가 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="af48e-138">반면 XML 네임 스페이스 접두사는 사용할 수 XML 리터럴 또는 XML 축 속성에만 접두사로 정규화 된 요소 또는 특성 이름에 대 한 코드에서 식으로 가져오기 별칭을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="af48e-139">요소 이름</span><span class="sxs-lookup"><span data-stu-id="af48e-139">Element Names</span></span>  
 <span data-ttu-id="af48e-140">제공 하는 경우 `element`, 나타내야는 *컨테이너 요소*, 다른 요소를 포함할 수 있는 프로그래밍 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="af48e-141">컨테이너 요소는 클래스, 구조체, 모듈, 인터페이스 및 열거형에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="af48e-142">사용할 수 있도록 하는 요소의 범위는 `Imports` 문을 지정 하는지 여부에 따라 달라 집니다 `element`합니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="af48e-143">만 지정한 경우 `namespace`, 모든 고유 하 게 명명 된 해당 네임 스페이스의 멤버 및 해당 네임 스페이스 내에서 컨테이너 요소의 멤버, 한정자 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="af48e-144">모두 지정 하면 `namespace` 및 `element`만 해당 요소의 멤버를 한정자 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af48e-145">예제</span><span class="sxs-lookup"><span data-stu-id="af48e-145">Example</span></span>  
 <span data-ttu-id="af48e-146">다음 예제에서는 <xref:System.IO.DirectoryInfo>클래스</xref:System.IO.DirectoryInfo> 를 사용 하 여 C:\ 디렉터리에 있는 모든 폴더를 반환</span><span class="sxs-lookup"><span data-stu-id="af48e-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="af48e-147">코드에 없는 `Imports` 파일 맨 위에 있는 문.</span><span class="sxs-lookup"><span data-stu-id="af48e-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="af48e-148">따라서는 `DirectoryInfo`, <xref:System.Text.StringBuilder>, 및 <xref:Microsoft.VisualBasic.ControlChars.CrLf>네임 스페이스를 사용 하 여 정규화 되지 않은 참조는.</xref:Microsoft.VisualBasic.ControlChars.CrLf> </xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="af48e-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 <span data-ttu-id="af48e-149">[!code-vb[VbVbalrStatements #&152;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="af48e-149">[!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="af48e-150">예제</span><span class="sxs-lookup"><span data-stu-id="af48e-150">Example</span></span>  
 <span data-ttu-id="af48e-151">다음 예제에서는 포함 `Imports` 참조 된 네임 스페이스에 대 한 문입니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-151">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="af48e-152">따라서 형식 네임 스페이스를 사용 하 여 정규화 될 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-152">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 <span data-ttu-id="af48e-153">[!code-vb[VbVbalrStatements #&153;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="af48e-153">[!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]</span></span>  
  
 <span data-ttu-id="af48e-154">[!code-vb[VbVbalrStatements #&154;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="af48e-154">[!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="af48e-155">예제</span><span class="sxs-lookup"><span data-stu-id="af48e-155">Example</span></span>  
 <span data-ttu-id="af48e-156">다음 예제에서는 포함 `Imports` 참조 된 네임 스페이스에 대 한 별칭을 사용 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-156">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="af48e-157">형식은 별칭으로 한정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-157">The types are qualified with the aliases.</span></span>  
  
 <span data-ttu-id="af48e-158">[!code-vb[VbVbalrStatements #&155;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="af48e-158">[!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]</span></span>  
  
 <span data-ttu-id="af48e-159">[!code-vb[VbVbalrStatements #&156;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="af48e-159">[!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="af48e-160">예제</span><span class="sxs-lookup"><span data-stu-id="af48e-160">Example</span></span>  
 <span data-ttu-id="af48e-161">다음 예제에서는 포함 `Imports` 참조 된 형식에 대 한 별칭을 사용 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-161">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="af48e-162">별칭은 형식을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af48e-162">Aliases are used to specify the types.</span></span>  
  
 <span data-ttu-id="af48e-163">[!code-vb[VbVbalrStatements #&157;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="af48e-163">[!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]</span></span>  
  
 <span data-ttu-id="af48e-164">[!code-vb[VbVbalrStatements #&158;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="af48e-164">[!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af48e-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af48e-165">See Also</span></span>  
 <span data-ttu-id="af48e-166">[Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md) </span><span class="sxs-lookup"><span data-stu-id="af48e-166">[Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) </span></span>  
<span data-ttu-id="af48e-167"> [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="af48e-167"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="af48e-168"> [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="af48e-168"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="af48e-169"> [Imports 문 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="af48e-169"> [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="af48e-170"> [선언된 요소 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="af48e-170"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>
