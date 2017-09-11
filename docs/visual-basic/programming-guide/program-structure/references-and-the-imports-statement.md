---
title: "참조 및 Imports 문 (Visual Basic) | Microsoft 문서"
ms.custom: 
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
- assemblies [Visual Basic], namespaces
- references, assembly
- namespaces, assemblies
- referencing assemblies
- Imports statement, referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
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
ms.openlocfilehash: 4c6ce65005f84317c96a1124d609c46734d3cc66
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="2b912-102">참조 및 Imports 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b912-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="2b912-103">사용할 수 있습니다 외부 개체를 프로젝트를 선택 하 여는 **참조 추가** 명령에 **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="2b912-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="2b912-104">참조에 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 같은 형식 라이브러리 하지만 자세한 정보를 포함 하는 어셈블리를 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-104">References in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="2b912-105">Imports 문</span><span class="sxs-lookup"><span data-stu-id="2b912-105">The Imports Statement</span></span>  
 <span data-ttu-id="2b912-106">하나 이상의 네임 스페이스를 포함 하는 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="2b912-107">어셈블리에 대 한 참조를 추가할 때 추가할 수도 있습니다는 `Imports` 모듈 내에서 해당 어셈블리의 네임 스페이스의 가시성을 제어 하는 모듈에는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="2b912-108">`Imports` 문은 고유한 참조를 제공 하는 데 필요한 네임 스페이스의 부분에만 사용할 수 있도록 범위 컨텍스트가 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="2b912-109">`Imports` 문에 다음 구문:</span><span class="sxs-lookup"><span data-stu-id="2b912-109">The `Imports` statement has the following syntax:</span></span>  
  
 <span data-ttu-id="2b912-110">`Imports` [`|``Aliasname` =] `Namespace`</span><span class="sxs-lookup"><span data-stu-id="2b912-110">`Imports` [`|``Aliasname` =] `Namespace`</span></span>  
  
 <span data-ttu-id="2b912-111">`Aliasname`가져온된 네임 스페이스를 참조 하도록 코드 내에서 사용할 수는 짧은 이름으로 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-111">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="2b912-112">`Namespace`네임 스페이스를 통해 사용할 수 있는 프로젝트 참조를 프로젝트 내에서 정의 통해 또는 이전은 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-112">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="2b912-113">모듈에는 개수에 제한 없이 포함 될 수 있습니다 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-113">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="2b912-114">후 나타나야 `Option` 문, 있는 경우 다른 코드 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-114">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b912-115">프로젝트 참조를 혼동 하지 마십시오는 `Imports` 문 또는 `Declare` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-115">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="2b912-116">프로젝트 참조 어셈블리의 개체와 같은 외부 개체를 사용할 수 있도록 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-116">Project references make external objects, such as objects in assemblies, available to [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] projects.</span></span> <span data-ttu-id="2b912-117">`Imports` 문을 프로젝트 참조에 대 한 액세스를 간소화 하 고 있지만 이러한 개체에 대 한 액세스를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-117">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="2b912-118">`Declare` 문을 사용 하는 외부 프로시저 동적 연결 라이브러리 (DLL)에 대 한 참조를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-118">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="2b912-119">Imports 문을 사용 하 여 별칭을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="2b912-119">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="2b912-120">`Imports` 문을 사용 하면 클래스의 메서드에 액세스할 쉽게 명시적으로 참조의 정규화 된 이름을 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-120">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="2b912-121">별칭을 통해 네임 스페이스의 한 부분에 친숙 한 이름을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-121">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="2b912-122">예를 들어, 캐리지 리턴/줄 바꿈 시퀀스는 단일 여러 줄에 표시할 텍스트를 일부인는 <xref:Microsoft.VisualBasic.ControlChars>모듈에는 <xref:Microsoft.VisualBasic?displayProperty=fullName>네임 스페이스.</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.ControlChars></span><span class="sxs-lookup"><span data-stu-id="2b912-122">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="2b912-123">이 상수 별칭 없이 프로그램을 사용 하려면 다음 코드를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-123">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 <span data-ttu-id="2b912-124">[!code-vb[VbVbalrApplication #&3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2b912-124">[!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="2b912-125">`Imports`문은 바로 다음 첫 번째 줄은 반드시 `Option` 모듈의 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-125">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="2b912-126">다음 코드 조각에는 가져오기에 대 한 별칭을 할당 하는 방법을 보여 줍니다는 <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>모듈:</xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2b912-126">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName> module:</span></span>  
  
 <span data-ttu-id="2b912-127">[!code-vb[VbVbalrApplication #&4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2b912-127">[!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]</span></span>  
  
 <span data-ttu-id="2b912-128">이 네임 스페이스에 대 한 향후 참조 상당히 단축 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-128">Future references to this namespace can be considerably shorter:</span></span>  
  
 <span data-ttu-id="2b912-129">[!code-vb[VbVbalrApplication #&5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="2b912-129">[!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]</span></span>  
  
 <span data-ttu-id="2b912-130">하는 경우는 `Imports` 문에 별칭 이름을 지정 하지 않은, 한정자 없이 모듈에는 가져온된 네임 스페이스 내에 정의 된 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-130">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="2b912-131">별칭 이름을 지정 됩니다 해당 네임 스페이스 내에 포함 된 이름에 대 한 한정자로 사용 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b912-131">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b912-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b912-132">See Also</span></span>  
 <span data-ttu-id="2b912-133"><xref:Microsoft.VisualBasic.ControlChars></xref:Microsoft.VisualBasic.ControlChars></span><span class="sxs-lookup"><span data-stu-id="2b912-133"><xref:Microsoft.VisualBasic.ControlChars></span></span>   
 <span data-ttu-id="2b912-134"><xref:Microsoft.VisualBasic></xref:Microsoft.VisualBasic></span><span class="sxs-lookup"><span data-stu-id="2b912-134"><xref:Microsoft.VisualBasic></span></span>   
<span data-ttu-id="2b912-135"> [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span><span class="sxs-lookup"><span data-stu-id="2b912-135"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span></span>  
<span data-ttu-id="2b912-136"> [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="2b912-136"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="2b912-137"> [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b912-137"> [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="2b912-138"> [방법: 명령줄을 사용 하 여 어셈블리 만들기 및 사용](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span><span class="sxs-lookup"><span data-stu-id="2b912-138"> [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span></span>  
<span data-ttu-id="2b912-139"> [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span><span class="sxs-lookup"><span data-stu-id="2b912-139"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span></span>
