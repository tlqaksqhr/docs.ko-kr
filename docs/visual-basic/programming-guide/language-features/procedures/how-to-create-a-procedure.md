---
title: '방법: 프로시저 만들기(Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5e23358e26dbc993b0f9290a8491a3c66717b4c6
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="3ff9c-102">방법: 프로시저 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ff9c-102">How to: Create a Procedure (Visual Basic)</span></span>
<span data-ttu-id="3ff9c-103">선언문의 시작 사이 프로시저를 묶습니다 (`Sub` 또는 `Function`) 및 선언문의 끝 (`End Sub` 또는 `End Function`).</span><span class="sxs-lookup"><span data-stu-id="3ff9c-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="3ff9c-104">프로시저의 모든 코드이 문 사이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-104">All the procedure's code lies between these statements.</span></span>  
  
 <span data-ttu-id="3ff9c-105">프로시저의 시작 및 끝 문은 다른 프로시저 밖에 서 있어야 하므로 다른 프로시저를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>  
  
 <span data-ttu-id="3ff9c-106">서로 다른 위치에서 동일한 작업을 수행 하는 코드를 있는 경우 절차로 한 번 작업 쓰고 코드에서 다른 위치에서 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="3ff9c-107">값을 반환 하지 않는 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="3ff9c-107">To create a procedure that does not return a value</span></span>  
  
1.  <span data-ttu-id="3ff9c-108">다른 프로시저 밖에 서 사용 하 여 한 `Sub` 문 다음에 `End Sub` 문.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="3ff9c-109">에 `Sub` 문을 수행는 `Sub` 키워드와 프로시저를 지정한 다음 매개 변수 목록을 괄호로 이름 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="3ff9c-110">프로시저의 코드 문을 사이 `Sub` 및 `End Sub` 문.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="3ff9c-111">값을 반환 하는 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="3ff9c-111">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="3ff9c-112">다른 프로시저 밖에 서 사용 하 여 한 `Function` 문 다음에 `End Function` 문.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="3ff9c-113">에 `Function` 문을 수행는 `Function` 키워드와 프로시저를 지정한 다음 매개 변수 목록을 괄호로 이름 차례로 `As` 반환 값의 데이터 형식을 지정 하는 절.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>  
  
3.  <span data-ttu-id="3ff9c-114">프로시저의 코드 문을 사이 `Function` 및 `End Function` 문.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
4.  <span data-ttu-id="3ff9c-115">사용 하 여 한 `Return` 호출 코드에 값을 반환 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-115">Use a `Return` statement to return the value to the calling code.</span></span>  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="3ff9c-116">오래 되 고 반복적인 코드 블록을 사용 하 여 새 프로시저를 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="3ff9c-116">To connect your new procedure with the old, repetitive blocks of code</span></span>  
  
1.  <span data-ttu-id="3ff9c-117">이전 코드에 액세스할 수 있는 위치에서 새 프로시저를 정의 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>  
  
2.  <span data-ttu-id="3ff9c-118">이전 반복 코드 블록을 호출 하는 단일 문 반복적인 작업을 수행 하는 문을 바꿉니다는 `Sub` 또는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>  
  
3.  <span data-ttu-id="3ff9c-119">프로시저가 `Function` 값을 반환 하는, 하도록 하는 변수에 저장 하는 등의 반환된 값과 함께 동작을 수행 하는 호출 문에서 값이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ff9c-120">예제</span><span class="sxs-lookup"><span data-stu-id="3ff9c-120">Example</span></span>  
 <span data-ttu-id="3ff9c-121">다음 `Function` 프로시저 가장 긴 면 또는 다른 두 변에 대 한 값을 지정 하는 직각 삼각형의 빗변을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff9c-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3ff9c-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="3ff9c-122">See also</span></span>

 [<span data-ttu-id="3ff9c-123">절차</span><span class="sxs-lookup"><span data-stu-id="3ff9c-123">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="3ff9c-124">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="3ff9c-124">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="3ff9c-125">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="3ff9c-125">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="3ff9c-126">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="3ff9c-126">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="3ff9c-127">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="3ff9c-127">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="3ff9c-128">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="3ff9c-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="3ff9c-129">재귀 프로시저</span><span class="sxs-lookup"><span data-stu-id="3ff9c-129">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="3ff9c-130">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="3ff9c-130">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="3ff9c-131">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="3ff9c-131">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="3ff9c-132">개체 지향 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ff9c-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)  
