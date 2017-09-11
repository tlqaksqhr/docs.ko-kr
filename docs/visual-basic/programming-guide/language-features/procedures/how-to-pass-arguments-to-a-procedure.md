---
title: "방법: 프로시저 (Visual Basic)에 인수를 전달 합니다. | Microsoft 문서"
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
- arguments [Visual Basic], passing to procedures
- procedures, arguments
- procedures, parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures, calling
- argument passing, procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: 14
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
ms.openlocfilehash: 1e0a8d5e798f25f22f53f56a7c01bd69e3e14463
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="0bf70-102">방법: 프로시저에 인수 전달(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0bf70-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="0bf70-103">프로시저를 호출 하는 경우에 인수 목록 괄호로 묶어 프로시저 이름 뒤에.</span><span class="sxs-lookup"><span data-stu-id="0bf70-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="0bf70-104">프로시저를 정의 하는 모든 필수 매개 변수에 해당 하는 인수를 제공 하 고에 대 한 인수를 선택적으로 제공할 수는 `Optional` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="0bf70-105">지정 하지 않으면는 `Optional` 호출에서 매개 변수를 모든 후속 인수를 제공 하는 경우 인수 목록에서 해당 위치를 표시 하는 쉼표를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="0bf70-106">데이터 형식의 인수를와 같은 서로 다른 지는 해당 매개 변수로 전달 하려는 경우 `Byte` 를 `String`, 형식 검사 스위치를 설정할 수 있습니다 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))를 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="0bf70-107">경우 `Option Strict` 는 `On`, 하나를 사용 해야 확대 변환 또는 명시적 변환 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="0bf70-108">자세한 내용은 참조 [확장 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) 및 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="0bf70-109">자세한 내용은 참조 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="0bf70-110">프로시저에 하나 이상의 인수를 전달 하려면</span><span class="sxs-lookup"><span data-stu-id="0bf70-110">To pass one or more arguments to a procedure</span></span>  
  
1.  <span data-ttu-id="0bf70-111">문 호출 프로시저 이름을 뒤에 괄호를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2.  <span data-ttu-id="0bf70-112">괄호 안에 인수 목록을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="0bf70-113">프로시저에 정의 필요한 각 매개 변수에 대 한 인수를 포함 하 고 인수를 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3.  <span data-ttu-id="0bf70-114">각 인수는 해당 매개 변수에 대 한 프로시저 형식으로 변환할 수 있는 데이터 형식으로 계산 되는 유효한 식 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4.  <span data-ttu-id="0bf70-115">매개 변수가 정의 되어 있으면 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md)를 인수 목록에 포함 하거나 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="0bf70-116">를 생략 하면 프로시저는 해당 매개 변수에 대해 정의 된 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5.  <span data-ttu-id="0bf70-117">에 대 한 인수를 생략 하면는 `Optional` 매개 변수 및 매개 변수 목록 뒤에 다른 매개 변수가 있는, 인수 목록에 여분의 쉼표 여 생략 된 인수의 위치를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="0bf70-118">다음 예제에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>함수.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="0bf70-118">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     <span data-ttu-id="0bf70-119">[!code-vb[VbVbcnProcedures #&34;](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0bf70-119">[!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="0bf70-120">앞의 예제에 표시 될 메시지 문자열은 필요한 첫 번째 인수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-120">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="0bf70-121">메시지 상자에 표시할 단추를 지정 하는 선택적 두 번째 매개 변수에 대 한 인수를 생략 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-121">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="0bf70-122">호출에 값을 제공 하지 않는 때문에 `MsgBox` 기본값을 사용 하 여 `MsgBoxStyle.OKOnly`만 표시 되는 **확인** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-122">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="0bf70-123">인수 목록에 두 번째 쉼표는 생략 두 번째 인수의 위치를 표시 하 고 마지막 문자열의 세 번째 선택적 매개 변수에 전달 됩니다 `MsgBox`, 제목 표시줄에 표시할 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="0bf70-123">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf70-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bf70-124">See Also</span></span>  
 <span data-ttu-id="0bf70-125">[Sub 프로시저](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="0bf70-125">[Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="0bf70-126"> [Function 프로시저](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="0bf70-126"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="0bf70-127"> [속성 프로시저](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="0bf70-127"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="0bf70-128"> [연산자 프로시저](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="0bf70-128"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="0bf70-129"> [방법: 프로시저에 대 한 매개 변수를 정의 합니다.](./how-to-define-a-parameter-for-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="0bf70-129"> [How to: Define a Parameter for a Procedure](./how-to-define-a-parameter-for-a-procedure.md) </span></span>  
<span data-ttu-id="0bf70-130"> [값 및 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0bf70-130"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="0bf70-131"> [재귀 프로시저](./recursive-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="0bf70-131"> [Recursive Procedures](./recursive-procedures.md) </span></span>  
<span data-ttu-id="0bf70-132"> [프로시저 오버 로드](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="0bf70-132"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="0bf70-133"> [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="0bf70-133"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="0bf70-134"> [개체 지향 프로그래밍](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span><span class="sxs-lookup"><span data-stu-id="0bf70-134"> [Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span></span>
