---
title: "수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab108d064f5c6740f80328a9b6db4785334550ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="608bd-102">수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="608bd-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="608bd-103">프로시저를 호출 하는 경우 일반적으로에 하나 이상의 인수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="608bd-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="608bd-104">각 인수는 기본 프로그래밍 요소에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="608bd-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="608bd-105">기본 요소와 인수 자체 수정 가능 하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="608bd-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="608bd-106">수정할 수 있는 인수와 수정할 수 없는 요소</span><span class="sxs-lookup"><span data-stu-id="608bd-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="608bd-107">프로그래밍 요소는 일 수 있습니다는 *수정할 수 있는 요소*, 변경, 해당 값을 사용할 수 있는 또는 *수정할 수 없는 요소*에 고정된 값이 있는 만들어진 후 합니다.</span><span class="sxs-lookup"><span data-stu-id="608bd-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="608bd-108">다음 표에서 수정할 수 있는 인수와 수정할 수 없는 프로그래밍 요소를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="608bd-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="608bd-109">수정할 수 있는 요소</span><span class="sxs-lookup"><span data-stu-id="608bd-109">Modifiable elements</span></span>|<span data-ttu-id="608bd-110">수정할 수 없는 요소</span><span class="sxs-lookup"><span data-stu-id="608bd-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="608bd-111">지역 변수 (프로시저 내에 선언 됨), 읽기 전용 제외 개체 변수를 포함 하 여</span><span class="sxs-lookup"><span data-stu-id="608bd-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="608bd-112">읽기 전용 변수, 필드 및 속성</span><span class="sxs-lookup"><span data-stu-id="608bd-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="608bd-113">읽기 전용 제외 필드 (모듈, 클래스 및 구조체의 멤버 변수)</span><span class="sxs-lookup"><span data-stu-id="608bd-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="608bd-114">상수 및 리터럴</span><span class="sxs-lookup"><span data-stu-id="608bd-114">Constants and literals</span></span>|  
|<span data-ttu-id="608bd-115">읽기 전용 제외 속성</span><span class="sxs-lookup"><span data-stu-id="608bd-115">Properties, except for read-only</span></span>|<span data-ttu-id="608bd-116">열거형 멤버</span><span class="sxs-lookup"><span data-stu-id="608bd-116">Enumeration members</span></span>|  
|<span data-ttu-id="608bd-117">배열 요소</span><span class="sxs-lookup"><span data-stu-id="608bd-117">Array elements</span></span>|<span data-ttu-id="608bd-118">식 (해당 요소를 수정할 수 있는 경우에)</span><span class="sxs-lookup"><span data-stu-id="608bd-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="608bd-119">수정할 수 있는 인수와 인수</span><span class="sxs-lookup"><span data-stu-id="608bd-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="608bd-120">A *수정할 수 있는 인수* 는 수정할 수 없는 내부 요소를 포함 된 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="608bd-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="608bd-121">호출 코드에서 언제 든 지 새 값을 저장할 수는 인수를 전달 하는 경우 및 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), 절차의 코드 호출 코드에서 기본 요소를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="608bd-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="608bd-122">A *수정할 수 없는 인수* 는 수정할 수 없는 내부 요소 또는 전달 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="608bd-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="608bd-123">수정 가능한 요소인 것 이며 경우에 프로시저에서 호출 코드에서 해당 요소를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="608bd-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="608bd-124">수정할 수 없는 요소는 호출 코드 자체 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="608bd-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="608bd-125">호출된 된 프로시저 수정 호출 코드에서 해당 요소에는 영향을 주지 있지만 수정할 수 없는 인수의 자체 로컬 복사본을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="608bd-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="608bd-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="608bd-126">See Also</span></span>  
 [<span data-ttu-id="608bd-127">절차</span><span class="sxs-lookup"><span data-stu-id="608bd-127">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="608bd-128">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="608bd-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="608bd-129">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="608bd-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="608bd-130">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="608bd-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="608bd-131">인수를 값으로 전달할 때와 참조로 전달할 때의 차이점</span><span class="sxs-lookup"><span data-stu-id="608bd-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="608bd-132">방법: 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="608bd-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="608bd-133">방법: 값 변경에 대해 프로시저 인수 보호</span><span class="sxs-lookup"><span data-stu-id="608bd-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="608bd-134">방법: 인수가 값으로 전달되도록 설정</span><span class="sxs-lookup"><span data-stu-id="608bd-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="608bd-135">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="608bd-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="608bd-136">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="608bd-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
