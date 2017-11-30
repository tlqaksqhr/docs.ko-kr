---
title: "부분 메서드(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ebedd6f8173e3c349240d24ddaf16e4841f67a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="3da8c-102">부분 메서드(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3da8c-102">Partial Methods (Visual Basic)</span></span>
<span data-ttu-id="3da8c-103">부분 메서드는 개발자가 코드를 사용자 지정 논리를 삽입할 수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-103">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="3da8c-104">일반적으로 코드는 디자이너에서 생성 된 클래스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-104">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="3da8c-105">부분 메서드는 코드 생성기에 의해 만들어진 partial 클래스에 정의 된 하 고 변경 된 내용이 알림을 제공 하 여 일반적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-105">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="3da8c-106">사용 개발자는 변경에 따른에서 사용자 지정 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-106">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="3da8c-107">코드 생성기의 디자이너 메서드 서명과 메서드에 하나 이상의 호출을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-107">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="3da8c-108">그런 다음 개발자는 생성된 된 코드의 동작을 사용자 지정 하는 경우 메서드의 구현을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-108">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="3da8c-109">구현이 제공 되 면 메서드를 호출 하는 컴파일러에 추가적인 성능 오버 헤드 없음 통해 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-109">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="3da8c-110">선언</span><span class="sxs-lookup"><span data-stu-id="3da8c-110">Declaration</span></span>  
 <span data-ttu-id="3da8c-111">키워드를 배치 하 여 부분 메서드의 정의 표시 하는 생성 된 코드 `Partial` 서명 줄의 시작 부분에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-111">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="3da8c-112">정의는 다음 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-112">The definition must meet the following conditions:</span></span>  
  
-   <span data-ttu-id="3da8c-113">메서드는 이어야 합니다는 `Sub`이 아니라는 `Function`합니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-113">The method must be a `Sub`, not a `Function`.</span></span>  
  
-   <span data-ttu-id="3da8c-114">메서드의 본문 비어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-114">The body of the method must be left empty.</span></span>  
  
-   <span data-ttu-id="3da8c-115">액세스 한정자 이어야 합니다. `Private`합니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-115">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="3da8c-116">구현</span><span class="sxs-lookup"><span data-stu-id="3da8c-116">Implementation</span></span>  
 <span data-ttu-id="3da8c-117">구현에서는 주로 채우기로 부분 메서드의 본문에 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-117">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="3da8c-118">구현 정의에서 별도 partial 클래스에는 일반적으로 고 생성된 된 코드를 확장 하려는 개발자가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-118">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="3da8c-119">앞의 예제는 선언의 시그니처를 정확 하 게 복제 되지만 변형이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-119">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="3da8c-120">특히, 다른 한정자를 추가할 수와 같은 `Overloads` 또는 `Overrides`합니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-120">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="3da8c-121">하나의 `Overrides` 한정자는 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-121">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="3da8c-122">메서드 한정자에 대 한 자세한 내용은 참조 [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-122">For more information about method modifiers, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="3da8c-123">기능</span><span class="sxs-lookup"><span data-stu-id="3da8c-123">Use</span></span>  
 <span data-ttu-id="3da8c-124">다른 모든를 호출 하는 것 처럼 부분 메서드를 호출 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-124">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="3da8c-125">메서드 구현 된 경우 인수 평가 되 고 메서드 본문이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-125">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="3da8c-126">그러나 부분 메서드를 구현 하는 선택적 임을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-126">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="3da8c-127">메서드가 구현 되지 않은 경우에이 호출이 아무 효과가 없으며 메서드에 인수로 전달 된 식은 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-127">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3da8c-128">예제</span><span class="sxs-lookup"><span data-stu-id="3da8c-128">Example</span></span>  
 <span data-ttu-id="3da8c-129">Product.Designer.vb 라는 파일에 정의 된 `Product` 가 있는 클래스는 `Quantity` 속성.</span><span class="sxs-lookup"><span data-stu-id="3da8c-129">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 <span data-ttu-id="3da8c-130">Product.vb 라는 파일에 대 한 구현을 제공 `QuantityChanged`합니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-130">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 <span data-ttu-id="3da8c-131">마지막으로, 프로젝트의 Main 메서드를 선언는 `Product` 인스턴스를 초기 값을 제공 합니다. 해당 `Quantity` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-131">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 <span data-ttu-id="3da8c-132">이 메시지를 표시 하는 메시지 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3da8c-132">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="3da8c-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3da8c-133">See Also</span></span>  
 [<span data-ttu-id="3da8c-134">Sub 문</span><span class="sxs-lookup"><span data-stu-id="3da8c-134">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="3da8c-135">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="3da8c-135">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="3da8c-136">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="3da8c-136">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="3da8c-137">부분</span><span class="sxs-lookup"><span data-stu-id="3da8c-137">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [<span data-ttu-id="3da8c-138">LINQ to SQL에서에서 코드 생성</span><span class="sxs-lookup"><span data-stu-id="3da8c-138">Code Generation in LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb399400)  
 [<span data-ttu-id="3da8c-139">부분 메서드를 사용 하 여 비즈니스 논리 추가</span><span class="sxs-lookup"><span data-stu-id="3da8c-139">Adding Business Logic By Using Partial Methods</span></span>](https://msdn.microsoft.com/library/bb546176)
