---
title: Visual Basic의 변수
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
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7a47ad7e4ade9f15159c27ac672aeb937a05493
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="variables-in-visual-basic"></a><span data-ttu-id="c4064-102">Visual Basic의 변수</span><span class="sxs-lookup"><span data-stu-id="c4064-102">Variables in Visual Basic</span></span>
<span data-ttu-id="c4064-103">일반적으로 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서 계산을 수행할 경우 값을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-103">You often have to store values when you perform calculations with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="c4064-104">예를 들어 여러 값을 계산하여 비교하고 비교 결과에 따라 값에서 다른 작업을 수행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-104">For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison.</span></span> <span data-ttu-id="c4064-105">값을 비교하려면 값을 보존해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-105">You have to retain the values if you want to compare them.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="c4064-106">용도</span><span class="sxs-lookup"><span data-stu-id="c4064-106">Usage</span></span>  
 <span data-ttu-id="c4064-107">대부분 프로그래밍 언어처럼 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서는 값 저장에 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-107">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], just like most programming languages, uses variables for storing values.</span></span> <span data-ttu-id="c4064-108">*변수*에는 이름(변수에 포함된 값을 참조하는 데 사용할 단어)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-108">A *variable* has a name (the word that you use to refer to the value that the variable contains).</span></span> <span data-ttu-id="c4064-109">변수에는 데이터 형식(변수가 저장할 수 있는 데이터 종류 결정)도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-109">A variable also has a data type (which determines the kind of data that the variable can store).</span></span> <span data-ttu-id="c4064-110">변수는 밀접하게 관련된 데이터 항목의 인덱싱된 집합을 저장해야 할 경우 배열을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-110">A variable can represent an array if it has to store an indexed set of closely related data items.</span></span>  
  
 <span data-ttu-id="c4064-111">데이터 형식을 명시적으로 지정하지 않고 지역 형식 유추를 사용하여 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-111">Local type inference enables you to declare variables without explicitly stating a data type.</span></span> <span data-ttu-id="c4064-112">대신에 컴파일러는 초기화 식의 형식에서 변수 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-112">Instead, the compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="c4064-113">자세한 내용은 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) 및 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4064-113">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="assigning-values"></a><span data-ttu-id="c4064-114">값 할당</span><span class="sxs-lookup"><span data-stu-id="c4064-114">Assigning Values</span></span>  
 <span data-ttu-id="c4064-115">다음 예제와 같이 대입문을 사용하여 계산을 수행하고 결과를 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-115">You use assignment statements to perform calculations and assign the result to a variable, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]  
  
> [!NOTE]
>  <span data-ttu-id="c4064-116">이 예제의 등호(`=`)는 같음 연산자가 아닌 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-116">The equal sign (`=`) in this example is an assignment operator, not an equality operator.</span></span> <span data-ttu-id="c4064-117">값이 `applesSold` 변수에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-117">The value is being assigned to the variable `applesSold`.</span></span>  
  
 <span data-ttu-id="c4064-118">자세한 내용은 [방법: 변수 값 저장 및 검색](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4064-118">For more information, see [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).</span></span>  
  
## <a name="variables-and-properties"></a><span data-ttu-id="c4064-119">변수 및 속성</span><span class="sxs-lookup"><span data-stu-id="c4064-119">Variables and Properties</span></span>  
 <span data-ttu-id="c4064-120">변수처럼 *속성*은 액세스할 수 있는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-120">Like a variable, a *property* represents a value that you can access.</span></span> <span data-ttu-id="c4064-121">그러나 변수보다 더 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-121">However, it is more complex than a variable.</span></span> <span data-ttu-id="c4064-122">속성에는 값을 설정 및 검색하는 방법을 제어하는 코드 블록이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4064-122">A property uses code blocks that control how to set and retrieve its value.</span></span> <span data-ttu-id="c4064-123">자세한 내용은 [Visual Basic에서 속성과 변수의 차이점](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4064-123">For more information, see [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4064-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4064-124">See Also</span></span>  
 [<span data-ttu-id="c4064-125">변수 선언</span><span class="sxs-lookup"><span data-stu-id="c4064-125">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="c4064-126">개체 변수</span><span class="sxs-lookup"><span data-stu-id="c4064-126">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="c4064-127">변수 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c4064-127">Troubleshooting Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)  
 [<span data-ttu-id="c4064-128">방법: 변수 값 저장 및 검색</span><span class="sxs-lookup"><span data-stu-id="c4064-128">How to: Move Data Into and Out of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)  
 [<span data-ttu-id="c4064-129">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="c4064-129">Differences Between Properties and Variables in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)  
 [<span data-ttu-id="c4064-130">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="c4064-130">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
