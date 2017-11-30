---
title: "방법: 파생 클래스에 의해 숨겨진 변수에 액세스(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f94e45fcb0a26b0d59789e101c37aceba219250
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a><span data-ttu-id="80897-102">방법: 파생 클래스에 의해 숨겨진 변수에 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80897-102">How to: Access a Variable Hidden by a Derived Class (Visual Basic)</span></span>
<span data-ttu-id="80897-103">변수에 액세스 하는 파생된 클래스에서 코드를 컴파일러는 이전 파생 단계의 액세스 하는 클래스에서 액세스할 수 있는 버전 즉, 가장 가까운 액세스할 수 있는 버전에 대 한 참조에 해결 일반적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="80897-103">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span></span> <span data-ttu-id="80897-104">변수를 파생된 클래스에서 정의 하는 경우 코드는 일반적으로 해당 정의 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="80897-104">If the variable is defined in the derived class, the code normally accesses that definition.</span></span>  
  
 <span data-ttu-id="80897-105">파생된 클래스 변수는 기본 클래스의 변수를 숨기면 기본 클래스 버전을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="80897-105">If the derived class variable shadows a variable in the base class, it hides the base class version.</span></span> <span data-ttu-id="80897-106">그러나 기본 클래스 변수를 정규화 하 여 액세스할 수 있습니다는 `MyBase` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="80897-106">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span></span>  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a><span data-ttu-id="80897-107">파생된 클래스에 의해 숨겨진 기본 클래스 변수에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="80897-107">To access a base class variable hidden by a derived class</span></span>  
  
-   <span data-ttu-id="80897-108">식 또는 대입문, 변수 이름 앞에 `MyBase` 키워드와 마침표 (`.`).</span><span class="sxs-lookup"><span data-stu-id="80897-108">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span></span>  
  
     <span data-ttu-id="80897-109">컴파일러는 변수의 기본 클래스 버전에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="80897-109">The compiler resolves the reference to the base class version of the variable.</span></span>  
  
     <span data-ttu-id="80897-110">다음 예제에서는 상속을 통한 숨김</span><span class="sxs-lookup"><span data-stu-id="80897-110">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="80897-111">예제에서는 두 개의 참조, 숨기는 변수에 액세스 하 고 다른 하나는 숨기기를 무시.</span><span class="sxs-lookup"><span data-stu-id="80897-111">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
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
  
     <span data-ttu-id="80897-112">위 예제에서는 변수를 선언 `shadowString` 기본 클래스에서 파생된 클래스에서이 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="80897-112">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="80897-113">프로시저 `showStrings` 파생된 클래스에서 문자열의 숨김 버전을 표시 때 이름 `shadowString` 한정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80897-113">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="80897-114">다음 숨겨진된 버전을 표시 때 `shadowString` 으로 한정 되는 `MyBase` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="80897-114">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="80897-115">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="80897-115">Robust Programming</span></span>  
 <span data-ttu-id="80897-116">위험을 낮추기 위해서는 의도 하지 않은 버전의 숨겨진된 변수에 참조를 완전히 숨겨진된 변수에 대 한 모든 참조를 한정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80897-116">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span></span> <span data-ttu-id="80897-117">섀도잉 동일한 이름 가진 변수 둘 이상의 버전을 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80897-117">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="80897-118">코드 문이 변수 이름에는 참조, 컴파일러 참조를 확인 하는 버전 문 코드의 위치 및 한정 문자열이 있는지 여부 등의 요인에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="80897-118">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="80897-119">잘못 된 버전의 변수를 참조할 위험이 높아질 수 있습니다이 합니다.</span><span class="sxs-lookup"><span data-stu-id="80897-119">This can increase the risk of referring to the wrong version of the variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80897-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80897-120">See Also</span></span>  
 [<span data-ttu-id="80897-121">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="80897-121">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="80897-122">Visual Basic의 숨김 기능</span><span class="sxs-lookup"><span data-stu-id="80897-122">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="80897-123">숨기기와 재정의의 차이점</span><span class="sxs-lookup"><span data-stu-id="80897-123">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [<span data-ttu-id="80897-124">방법: 이름이 같은 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="80897-124">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [<span data-ttu-id="80897-125">방법: 상속된 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="80897-125">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [<span data-ttu-id="80897-126">Shadows</span><span class="sxs-lookup"><span data-stu-id="80897-126">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="80897-127">재정의</span><span class="sxs-lookup"><span data-stu-id="80897-127">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="80897-128">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="80897-128">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="80897-129">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="80897-129">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
