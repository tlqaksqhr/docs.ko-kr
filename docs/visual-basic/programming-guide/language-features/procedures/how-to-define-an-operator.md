---
title: "방법: 연산자 정의(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 51921ee38204fd528ed19436806fc9433abbdc5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="60cc4-102">방법: 연산자 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60cc4-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="60cc4-103">클래스 또는 구조체를 정의한 경우에 표준 연산자의 동작을 정의할 수 있습니다 (같은 `*`, `<>`, 또는 `And`) 경우 하나 또는 두 개의 피연산자는 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="60cc4-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="60cc4-104">클래스 또는 구조체 내에서 연산자 프로시저도 표준 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="60cc4-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="60cc4-105">모든 연산자 프로시저 여야 `Public` `Shared`합니다.</span><span class="sxs-lookup"><span data-stu-id="60cc4-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="60cc4-106">클래스 또는 구조체에서 연산자를 정의 라고도 *오버 로드* 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="60cc4-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60cc4-107">예제</span><span class="sxs-lookup"><span data-stu-id="60cc4-107">Example</span></span>  
 <span data-ttu-id="60cc4-108">다음 예제에서는 정의 `+` 구조체에 대 한 연산자 호출 `height`합니다.</span><span class="sxs-lookup"><span data-stu-id="60cc4-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="60cc4-109">피트 및 인치 단위로 측정 된 높이 사용 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="60cc4-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="60cc4-110">하나의 *인치* 2.54 센티미터 개와 *foot* 는 12 인치입니다.</span><span class="sxs-lookup"><span data-stu-id="60cc4-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="60cc4-111">정규화 된 값 (인치 < 12.0)을 보장 하려면 생성자는 다음과 같이 수행 됩니다. *모듈로* 산술 12입니다.</span><span class="sxs-lookup"><span data-stu-id="60cc4-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="60cc4-112">`+` 연산자 생성자를 사용 하 여 정규화 된 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="60cc4-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](./codesnippet/VisualBasic/how-to-define-an-operator_1.vb)]  
  
 <span data-ttu-id="60cc4-113">구조를 테스트할 수 `height` 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="60cc4-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](./codesnippet/VisualBasic/how-to-define-an-operator_2.vb)]  
  
 <span data-ttu-id="60cc4-114">자세한 내용과 예제는 [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703)(Visual Basic 2005의 연산자 오버로드)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60cc4-114">For more information and examples, see [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60cc4-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60cc4-115">See Also</span></span>  
 [<span data-ttu-id="60cc4-116">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="60cc4-116">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="60cc4-117">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="60cc4-117">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="60cc4-118">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="60cc4-118">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="60cc4-119">방법: 연산자를 정의하는 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="60cc4-119">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)  
 [<span data-ttu-id="60cc4-120">Operator 문</span><span class="sxs-lookup"><span data-stu-id="60cc4-120">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="60cc4-121">Structure 문</span><span class="sxs-lookup"><span data-stu-id="60cc4-121">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="60cc4-122">방법: 구조체 선언</span><span class="sxs-lookup"><span data-stu-id="60cc4-122">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="60cc4-123">Mod 연산자</span><span class="sxs-lookup"><span data-stu-id="60cc4-123">Mod Operator</span></span>](../../../../visual-basic/language-reference/operators/mod-operator.md)
