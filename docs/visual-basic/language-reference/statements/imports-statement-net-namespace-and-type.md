---
title: Imports 문(.NET 네임스페이스 및 형식)
ms.date: 07/20/2015
f1_keywords:
- vb.Imports
- imports
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
ms.openlocfilehash: ef569b0ed6428d24d019e00c500e4d4b91c83d49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604486"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="56abe-102">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="56abe-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="56abe-103">사용 하도록 설정 이름을 네임 스페이스 한정자 없이 참조할 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56abe-104">구문</span><span class="sxs-lookup"><span data-stu-id="56abe-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="56abe-105">요소</span><span class="sxs-lookup"><span data-stu-id="56abe-105">Parts</span></span>  
  
|<span data-ttu-id="56abe-106">용어</span><span class="sxs-lookup"><span data-stu-id="56abe-106">Term</span></span>|<span data-ttu-id="56abe-107">정의</span><span class="sxs-lookup"><span data-stu-id="56abe-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="56abe-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-108">Optional.</span></span> <span data-ttu-id="56abe-109">*가져오기 별칭* 또는 코드를 참조할 수 있는 이름을 `namespace` 정규화 문자열 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="56abe-110">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="56abe-111">필수.</span><span class="sxs-lookup"><span data-stu-id="56abe-111">Required.</span></span> <span data-ttu-id="56abe-112">가져오고 있는 네임 스페이스의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="56abe-113">중첩 될 수 있습니다는 문자열 네임 스페이스의 모든 수준에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="56abe-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-114">Optional.</span></span> <span data-ttu-id="56abe-115">네임 스페이스에 선언 된 프로그래밍 요소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="56abe-116">컨테이너 요소가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56abe-117">설명</span><span class="sxs-lookup"><span data-stu-id="56abe-117">Remarks</span></span>  
 <span data-ttu-id="56abe-118">`Imports` 문을 직접 참조 하도록 지정된 된 네임 스페이스에 포함 된 형식을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="56abe-119">단일 네임 스페이스 이름 또는 중첩 된 네임 스페이스의 문자열을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="56abe-120">각 중첩 된 네임 스페이스는 마침표로 다음 수준의 네임 스페이스에서 (`.`) 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="56abe-121">각 소스 파일에는 개수에 관계 없이 포함 될 수 있습니다 `Imports` 문.</span><span class="sxs-lookup"><span data-stu-id="56abe-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="56abe-122">이러한 옵션 선언 같은 따라야는 `Option Strict` 문 및 이러한 앞에 야 프로그래밍 요소 선언와 같은 `Module` 또는 `Class` 문.</span><span class="sxs-lookup"><span data-stu-id="56abe-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="56abe-123">사용할 수 있습니다 `Imports` 파일 수준에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="56abe-124">즉, 가져오기에 대 한 선언 컨텍스트는 소스 파일 이어야 하며 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스, 프로시저 또는 블록 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="56abe-125">`Imports` 문으로 하지 요소 만들 다른 프로젝트 및 어셈블리를 프로젝트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="56abe-126">가져오기 설정 대 한 참조를 대신을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="56abe-127">만 이미 프로젝트에 사용할 수 있는 이름을 정규화 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="56abe-128">자세한 내용은 "포함 된 요소 가져오기"를 참조 [선언 된 요소에 대 한 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56abe-129">암시적으로 정의할 수 `Imports` 문에서 사용 하 여는 [참조 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="56abe-130">자세한 내용은 참조 [하는 방법: 추가 또는 제거 (Visual Basic) 가져온 네임 스페이스](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="56abe-131">Import 별칭</span><span class="sxs-lookup"><span data-stu-id="56abe-131">Import Aliases</span></span>  
 <span data-ttu-id="56abe-132">*가져오기 별칭* 네임 스페이스 또는 형식에 대 한 별칭을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="56abe-133">가져오기 별칭은 하나 이상의 네임 스페이스에 선언 되어 있는 동일한 이름의 항목을 사용 해야 할 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="56abe-134">자세한 내용 및 예제에 대 한 "요소 이름 한정"의 참조 [선언 된 요소에 대 한 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="56abe-135">동일한 이름의 모듈 수준에서 멤버를 선언 하지 해야 `aliasname`합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="56abe-136">Visual Basic 컴파일러를 사용 하는 경우 `aliasname` 선언 된 멤버에 대해서만 하 고 더 이상 존재 하지 가져오기 별칭으로 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="56abe-137">그렇게에 XML 네임 스페이스 접두사를 가져오기 위한 가져오기 별칭 선언에 사용 되는 구문을 사용 해도 결과 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="56abe-138">가져오기 별칭은 XML 네임 스페이스 접두사 수 수는 사용 되지만 XML 리터럴 또는 XML 축 속성에만 접두사로 정규화 된 요소 또는 특성 이름에 대 한 코드의 식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="56abe-139">요소 이름</span><span class="sxs-lookup"><span data-stu-id="56abe-139">Element Names</span></span>  
 <span data-ttu-id="56abe-140">제공 하는 경우 `element`를 나타내야 합니다는 *컨테이너 요소*, 다른 요소를 포함할 수 있는 프로그래밍 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="56abe-141">컨테이너 요소에는 클래스, 구조체, 모듈, 인터페이스 및 열거형 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="56abe-142">사용할 수 있도록 하는 요소의 범위는 `Imports` 문의 지정 여부에 따라 달라 집니다 `element`합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="56abe-143">지정 하는 경우 `namespace`, 모든 고유 하 게 해당 네임 스페이스의 멤버와 해당 네임 스페이스 내에서 컨테이너 요소의 멤버 이름이, 한정자 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="56abe-144">모두 지정 하면 `namespace` 및 `element`해당 요소의 멤버 자격 없이 사용할 수 있는 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56abe-145">예제</span><span class="sxs-lookup"><span data-stu-id="56abe-145">Example</span></span>  
 <span data-ttu-id="56abe-146">다음 예제에서는 C:\ 디렉터리에 있는 폴더를 모두 사용 하 여 반환 된 <xref:System.IO.DirectoryInfo> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="56abe-147">코드에 없는 `Imports` 파일 맨 위에 있는 문.</span><span class="sxs-lookup"><span data-stu-id="56abe-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="56abe-148">따라서는 `DirectoryInfo`, <xref:System.Text.StringBuilder>, 및 <xref:Microsoft.VisualBasic.ControlChars.CrLf> 네임 스페이스를 사용 하 여 정규화 된 참조가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="56abe-149">예제</span><span class="sxs-lookup"><span data-stu-id="56abe-149">Example</span></span>  
 <span data-ttu-id="56abe-150">다음 예제에서는 포함 `Imports` 참조 된 네임 스페이스에 대 한 문입니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="56abe-151">따라서 형식 네임 스페이스를 사용 하 여 정규화 될 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]  
  
 [!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="56abe-152">예제</span><span class="sxs-lookup"><span data-stu-id="56abe-152">Example</span></span>  
 <span data-ttu-id="56abe-153">다음 예제에서는 포함 `Imports` 참조 된 네임 스페이스에 대 한 별칭을 사용 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="56abe-154">형식은 별칭으로 한정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]  
  
 [!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="56abe-155">예제</span><span class="sxs-lookup"><span data-stu-id="56abe-155">Example</span></span>  
 <span data-ttu-id="56abe-156">다음 예제에서는 포함 `Imports` 참조 된 형식에 대 한 별칭을 사용 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="56abe-157">별칭은 유형을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56abe-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]  
  
 [!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="56abe-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56abe-158">See Also</span></span>  
 [<span data-ttu-id="56abe-159">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="56abe-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="56abe-160">Visual Basic의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="56abe-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="56abe-161">참조 및 Imports 문</span><span class="sxs-lookup"><span data-stu-id="56abe-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="56abe-162">Imports 문(XML 네임스페이스)</span><span class="sxs-lookup"><span data-stu-id="56abe-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [<span data-ttu-id="56abe-163">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="56abe-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
