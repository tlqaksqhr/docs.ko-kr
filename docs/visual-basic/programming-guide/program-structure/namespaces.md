---
title: Visual Basic의 네임스페이스
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.global
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names [Visual Basic], avoiding conflicts
- naming conflicts [Visual Basic], namespaces
- namespaces [Visual Basic], assemblies
- Visual Basic code, namespaces
- fully qualified names [Visual Basic]
- naming conventions [Visual Basic], naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c18d0a9abb1d8b9e3e22f3b81bf605fb8ed75cfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="namespaces-in-visual-basic"></a><span data-ttu-id="f04b7-102">Visual Basic의 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="f04b7-102">Namespaces in Visual Basic</span></span>
<span data-ttu-id="f04b7-103">네임스페이스는 어셈블리에 정의된 개체를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-103">Namespaces organize the objects defined in an assembly.</span></span> <span data-ttu-id="f04b7-104">어셈블리는 여러 네임스페이스를 포함할 수 있으며, 이러한 각 네임스페이스는 다른 네임스페이스를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-104">Assemblies can contain multiple namespaces, which can in turn contain other namespaces.</span></span> <span data-ttu-id="f04b7-105">클래스 라이브러리와 같은 대규모 개체 그룹을 사용할 때 네임스페이스는 모호성을 방지하고 참조를 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-105">Namespaces prevent ambiguity and simplify references when using large groups of objects such as class libraries.</span></span>  
  
 <span data-ttu-id="f04b7-106">예를 들어 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]는 <xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스에서 <xref:System.Windows.Forms.ListBox> 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-106">For example, the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] defines the <xref:System.Windows.Forms.ListBox> class in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="f04b7-107">다음 코드 조각은 이 클래스의 정규화된 이름을 사용하여 변수를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-107">The following code fragment shows how to declare a variable using the fully qualified name for this class:</span></span>  
  
 [!code-vb[VbVbalrApplication#6](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_1.vb)]  
  
## <a name="avoiding-name-collisions"></a><span data-ttu-id="f04b7-108">이름 충돌 방지</span><span class="sxs-lookup"><span data-stu-id="f04b7-108">Avoiding Name Collisions</span></span>  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]<span data-ttu-id="f04b7-109"> 네임스페이스는 클래스 라이브러리의 개발자가 또 다른 라이브러리에서 유사한 이름을 사용하여 방해를 받는 *네임스페이스 공해*라고도 하는 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-109"> namespaces address a problem sometimes called *namespace pollution*, in which the developer of a class library is hampered by the use of similar names in another library.</span></span> <span data-ttu-id="f04b7-110">기존 구성 요소와의 이러한 충돌을 *이름 충돌*이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-110">These conflicts with existing components are sometimes called *name collisions*.</span></span>  
  
 <span data-ttu-id="f04b7-111">예를 들어 `ListBox`라는 새 클래스를 만드는 경우, 프로젝트 내부에서 한정자 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-111">For example, if you create a new class named `ListBox`, you can use it inside your project without qualification.</span></span> <span data-ttu-id="f04b7-112">그러나 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.Windows.Forms.ListBox> 클래스를 같은 프로젝트에서 사용하려는 경우, 참조를 고유하게 지정하기 위해 정규화된 참조를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-112">However, if you want to use the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.Windows.Forms.ListBox> class in the same project, you must use a fully qualified reference to make the reference unique.</span></span> <span data-ttu-id="f04b7-113">참조가 고유하지 않으면 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 에서 이름이 모호하다는 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-113">If the reference is not unique, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] produces an error stating that the name is ambiguous.</span></span> <span data-ttu-id="f04b7-114">다음 코드 예제에서는 이러한 개체를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-114">The following code example demonstrates how to declare these objects:</span></span>  
  
 [!code-vb[VbVbalrApplication#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_2.vb)]  
  
 <span data-ttu-id="f04b7-115">다음 그림에서는 `ListBox`라는 이름의 개체를 포함하는 두 개의 네임스페이스 계층 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-115">The following illustration shows two namespace hierarchies, both containing an object named `ListBox`.</span></span>  
  
 <span data-ttu-id="f04b7-116">![Namespace 계층](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "vaNamespaceHierarchy")</span><span class="sxs-lookup"><span data-stu-id="f04b7-116">![Namespace Hierarchy](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "vaNamespaceHierarchy")</span></span>  
  
 <span data-ttu-id="f04b7-117">기본적으로 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 에서 만드는 모든 실행 파일에는 프로젝트와 이름이 같은 네임스페이스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-117">By default, every executable file you create with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] contains a namespace with the same name as your project.</span></span> <span data-ttu-id="f04b7-118">예를 들어 `ListBoxProject`라는 이름의 프로젝트 내에서 개체를 정의하면 실행 파일 ListBoxProject.exe는 `ListBoxProject`라는 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-118">For example, if you define an object within a project named `ListBoxProject`, the executable file ListBoxProject.exe contains a namespace called `ListBoxProject`.</span></span>  
  
 <span data-ttu-id="f04b7-119">여러 어셈블리에서 동일한 네임스페이스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-119">Multiple assemblies can use the same namespace.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="f04b7-120"> 은 이를 단일 이름 집합으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-120"> treats them as a single set of names.</span></span> <span data-ttu-id="f04b7-121">예를 들어 `SomeNameSpace` 이라는 이름의 어셈블리에서 `Assemb1`라는 네임스페이스에 대한 클래스를 정의하고, `Assemb2`라는 이름의 어셈블리에서 동일한 네임스페이스에 대해 추가 클래스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-121">For example, you can define classes for a namespace called `SomeNameSpace` in an assembly named `Assemb1`, and define additional classes for the same namespace from an assembly named `Assemb2`.</span></span>  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="f04b7-122">정규화된 이름</span><span class="sxs-lookup"><span data-stu-id="f04b7-122">Fully Qualified Names</span></span>  
 <span data-ttu-id="f04b7-123">정규화된 이름은 개체가 정의된 네임스페이스의 이름으로 접두사가 지정된 개체 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-123">Fully qualified names are object references that are prefixed with the name of the namespace in which the object is defined.</span></span> <span data-ttu-id="f04b7-124">클래스에 대한 참조를 만들고( **프로젝트** 메뉴에서 **참조 추가** 선택) 코드에서 개체에 대해 정규화된 이름을 사용하면 다른 프로젝트에 정의된 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-124">You can use objects defined in other projects if you create a reference to the class (by choosing **Add Reference** from the **Project** menu) and then use the fully qualified name for the object in your code.</span></span> <span data-ttu-id="f04b7-125">다음 코드 조각은 다른 프로젝트의 네임스페이스에서 개체에 대해 정규화된 이름을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-125">The following code fragment shows how to use the fully qualified name for an object from another project's namespace:</span></span>  
  
 [!code-vb[VbVbalrApplication#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_3.vb)]  
  
 <span data-ttu-id="f04b7-126">어떤 개체가 사용되고 있는지를 컴파일러가 확인할 수 있도록 해주기 때문에 정규화된 이름은 이름 충돌을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-126">Fully qualified names prevent naming conflicts because they make it possible for the compiler to determine which object is being used.</span></span> <span data-ttu-id="f04b7-127">그러나 이름 자체가 길고 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-127">However, the names themselves can get long and cumbersome.</span></span> <span data-ttu-id="f04b7-128">이를 해결하려면 `Imports` 문을 사용하여 *별칭*을 정의할 수 있습니다. 별칭이란 정규화된 이름 대신 사용할 수 있는 약식 이름을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-128">To get around this, you can use the `Imports` statement to define an *alias*—an abbreviated name you can use in place of a fully qualified name.</span></span> <span data-ttu-id="f04b7-129">예를 들어 다음 코드 예제에서는 정규화된 이름 두 개의 별칭을 만들고 이러한 별칭을 사용하여 두 개체를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-129">For example, the following code example creates aliases for two fully qualified names, and uses these aliases to define two objects.</span></span>  
  
 [!code-vb[VbVbalrApplication#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_4.vb)]  
  
 [!code-vb[VbVbalrApplication#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_5.vb)]  
  
 <span data-ttu-id="f04b7-130">별칭 없이 `Imports` 문을 사용하는 경우, 한정자 없이 해당 네임스페이스의 모든 이름(프로젝트에서 고유하다면)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-130">If you use the `Imports` statement without an alias, you can use all the names in that namespace without qualification, provided they are unique to the project.</span></span> <span data-ttu-id="f04b7-131">같은 이름의 여러 항목을 포함하는 네임스페이스에 대한 `Imports` 문이 프로젝트에 포함된 경우, 반드시 이름을 정규화하여 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-131">If your project contains `Imports` statements for namespaces that contain items with the same name, you must fully qualify that name when you use it.</span></span> <span data-ttu-id="f04b7-132">예를 들어 프로젝트에 다음 두 개의 `Imports` 문이 포함되어 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-132">Suppose, for example, your project contained the following two `Imports` statements:</span></span>  
  
 [!code-vb[VbVbalrApplication#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_6.vb)]  
  
 <span data-ttu-id="f04b7-133">이름을 정규화하지 않고 `Class1` 을 사용하려고 시도하면 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 은 `Class1` 이름이 모호하다는 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-133">If you attempt to use `Class1` without fully qualifying it, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] produces an error stating that the name `Class1` is ambiguous.</span></span>  
  
## <a name="namespace-level-statements"></a><span data-ttu-id="f04b7-134">네임스페이스 수준 문</span><span class="sxs-lookup"><span data-stu-id="f04b7-134">Namespace Level Statements</span></span>  
 <span data-ttu-id="f04b7-135">네임스페이스 내에서 모듈, 인터페이스, 클래스, 대리자, 열거형, 구조체 및 기타 네임스페이스와 같은 항목을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-135">Within a namespace, you can define items such as modules, interfaces, classes, delegates, enumerations, structures, and other namespaces.</span></span> <span data-ttu-id="f04b7-136">네임스페이스 수준에서는 속성, 프로시저, 변수 및 이벤트와 같은 항목을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-136">You cannot define items such as properties, procedures, variables and events at the namespace level.</span></span> <span data-ttu-id="f04b7-137">이러한 항목은 모듈, 구조체 또는 클래스와 같은 컨테이너 내에서 선언되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-137">These items must be declared within containers such as modules, structures, or classes.</span></span>  
  
## <a name="global-keyword-in-fully-qualified-names"></a><span data-ttu-id="f04b7-138">정규화된 이름의 Global 키워드</span><span class="sxs-lookup"><span data-stu-id="f04b7-138">Global Keyword in Fully Qualified Names</span></span>  
 <span data-ttu-id="f04b7-139">네임스페이스의 중첩된 계층 구조를 정의한 경우 해당 계층 구조 내의 코드는 .NET Framework의 <xref:System?displayProperty=nameWithType> 네임스페이스에 액세스하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-139">If you have defined a nested hierarchy of namespaces, code inside that hierarchy might be blocked from accessing the <xref:System?displayProperty=nameWithType> namespace of the .NET Framework.</span></span> <span data-ttu-id="f04b7-140">다음 예제에서는 `SpecialSpace.System` 네임스페이스가 <xref:System?displayProperty=nameWithType>에 대한 액세스를 차단하는 계층 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-140">The following example illustrates a hierarchy in which the `SpecialSpace.System` namespace blocks access to <xref:System?displayProperty=nameWithType>.</span></span>  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As System.Int32  
                Dim n As System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 <span data-ttu-id="f04b7-141">그 결과 Visual Basic 컴파일러는 <xref:System.Int32?displayProperty=nameWithType>에 대한 참조를 성공적으로 해결할 수 없습니다. `SpecialSpace.System`이 `Int32`를 정의하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-141">As a result, the Visual Basic compiler cannot successfully resolve the reference to <xref:System.Int32?displayProperty=nameWithType>, because `SpecialSpace.System` does not define `Int32`.</span></span> <span data-ttu-id="f04b7-142">.NET Framework 클래스 라이브러리의 가장 바깥쪽 수준에서 검증 체인을 시작하려면 `Global` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-142">You can use the `Global` keyword to start the qualification chain at the outermost level of the .NET Framework class library.</span></span> <span data-ttu-id="f04b7-143">이렇게 하면 <xref:System?displayProperty=nameWithType> 네임스페이스 또는 클래스 라이브러리의 다른 네임스페이스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-143">This allows you to specify the <xref:System?displayProperty=nameWithType> namespace or any other namespace in the class library.</span></span> <span data-ttu-id="f04b7-144">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-144">The following example illustrates this.</span></span>  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As Global.System.Int32  
                Dim n As Global.System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 <span data-ttu-id="f04b7-145">`Global`을 사용하면 <xref:Microsoft.VisualBasic?displayProperty=nameWithType> 같은 다른 루트 수준 네임스페이스 및 프로젝트와 관련된 네임스페이스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-145">You can use `Global` to access other root-level namespaces, such as <xref:Microsoft.VisualBasic?displayProperty=nameWithType>, and any namespace associated with your project.</span></span>  
  
## <a name="global-keyword-in-namespace-statements"></a><span data-ttu-id="f04b7-146">네임스페이스 문의 Global 키워드</span><span class="sxs-lookup"><span data-stu-id="f04b7-146">Global Keyword in Namespace Statements</span></span>  
 <span data-ttu-id="f04b7-147">사용할 수도 있습니다는 `Global` 키워드는 [Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-147">You can also use the `Global` keyword in a [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md).</span></span> <span data-ttu-id="f04b7-148">이렇게 하면 프로젝트의 루트 네임스페이스에서 네임스페이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-148">This lets you define a namespace out of the root namespace of your project.</span></span>  
  
 <span data-ttu-id="f04b7-149">프로젝트에서 모든 네임스페이스는 프로젝트에 대한 루트 네임스페이스를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-149">All namespaces in your project are based on the root namespace for the project.</span></span>  <span data-ttu-id="f04b7-150">Visual Studio는 프로젝트 이름을 프로젝트의 모든 코드에 대한 기본 루트 네임스페이스로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-150">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="f04b7-151">예를 들어 프로젝트 이름이 `ConsoleApplication1`이면 해당 프로그래밍 요소는 해당 네임스페이스 `ConsoleApplication1`에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-151">For example, if your project is named `ConsoleApplication1`, its programming elements belong to namespace `ConsoleApplication1`.</span></span> <span data-ttu-id="f04b7-152">`Namespace Magnetosphere`를 선언하는 경우, 프로젝트의 `Magnetosphere` 에 대한 참조는 `ConsoleApplication1.Magnetosphere`에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-152">If you declare `Namespace Magnetosphere`, references to `Magnetosphere` in the project will access `ConsoleApplication1.Magnetosphere`.</span></span>  
  
 <span data-ttu-id="f04b7-153">다음 예제에서는 `Global` 키워드를 사용하여 프로젝트에 대한 루트 네임스페이스에서 네임스페이스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-153">The following examples use the `Global` keyword to declare a namespace out of the root namespace for the project.</span></span>  
  
 [!code-vb[VbVbalrApplication#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_7.vb)]  
  
 <span data-ttu-id="f04b7-154">네임스페이스 선언에서 `Global` 은 다른 네임스페이스에 중첩할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-154">In a namespace declaration, `Global` cannot be nested in another namespace.</span></span>  
  
 <span data-ttu-id="f04b7-155">사용할 수는 [응용 프로그램 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) 확인 및 수정 하는 **루트 Namespace** 프로젝트의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-155">You can use the [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) to view and modify the **Root Namespace** of the project.</span></span>  <span data-ttu-id="f04b7-156">새 프로젝트에서 **루트 네임스페이스** 는 기본적으로 프로젝트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-156">For new projects, the **Root Namespace** defaults to the project name.</span></span> <span data-ttu-id="f04b7-157">`Global` 이 최상위 네임스페이스가 되도록 하려면 **루트 네임스페이스** 항목을 지워 상자를 비울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-157">To cause `Global` to be the top-level namespace, you can clear the **Root Namespace** entry so that the box is empty.</span></span> <span data-ttu-id="f04b7-158">**루트 네임스페이스** 를 지우면 네임스페이스 선언에서 `Global` 키워드가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-158">Clearing **Root Namespace** removes the need for the `Global` keyword in namespace declarations.</span></span>  
  
 <span data-ttu-id="f04b7-159">`Namespace` 문이 .NET Framework에서 역시 네임스페이스인 이름을 선언하면, `Global` 키워드가 정규화된 이름으로 사용되지 않는 경우 .NET Framework 네임스페이스를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-159">If a `Namespace` statement declares a name that is also a namespace in the .NET Framework, the .NET Framework namespace becomes unavailable if the `Global` keyword is not used in a fully qualified name.</span></span> <span data-ttu-id="f04b7-160">`Global` 키워드를 사용하지 않은 채 해당 .NET Framework 네임스페이스에 액세스하려면 `Global` 문에 `Namespace` 키워드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-160">To enable access to that .NET Framework namespace without using the `Global` keyword, you can include the `Global` keyword in the `Namespace` statement.</span></span>  
  
 <span data-ttu-id="f04b7-161">다음 예제에서는 `Global` 네임스페이스 선언에 `System.Text` 키워드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-161">The following example has the `Global` keyword in the `System.Text` namespace declaration.</span></span>  
  
 <span data-ttu-id="f04b7-162">`Global` 키워드가 네임스페이스 선언에 없는 경우 <xref:System.Text.StringBuilder> 를 지정하지 않은 채 `Global.System.Text.StringBuilder`에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-162">If the `Global` keyword was not present in the namespace declaration, <xref:System.Text.StringBuilder> could not be accessed without specifying `Global.System.Text.StringBuilder`.</span></span> <span data-ttu-id="f04b7-163">`ConsoleApplication1`이라는 프로젝트에서는 `System.Text` 키워드가 사용되지 않은 경우 `ConsoleApplication1.System.Text` 에 대한 참조가 `Global` 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b7-163">For a project named `ConsoleApplication1`, references to `System.Text` would access `ConsoleApplication1.System.Text` if the `Global` keyword was not used.</span></span>  
  
 [!code-vb[VbVbalrApplication#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_8.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f04b7-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f04b7-164">See Also</span></span>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
 [<span data-ttu-id="f04b7-165">어셈블리 및 전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="f04b7-165">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="f04b7-166">방법: 명령줄을 사용하여 어셈블리 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="f04b7-166">How to: Create and Use Assemblies Using the Command Line</span></span>](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)  
 [<span data-ttu-id="f04b7-167">참조 및 Imports 문</span><span class="sxs-lookup"><span data-stu-id="f04b7-167">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="f04b7-168">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="f04b7-168">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="f04b7-169">Office 솔루션에서 코드 작성</span><span class="sxs-lookup"><span data-stu-id="f04b7-169">Writing Code in Office Solutions</span></span>](https://msdn.microsoft.com/library/bb608596)
