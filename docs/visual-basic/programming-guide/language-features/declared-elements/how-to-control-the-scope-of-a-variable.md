---
title: "방법: 변수의 범위 제어(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7284d344e3bf0fdd0f900f2a820d6c8db4a4bf74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="f8373-102">방법: 변수의 범위 제어(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8373-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="f8373-103">변수는 일반적으로 *범위*, 또는 참조를 선언 하면 영역 전체에 대 한 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="f8373-104">경우에 따라 변수의 *액세스 수준* 해당 범위에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="f8373-105">자세한 내용은 참조 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-105">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="f8373-106">프로시저 수준 또는 블록 범위</span><span class="sxs-lookup"><span data-stu-id="f8373-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="f8373-107">변수는 블록 내 에서만 볼 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="f8373-107">To make a variable visible only within a block</span></span>  
  
-   <span data-ttu-id="f8373-108">위치는 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 는 시작 하 고 간의 선언문 해당 블록의 예를 들어 종료 사이 변수에 대 한는 `For` 및 `Next` 설명의는 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-108">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="f8373-109">블록 내 에서만 변수를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="f8373-110">변수는 프로시저 내 에서만 볼 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="f8373-110">To make a variable visible only within a procedure</span></span>  
  
-   <span data-ttu-id="f8373-111">위치는 `Dim` 프로시저 내에 있는 블록 외부에서 변수에 대 한 문을 (예:는 `With`... `End With` 블록).</span><span class="sxs-lookup"><span data-stu-id="f8373-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="f8373-112">절차에 포함 된 모든 블록을 포함 하 여 프로시저 내 에서만 변수를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="f8373-113">모듈 또는 Namespace 수준 범위</span><span class="sxs-lookup"><span data-stu-id="f8373-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="f8373-114">편의 위해 제공 되는 단일 용어에 대 한 *모듈 수준* 모듈, 클래스 및 구조체에 동일 하 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="f8373-115">모듈 수준 변수의 액세스 수준은 해당 범위를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="f8373-116">모듈, 클래스 또는 구조체를 포함 하는 네임 스페이스 범위를도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="f8373-117">변수를 전체 모듈, 클래스 또는 구조체에서 볼 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="f8373-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1.  <span data-ttu-id="f8373-118">위치는 `Dim` 프로시저 외부 모듈, 클래스 또는 구조체 내에서 변수에 대 한 문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="f8373-119">포함는 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 키워드는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="f8373-119">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3.  <span data-ttu-id="f8373-120">가 아니라 하지만 모듈, 클래스 또는 구조체 내에서 변수를 참조할 수 밖에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="f8373-121">변수 네임 스페이스 전체에서 볼 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="f8373-121">To make a variable visible throughout a namespace</span></span>  
  
1.  <span data-ttu-id="f8373-122">위치는 `Dim` 프로시저 외부 모듈, 클래스 또는 구조체 내에서 변수에 대 한 문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="f8373-123">포함는 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 또는 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 키워드는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="f8373-123">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3.  <span data-ttu-id="f8373-124">어디에서 나 변수를 참조할 수 모듈, 클래스 또는 구조체를 포함 하는 네임 스페이스 내의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8373-125">예제</span><span class="sxs-lookup"><span data-stu-id="f8373-125">Example</span></span>  
 <span data-ttu-id="f8373-126">다음 예제에서는 모듈 수준에서 변수를 선언 하 고 모듈 내의 코드를 참조할 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="f8373-127">모듈에 정의 된 모든 프로시저 앞의 예제에서 `demonstrateScope` 를 참조할 수는 `String` 변수 `strMsg`합니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="f8373-128">경우는 `usePrivateVariable` 프로시저가 호출을 문자열 변수의 내용을 표시 합니다. `strMsg` 대화 상자에서.</span><span class="sxs-lookup"><span data-stu-id="f8373-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="f8373-129">위의 예제에서는 문자열 변수를 다음과 같이 변경 하면 `strMsg` 선언의 네임 스페이스에 있는 모든 코드에서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="f8373-130">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="f8373-130">Robust Programming</span></span>  
 <span data-ttu-id="f8373-131">실수로 동일한 이름 가진 다른 변수 참조에 대 한 더 적은 기회 변수의 좁을수록 범위</span><span class="sxs-lookup"><span data-stu-id="f8373-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="f8373-132">참조 일치 문제를 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f8373-133">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="f8373-133">.NET Framework Security</span></span>  
 <span data-ttu-id="f8373-134">변수의 범위 좁을수록를 사용 하 여 악성 코드가 부적절 하 게 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="f8373-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8373-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8373-135">See Also</span></span>  
 [<span data-ttu-id="f8373-136">Visual Basic의 범위</span><span class="sxs-lookup"><span data-stu-id="f8373-136">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [<span data-ttu-id="f8373-137">Visual Basic의 수명</span><span class="sxs-lookup"><span data-stu-id="f8373-137">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [<span data-ttu-id="f8373-138">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="f8373-138">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="f8373-139">변수</span><span class="sxs-lookup"><span data-stu-id="f8373-139">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="f8373-140">변수 선언</span><span class="sxs-lookup"><span data-stu-id="f8373-140">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="f8373-141">Dim 문</span><span class="sxs-lookup"><span data-stu-id="f8373-141">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
