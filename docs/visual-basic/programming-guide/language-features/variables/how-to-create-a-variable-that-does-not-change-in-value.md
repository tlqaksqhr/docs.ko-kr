---
title: "방법: 값이 변경되지 않는 변수 만들기(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1475553e64fef92ec3f3bb7e1b4fbfb357dbec8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="fe64c-102">방법: 값이 변경되지 않는 변수 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe64c-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>
<span data-ttu-id="fe64c-103">해당 값이 변경 되지 않는 변수 개념 모순 되 게 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="fe64c-104">하지만 상황이 발생 하는 상수 작업이 불가능 하 고 변수 고정된 값을 사용 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="fe64c-105">이러한 경우에 사용 하 여 멤버 변수를 정의할 수 있습니다는 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-105">In such a case you can define a member variable with the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
 <span data-ttu-id="fe64c-106">사용할 수 없습니다는 [Const 문을](../../../../visual-basic/language-reference/statements/const-statement.md) 선언 하 고 다음과 같은 경우 상수 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-106">You cannot use the [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>  
  
-   <span data-ttu-id="fe64c-107">`Const` 문에서 사용 하려는 데이터 형식을 허용 하지 않는</span><span class="sxs-lookup"><span data-stu-id="fe64c-107">The `Const` statement does not accept the data type you want to use</span></span>  
  
-   <span data-ttu-id="fe64c-108">컴파일 타임에 값을 알지 못합니다</span><span class="sxs-lookup"><span data-stu-id="fe64c-108">You do not know the value at compile time</span></span>  
  
-   <span data-ttu-id="fe64c-109">컴파일 타임에 상수 값을 계산할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="fe64c-109">You are unable to compute the constant value at compile time</span></span>  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="fe64c-110">값에서 변경 되지 않는 변수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="fe64c-110">To create a variable that does not change in value</span></span>  
  
1.  <span data-ttu-id="fe64c-111">모듈 수준에서 멤버 변수를 선언에서 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md), 포함 하 고는 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-111">At module level, declare a member variable with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     <span data-ttu-id="fe64c-112">지정할 수 있습니다 `ReadOnly` 멤버 변수에 대해서만 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="fe64c-113">즉, 기존 프로시저 외부의 모듈 수준에서 변수를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-113">This means you must define the variable at module level, outside of any procedure.</span></span>  
  
2.  <span data-ttu-id="fe64c-114">컴파일 타임에 하나의 문에서 값을 계산할 수 있으면에 초기화 절을 사용 합니다.는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="fe64c-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="fe64c-115">에 따라는 [으로](../../../../visual-basic/language-reference/statements/as-clause.md) 등호로 절 (`=`) 식 옵니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-115">Follow the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="fe64c-116">컴파일러에는 상수 값이 식을 계산할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     <span data-ttu-id="fe64c-117">값을 할당할 수는 `ReadOnly` 변수 한 번만 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="fe64c-118">이렇게 하면 코드가 해당 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-118">Once you do so, no code can ever change its value.</span></span>  
  
     <span data-ttu-id="fe64c-119">컴파일 타임에 값을 알지 못하는 하거나 단일 문에서 컴파일 타임에 계산할 수 없는 경우에 생성자에서 런타임 시 여전히 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="fe64c-120">이 작업을 수행 하려면 해당 선언 해야는 `ReadOnly` 클래스 또는 구조 수준에서 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="fe64c-121">해당 클래스 또는 구조체에 대 한 생성자에서 변수의 고정된 값을 계산 하 고 생성자에서 반환 하기 전에를 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe64c-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe64c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe64c-122">See Also</span></span>  
 [<span data-ttu-id="fe64c-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="fe64c-123">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [<span data-ttu-id="fe64c-124">Const 문</span><span class="sxs-lookup"><span data-stu-id="fe64c-124">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
