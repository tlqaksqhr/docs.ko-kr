---
title: '방법: 새 변수 만들기(Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aff160584d3d1fe382020d5b8c25ac57dab66d92
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="74435-102">방법: 새 변수 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74435-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="74435-103">변수를 만들는 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="74435-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="74435-104">새 변수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="74435-104">To create a new variable</span></span>  
  
1.  <span data-ttu-id="74435-105">변수를 선언 하는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="74435-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  <span data-ttu-id="74435-106">같은 변수 특징에 대 한 사양이 포함 [개인](../../../../visual-basic/language-reference/modifiers/private.md), [정적](../../../../visual-basic/language-reference/modifiers/static.md), [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md), 또는 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="74435-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="74435-107">자세한 내용은 참조 [선언 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="74435-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="74435-108">필요 하지 않습니다는 `Dim` 키워드는 선언에서 다른 키워드를 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="74435-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3.  <span data-ttu-id="74435-109">Visual Basic 규칙 및 규칙을 따라야 하는 변수 이름의 사양을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="74435-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="74435-110">자세한 내용은 참조 [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="74435-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  <span data-ttu-id="74435-111">이름 뒤에 [으로](../../../../visual-basic/language-reference/statements/as-clause.md) 절 변수의 데이터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74435-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="74435-112">데이터 형식을 지정 하지 않으면 기본 사용: `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="74435-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5.  <span data-ttu-id="74435-113">에 따라는 `As` 등호로 절 (`=`) 등호 변수의 초기 값을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="74435-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     <span data-ttu-id="74435-114">Visual Basic 실행 될 때마다 변수에 지정된 된 값을 할당는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="74435-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="74435-115">초기 값을 지정 하지 않는 경우 Visual Basic 코드가 포함 된 처음 실행 하는 경우 변수의 데이터 형식에 대 한 기본 초기 값을 할당 하는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="74435-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="74435-116">변수 참조 형식인 경우를 포함 하 여 해당 클래스의 인스턴스를 만들 수 있습니다는 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md) 키워드는 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="74435-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="74435-117">사용 하지 않는 경우 `New`, 변수의 초기 값은 [Nothing](../../../../visual-basic/language-reference/nothing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="74435-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="74435-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74435-118">See Also</span></span>  
 [<span data-ttu-id="74435-119">변수</span><span class="sxs-lookup"><span data-stu-id="74435-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="74435-120">변수 선언</span><span class="sxs-lookup"><span data-stu-id="74435-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="74435-121">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="74435-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="74435-122">선언 요소의 특징</span><span class="sxs-lookup"><span data-stu-id="74435-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="74435-123">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="74435-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="74435-124">문</span><span class="sxs-lookup"><span data-stu-id="74435-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)  
 [<span data-ttu-id="74435-125">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="74435-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="74435-126">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="74435-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
