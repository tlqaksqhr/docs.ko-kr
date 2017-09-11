---
title: "연산자 프로시저 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, operator
- Visual Basic code, operators
- syntax, Operator procedures
- operators [Visual Basic], overloading
- overloaded operators
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3b2e8466ad355521dcec3cf7b2949037e569eb9a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="904c5-102">연산자 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="904c5-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="904c5-103">연산자 프로시저는 일련의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 표준 연산자의 동작을 정의 하는 문 (예: `*`, `<>`, 또는 `And`) 클래스 또는 구조를 정의한 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-103">An operator procedure is a series of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="904c5-104">이 라고도 *연산자 오버 로드*합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="904c5-105">연산자 프로시저를 정의 하는 경우</span><span class="sxs-lookup"><span data-stu-id="904c5-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="904c5-106">클래스 또는 구조를 정의한 경우 해당 클래스 또는 구조체의 형식으로 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="904c5-107">이러한 변수는 식의 일부로 작업에 참여 하도록 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="904c5-108">이 작업을 수행 하는 연산자의 피연산자는 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-108">To do this, it must be an operand of an operator.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="904c5-109">연산자의 기본 데이터 형식에 대해서만 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-109"> defines operators only on its fundamental data types.</span></span> <span data-ttu-id="904c5-110">한 경우 연산자의 동작을 정의할 수 또는 두 개의 피연산자는 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="904c5-111">자세한 내용은 참조 [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="904c5-112">연산자 프로시저의 형식</span><span class="sxs-lookup"><span data-stu-id="904c5-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="904c5-113">연산자 프로시저는 다음 유형 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-113">An operator procedure can be one of the following types:</span></span>  
  
-   <span data-ttu-id="904c5-114">클래스 또는 구조체의 형식 인수가 있는 단항 연산자의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="904c5-115">여기서 클래스 또는 구조체의 형식 인수 중 적어도 하나는 이항 연산자의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="904c5-116">인수 클래스 또는 구조체의 형식 변환 연산자의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="904c5-117">클래스 또는 구조체의 형식을 반환 하는 변환 연산자의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="904c5-118">변환 연산자는 항상 단항이며 및 항상 사용 `CType` 정의 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="904c5-119">선언 구문</span><span class="sxs-lookup"><span data-stu-id="904c5-119">Declaration Syntax</span></span>  
 <span data-ttu-id="904c5-120">연산자 프로시저를 선언 하기 위한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="904c5-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span><span class="sxs-lookup"><span data-stu-id="904c5-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="904c5-122">사용 된 `Widening` 또는 `Narrowing` 형식 변환 연산자에 대해서만 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="904c5-123">연산자 기호는 항상 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 형식 변환 연산자에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="904c5-124">이항 연산자를 정의 하는 두 개의 피연산자를 선언 및 형식 변환 연산자를 포함 하 여 단항 연산자를 정의 하는 하나의 피연산자를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="904c5-125">모든 피연산자를 선언 해야 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="904c5-126">매개 변수를 선언 하면 동일한 방식으로 각 피연산자를 선언 [Sub 프로시저](./sub-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="904c5-127">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="904c5-127">Data Type</span></span>  
 <span data-ttu-id="904c5-128">연산자를 정의 하는 클래스 또는 구조를 정의한 경우에 있으므로 피연산자 중 하나 이상이 해당 클래스 또는 구조체의 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="904c5-129">형식 변환 연산자에 대 한 반환 형식 또는 피연산자 클래스 또는 구조체의 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="904c5-130">자세한 내용은 다음을 참조 하십시오. [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="904c5-131">호출 구문</span><span class="sxs-lookup"><span data-stu-id="904c5-131">Calling Syntax</span></span>  
 <span data-ttu-id="904c5-132">식에서 연산자 기호를 사용 하 여 연산자 프로시저를 암시적으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="904c5-133">미리 정의 된 연산자와 동일한 방식으로 피연산자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="904c5-134">연산자 프로시저는 암시적으로 호출에 대 한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="904c5-135">`Dim testStruct As`  *structurename*</span><span class="sxs-lookup"><span data-stu-id="904c5-135">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="904c5-136">`Dim testNewStruct As`  *structurename*`= testStruct`*operatorsymbol    *  `10`</span><span class="sxs-lookup"><span data-stu-id="904c5-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="904c5-137">선언 및 호출의 그림</span><span class="sxs-lookup"><span data-stu-id="904c5-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="904c5-138">다음과 같은 구조는 128 비트의 부호 있는 정수 값을 구성 하는 상위 및 하위 부분으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="904c5-139">정의 `+` 두 개를 추가 하는 연산자 `veryLong` 값 및 결과 생성 `veryLong` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 <span data-ttu-id="904c5-140">[!code-vb[VbVbcnProcedures&23;](./codesnippet/VisualBasic/operator-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="904c5-140">[!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="904c5-141">다음 예제에서는 호출을는 `+` 에 정의 된 운영자 `veryLong`합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-141">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 <span data-ttu-id="904c5-142">[!code-vb[VbVbcnProcedures #&24;](./codesnippet/VisualBasic/operator-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="904c5-142">[!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]</span></span>  
  
 <span data-ttu-id="904c5-143">자세한 내용 및 예제에 대 한 참조 [Visual Basic 2005의 연산자 오버 로드를](http://go.microsoft.com/fwlink/?LinkId=101703)합니다.</span><span class="sxs-lookup"><span data-stu-id="904c5-143">For more information and examples, see [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="904c5-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="904c5-144">See Also</span></span>  
 <span data-ttu-id="904c5-145">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="904c5-145">[Procedures](./index.md) </span></span>  
<span data-ttu-id="904c5-146"> [Sub 프로시저](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="904c5-146"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="904c5-147"> [Function 프로시저](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="904c5-147"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="904c5-148"> [속성 프로시저](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="904c5-148"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="904c5-149"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="904c5-149"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="904c5-150"> [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md) </span><span class="sxs-lookup"><span data-stu-id="904c5-150"> [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md) </span></span>  
<span data-ttu-id="904c5-151"> [방법: 연산자 정의](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="904c5-151"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="904c5-152"> [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="904c5-152"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="904c5-153"> [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="904c5-153"> [How to: Call an Operator Procedure](./how-to-call-an-operator-procedure.md) </span></span>  
<span data-ttu-id="904c5-154"> [방법: 연산자를 정의하는 클래스 사용](./how-to-use-a-class-that-defines-operators.md)</span><span class="sxs-lookup"><span data-stu-id="904c5-154"> [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md)</span></span>
