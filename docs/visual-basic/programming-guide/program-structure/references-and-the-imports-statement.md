---
title: 참조 및 Imports 문(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: d767f42f8c836995064623b4aca15c86c98ec643
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651852"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="2d609-102">참조 및 Imports 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d609-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="2d609-103">있습니다 수 외부 개체에 사용할 프로젝트를 선택 하 여는 **참조 추가** 명령을 **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="2d609-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="2d609-104">Visual Basic의 형식 라이브러리 하지만 더 많은 정보를 포함 하는 like는 어셈블리를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="2d609-105">Imports 문</span><span class="sxs-lookup"><span data-stu-id="2d609-105">The Imports Statement</span></span>  
 <span data-ttu-id="2d609-106">어셈블리가 하나 이상의 네임 스페이스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="2d609-107">어셈블리에 대 한 참조를 추가할 때 추가할 수도 있습니다는 `Imports` 문이 모듈 내에서 해당 어셈블리의 네임 스페이스의 표시 유형을 제어 하는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="2d609-108">`Imports` 문을 하면 고유한 참조를 제공 하는 데 필요한 네임 스페이스의 일부분만 사용할 수 있도록 범위를 지정 하도록 컨텍스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="2d609-109">`Imports` 문의 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-109">The `Imports` statement has the following syntax:</span></span>  
  
 <span data-ttu-id="2d609-110">`Imports` [`|``Aliasname` =] `Namespace`</span><span class="sxs-lookup"><span data-stu-id="2d609-110">`Imports` [`|``Aliasname` =] `Namespace`</span></span>  
  
 <span data-ttu-id="2d609-111">`Aliasname` 가져온된 네임 스페이스를 참조 하도록 코드 내에서 사용할 수는 짧은 이름을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-111">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="2d609-112">`Namespace` 네임 스페이스 중 하나를 통해 사용할 수 있는 프로젝트 참조를 프로젝트에서 정의 통해 또는 이전 `Imports` 문.</span><span class="sxs-lookup"><span data-stu-id="2d609-112">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="2d609-113">모듈에는 개수에 관계 없이 포함 될 수 있습니다 `Imports` 문.</span><span class="sxs-lookup"><span data-stu-id="2d609-113">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="2d609-114">뒤에 나와야 `Option` 문, 있는 경우 다른 코드 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-114">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d609-115">프로젝트 참조를 혼동 하지 마십시오는 `Imports` 문 또는 `Declare` 문.</span><span class="sxs-lookup"><span data-stu-id="2d609-115">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="2d609-116">프로젝트 참조 어셈블리에는 개체와 같은 외부 개체를 Visual Basic 프로젝트를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-116">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="2d609-117">`Imports` 문을 프로젝트 참조에 대 한 액세스를 단순화 하는 데 사용 하지만 이러한 개체에 대 한 액세스를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-117">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="2d609-118">`Declare` 문을 사용 하는 동적 연결 라이브러리 (DLL)에 외부 프로시저에 대 한 참조를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-118">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="2d609-119">Imports 문을 사용 하 여 별칭을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="2d609-119">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="2d609-120">`Imports` 문을 사용 하면 클래스의 메서드에 대 한 액세스를 보다 쉽게 참조의 정규화 된 이름을 명시적으로 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-120">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="2d609-121">별칭을 통해 네임 스페이스의 한 부분에 친숙 한 이름을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-121">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="2d609-122">캐리지 리턴/줄 바꿈는 단일 여러 줄에 표시할 텍스트를 시퀀스의 일부인 예를 들어는 <xref:Microsoft.VisualBasic.ControlChars> 모듈에는 <xref:Microsoft.VisualBasic?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-122">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="2d609-123">이 상수 별칭 없이 프로그램을 사용 하려면 다음 코드를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-123">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 <span data-ttu-id="2d609-124">`Imports` 문은 바로 다음 첫 번째 줄은 반드시 `Option` 모듈의 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-124">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="2d609-125">다음 코드 조각에 가져와서에 대 한 별칭을 할당 하는 방법을 보여 줍니다는 <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> 모듈:</span><span class="sxs-lookup"><span data-stu-id="2d609-125">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 <span data-ttu-id="2d609-126">이 네임 스페이스에 대 한 참조가 상당히 단축 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-126">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 <span data-ttu-id="2d609-127">경우는 `Imports` 문에 별칭 이름을 지정 하지 않은, 한정 하지 않고 모듈에서 가져온된 네임 스페이스 내에서 정의 된 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-127">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="2d609-128">별칭 이름을 지정 하는 경우 해당 네임 스페이스 내에 포함 된 이름에 대 한 한정자로 사용 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d609-128">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d609-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d609-129">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ControlChars>  
 <xref:Microsoft.VisualBasic>  
   
 [<span data-ttu-id="2d609-130">Visual Basic의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="2d609-130">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="2d609-131">어셈블리 및 전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="2d609-131">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="2d609-132">방법: 명령줄을 사용하여 어셈블리 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="2d609-132">How to: Create and Use Assemblies Using the Command Line</span></span>](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)  
 [<span data-ttu-id="2d609-133">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="2d609-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
