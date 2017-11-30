---
title: "방법: 연산자를 정의하는 클래스 사용(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 223b3fc84fe75d1d530cd182c9332e5c663aa519
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="7d7e5-102">방법: 연산자를 정의하는 클래스 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d7e5-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="7d7e5-103">해당 연산자를 액세스할 수 있습니다를 사용 하는 클래스 또는 구조체는 자체 연산자를 정의 하는 경우 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="7d7e5-103">If you are using a class or structure that defines its own operators, you can access those operators from [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="7d7e5-104">클래스 또는 구조체에서 연산자를 정의 라고도 *오버 로드* 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="7d7e5-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d7e5-105">예제</span><span class="sxs-lookup"><span data-stu-id="7d7e5-105">Example</span></span>  
 <span data-ttu-id="7d7e5-106">다음 예제에서는 액세스 SQL 구조 <xref:System.Data.SqlTypes.SqlString>, 변환 연산자를 정의 하는 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)) SQL 문자열 사이 두 방향에서 및 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7d7e5-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] string.</span></span> <span data-ttu-id="7d7e5-107">사용 하 여 `CType(` *SQL 문자열 식*, `String)` SQL 문자열을 변환 하는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 문자열 및 `CType(` *Visual Basic 문자열 식을*, <xref:System.Data.SqlTypes.SqlString> `)` 는 다른 곳에서 변환 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d7e5-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 <span data-ttu-id="7d7e5-108"><xref:System.Data.SqlTypes.SqlString> 구조 변환 연산자 정의 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md))에서 `String` 를 <xref:System.Data.SqlTypes.SqlString> 및 다른 인스턴스로 <xref:System.Data.SqlTypes.SqlString> 를 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="7d7e5-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="7d7e5-109">할당 하는 문을 `title` 를 `jobTitle` 첫 번째 연산자를 사용 하 고 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수 호출에서는 두 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="7d7e5-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7d7e5-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7d7e5-110">Compiling the Code</span></span>  
 <span data-ttu-id="7d7e5-111">클래스 또는 구조체를 사용 하는 데 사용할 연산자를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d7e5-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="7d7e5-112">클래스 또는 구조체 오버 로드에 사용할 수 있는 모든 연산자가 정의 가정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="7d7e5-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="7d7e5-113">사용 가능한 연산자 목록을 참조 하십시오. [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d7e5-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="7d7e5-114">적절 한 포함 `Imports` 소스 파일의 시작 부분에 SQL 문자열에 대 한 문 (이 경우 <xref:System.Data.SqlTypes>).</span><span class="sxs-lookup"><span data-stu-id="7d7e5-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="7d7e5-115">프로젝트는 System.Data 및 System.XML에 대 한 참조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d7e5-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d7e5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d7e5-116">See Also</span></span>  
 [<span data-ttu-id="7d7e5-117">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="7d7e5-117">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="7d7e5-118">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="7d7e5-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="7d7e5-119">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="7d7e5-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="7d7e5-120">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="7d7e5-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="7d7e5-121">확장</span><span class="sxs-lookup"><span data-stu-id="7d7e5-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="7d7e5-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="7d7e5-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="7d7e5-123">Structure 문</span><span class="sxs-lookup"><span data-stu-id="7d7e5-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="7d7e5-124">방법: 구조체 선언</span><span class="sxs-lookup"><span data-stu-id="7d7e5-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="7d7e5-125">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="7d7e5-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="7d7e5-126">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="7d7e5-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
