---
title: "방법: 이름이 같은 변수 숨기기(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af031f3ef134b2a509922e6ada28aa5b2b80d641
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="2f7fb-102">방법: 이름이 같은 변수 숨기기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f7fb-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>
<span data-ttu-id="2f7fb-103">변수를 숨길 수 *섀도잉* 즉, 같은 이름의 변수로 다시 정의 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="2f7fb-104">두 가지 방법으로 숨기려는 변수를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-104">You can shadow the variable you want to hide in two ways:</span></span>  
  
-   <span data-ttu-id="2f7fb-105">**범위를 통한 숨김 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f7fb-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="2f7fb-106">숨기려는 변수가 포함 된 지역의 하위 영역 안에 다시 선언 하 여 범위를 통해 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>  
  
-   <span data-ttu-id="2f7fb-107">**상속을 통한 숨김 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f7fb-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="2f7fb-108">숨기려는 변수가 클래스 수준에서 정의 하는 경우 숨길 수 있습니다 상속을 통해 변수가 [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md) 파생된 클래스에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>  
  
## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="2f7fb-109">두 가지 방법으로 변수를 숨기려면</span><span class="sxs-lookup"><span data-stu-id="2f7fb-109">Two Ways to Hide a Variable</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="2f7fb-110">범위를 통해 여 변수를 숨기려면</span><span class="sxs-lookup"><span data-stu-id="2f7fb-110">To hide a variable by shadowing it through scope</span></span>  
  
1.  <span data-ttu-id="2f7fb-111">숨기려는 변수를 정의 하는 영역을 확인 하 고 사용자의 변수로 다시 정의 하는 하위 영역을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>  
  
    |<span data-ttu-id="2f7fb-112">변수의 영역</span><span class="sxs-lookup"><span data-stu-id="2f7fb-112">Variable's region</span></span>|<span data-ttu-id="2f7fb-113">다시 정의할 수 있는 허용 가능한 부분 영역</span><span class="sxs-lookup"><span data-stu-id="2f7fb-113">Allowable subregion for redefining it</span></span>|  
    |-----------------------|-------------------------------------------|  
    |<span data-ttu-id="2f7fb-114">모듈</span><span class="sxs-lookup"><span data-stu-id="2f7fb-114">Module</span></span>|<span data-ttu-id="2f7fb-115">모듈 내에서 클래스</span><span class="sxs-lookup"><span data-stu-id="2f7fb-115">A class within the module</span></span>|  
    |<span data-ttu-id="2f7fb-116">클래스</span><span class="sxs-lookup"><span data-stu-id="2f7fb-116">Class</span></span>|<span data-ttu-id="2f7fb-117">클래스 내의 하위 클래스</span><span class="sxs-lookup"><span data-stu-id="2f7fb-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="2f7fb-118">클래스 내의 프로시저</span><span class="sxs-lookup"><span data-stu-id="2f7fb-118">A procedure within the class</span></span>|  
  
     <span data-ttu-id="2f7fb-119">예를 들어 해당 프로시저 내에 프로시저 변수를 재정의할 수 없습니다는 `If`... `End If` 생성 또는 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>  
  
2.  <span data-ttu-id="2f7fb-120">아직 없는 경우 하위 영역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-120">Create the subregion if it does not already exist.</span></span>  
  
3.  <span data-ttu-id="2f7fb-121">하위 지역 내에서 작성 한 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 숨기는 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>  
  
     <span data-ttu-id="2f7fb-122">변수 이름에 하위 지역 내에서 코드 참조, 컴파일러를 숨기는 변수에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>  
  
     <span data-ttu-id="2f7fb-123">다음 예제는 숨기기를 무시 하는 참조 뿐만 아니라 범위를 통한 숨김입니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>  
  
    ```  
    Module shadowByScope  
        ' The following statement declares num as a module-level variable.  
        Public num As Integer  
        Sub show()  
            ' The following statement declares num as a local variable.  
            Dim num As Integer  
            ' The following statement sets the value of the local variable.  
            num = 2  
            ' The following statement displays the module-level variable.  
            MsgBox(CStr(shadowByScope.num))  
        End Sub  
        Sub useModuleLevelNum()  
            ' The following statement sets the value of the module-level variable.  
            num = 1  
            show()  
        End Sub  
    End Module  
    ```  
  
     <span data-ttu-id="2f7fb-124">위 예제에서는 변수를 선언 `num` 프로시저 수준 및 모듈 수준 (프로시저에서 `show`).</span><span class="sxs-lookup"><span data-stu-id="2f7fb-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="2f7fb-125">지역 변수 `num` 모듈 수준 변수를 숨깁니다 `num` 내 `show`이므로 지역 변수가 2로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="2f7fb-126">그러나는 그림자 로컬 변수가 없으면 `num` 에 `useModuleLevelNum` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="2f7fb-127">따라서 `useModuleLevelNum` 모듈 수준 변수 값을 1로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>  
  
     <span data-ttu-id="2f7fb-128">`MsgBox` 내부에서 호출 `show` 정규화 하 여 숨김 메커니즘을 우회 `num` 모듈 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="2f7fb-129">따라서 지역 변수 대신 모듈 수준 변수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="2f7fb-130">상속을 통해 하 여 변수를 숨기려면</span><span class="sxs-lookup"><span data-stu-id="2f7fb-130">To hide a variable by shadowing it through inheritance</span></span>  
  
1.  <span data-ttu-id="2f7fb-131">클래스 및 프로시저) (외부 클래스 수준에서 숨기려는 변수가 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="2f7fb-132">그렇지 않으면 상속을 통해 숨길 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-132">Otherwise you cannot shadow it through inheritance.</span></span>  
  
2.  <span data-ttu-id="2f7fb-133">아직 없는 경우 해당 변수의 클래스에서 파생 된 클래스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-133">Define a class derived from the variable's class if one does not already exist.</span></span>  
  
3.  <span data-ttu-id="2f7fb-134">파생된 클래스의 내부 쓰기는 `Dim` 문에 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="2f7fb-135">포함 된 [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md) 키워드를 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="2f7fb-136">변수 이름에도 다른 여러 가지 파생된 클래스에서 코드를 참조 하는 경우 컴파일러에서 사용자 변수에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="2f7fb-137">다음 예제에서는 상속을 통한 숨김</span><span class="sxs-lookup"><span data-stu-id="2f7fb-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="2f7fb-138">예제에서는 두 개의 참조, 숨기는 변수에 액세스 하 고 다른 하나는 숨기기를 무시.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                 vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="2f7fb-139">위 예제에서는 변수를 선언 `shadowString` 기본 클래스에서 파생된 클래스에서이 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="2f7fb-140">프로시저 `showStrings` 파생된 클래스에서 문자열의 숨김 버전을 표시 때 이름 `shadowString` 한정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="2f7fb-141">다음 숨겨진된 버전을 표시 때 `shadowString` 으로 한정 되는 `MyBase` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2f7fb-142">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2f7fb-142">Robust Programming</span></span>  
 <span data-ttu-id="2f7fb-143">섀도잉 동일한 이름 가진 변수 둘 이상의 버전을 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="2f7fb-144">코드 문이 변수 이름에는 참조, 컴파일러 참조를 확인 하는 버전 문 코드의 위치 및 한정 문자열이 있는지 여부 등의 요인에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="2f7fb-145">의도 하지 않은 버전의 숨겨진된 변수에 참조 위험이 높아질 수 있습니다이 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="2f7fb-146">숨겨진된 변수에 대 한 모든 참조를 정규화 하 여 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7fb-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f7fb-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f7fb-147">See Also</span></span>  
 [<span data-ttu-id="2f7fb-148">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="2f7fb-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="2f7fb-149">Visual Basic의 숨김 기능</span><span class="sxs-lookup"><span data-stu-id="2f7fb-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="2f7fb-150">숨기기와 재정의의 차이점</span><span class="sxs-lookup"><span data-stu-id="2f7fb-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [<span data-ttu-id="2f7fb-151">방법: 상속된 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="2f7fb-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [<span data-ttu-id="2f7fb-152">방법: 파생 클래스에 의해 숨겨진 변수에 액세스</span><span class="sxs-lookup"><span data-stu-id="2f7fb-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [<span data-ttu-id="2f7fb-153">재정의</span><span class="sxs-lookup"><span data-stu-id="2f7fb-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="2f7fb-154">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="2f7fb-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="2f7fb-155">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="2f7fb-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
