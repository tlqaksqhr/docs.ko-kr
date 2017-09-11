---
title: "방법: 연산자 (Visual Basic)를 정의 하는 클래스를 사용 하 여 | Microsoft 문서"
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
- operator procedures, calling
- procedures, operator
- procedures, calling
- examples [Visual Basic], CType
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: 21
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
ms.openlocfilehash: e4d76788346e08123102d56088c0a1e0f5f2238f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="47f06-102">방법: 연산자를 정의하는 클래스 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47f06-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="47f06-103">클래스 또는 고유한 연산자를 정의 하는 구조체를 사용 하는 경우 이러한 연산자에서 액세스할 수 있습니다 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="47f06-103">If you are using a class or structure that defines its own operators, you can access those operators from [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="47f06-104">연산자를 정의 하는 클래스 또는 구조체에는 라고도 *오버 로드* 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="47f06-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47f06-105">예제</span><span class="sxs-lookup"><span data-stu-id="47f06-105">Example</span></span>  
 <span data-ttu-id="47f06-106">SQL 구조를 액세스 하는 다음 예제에서는 <xref:System.Data.SqlTypes.SqlString>, 변환 연산자를 정의 하는 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md))는 SQL 문자열 사이의 양방향 및 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자열.</xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="47f06-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string.</span></span> <span data-ttu-id="47f06-107">사용 하 여 `CType(` *SQL 문자열 식*, `String)` SQL 문자열을 변환 하는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자열 및 `CType(` *Visual Basic 문자열 식을*, <xref:System.Data.SqlTypes.SqlString> `)` 반대 방향에서으로 변환 하.</xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="47f06-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 <span data-ttu-id="47f06-108">[!code-vb[VbVbcnProcedures #&30;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="47f06-108">[!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]</span></span>  
  
 <span data-ttu-id="47f06-109">[!code-vb[VbVbcnProcedures #&31;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="47f06-109">[!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]</span></span>  
  
 <span data-ttu-id="47f06-110"><xref:System.Data.SqlTypes.SqlString>구조 변환 연산자 정의 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md))에서 `String` 를 <xref:System.Data.SqlTypes.SqlString>에서 다른 <xref:System.Data.SqlTypes.SqlString>를 `String`.</xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="47f06-110">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="47f06-111">할당 하는 문을 `title` 를 `jobTitle` 첫 번째 연산자를 사용 하 고 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>함수 호출에서는 두 번째.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="47f06-111">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="47f06-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="47f06-112">Compiling the Code</span></span>  
 <span data-ttu-id="47f06-113">클래스 또는 구조체를 사용 하는 데 사용할 연산자를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47f06-113">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="47f06-114">클래스 또는 구조체 오버 로드에 사용할 수 있는 모든 연산자가 정의 가정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="47f06-114">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="47f06-115">사용 가능한 연산자 목록을 참조 하십시오. [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="47f06-115">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="47f06-116">적절 한 포함 `Imports` 소스 파일의 시작 부분에 SQL 문자열에 대 한 문 (이 경우 <xref:System.Data.SqlTypes>).</xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="47f06-116">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="47f06-117">프로젝트에는 System.Data 및 System.XML에 대 한 참조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47f06-117">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47f06-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47f06-118">See Also</span></span>  
 <span data-ttu-id="47f06-119">[연산자 프로시저](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="47f06-119">[Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="47f06-120"> [방법: 연산자 정의](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="47f06-120"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="47f06-121"> [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="47f06-121"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="47f06-122"> [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="47f06-122"> [How to: Call an Operator Procedure](./how-to-call-an-operator-procedure.md) </span></span>  
<span data-ttu-id="47f06-123"> [확대 변환](../../../../visual-basic/language-reference/modifiers/widening.md) </span><span class="sxs-lookup"><span data-stu-id="47f06-123"> [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) </span></span>  
<span data-ttu-id="47f06-124"> [축소](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span><span class="sxs-lookup"><span data-stu-id="47f06-124"> [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span></span>  
<span data-ttu-id="47f06-125"> [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="47f06-125"> [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="47f06-126"> [방법: 구조체 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span><span class="sxs-lookup"><span data-stu-id="47f06-126"> [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span></span>  
<span data-ttu-id="47f06-127"> [암시적 변환과 명시적 변환](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="47f06-127"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="47f06-128"> [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="47f06-128"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>
