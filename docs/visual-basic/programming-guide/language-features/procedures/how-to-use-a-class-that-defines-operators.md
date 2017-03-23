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
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b1db7c0b2a6fd8160baa48892b5f2214df24674e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>방법: 연산자를 정의하는 클래스 사용(Visual Basic)
클래스 또는 고유한 연산자를 정의 하는 구조체를 사용 하는 경우 이러한 연산자에서 액세스할 수 있습니다 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.  
  
 연산자를 정의 하는 클래스 또는 구조체에는 라고도 *오버 로드* 연산자입니다.  
  
## <a name="example"></a>예제  
 SQL 구조를 액세스 하는 다음 예제에서는 <xref:System.Data.SqlTypes.SqlString>, 변환 연산자를 정의 하는 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md))는 SQL 문자열 사이의 양방향 및 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자열.</xref:System.Data.SqlTypes.SqlString> 사용 하 여 `CType(` *SQL 문자열 식*, `String)` SQL 문자열을 변환 하는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자열 및 `CType(` *Visual Basic 문자열 식을*, <xref:System.Data.SqlTypes.SqlString> `)` 반대 방향에서으로 변환 하.</xref:System.Data.SqlTypes.SqlString>  
  
 [!code-vb[VbVbcnProcedures #&30;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures #&31;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 <xref:System.Data.SqlTypes.SqlString>구조 변환 연산자 정의 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md))에서 `String` 를 <xref:System.Data.SqlTypes.SqlString>에서 다른 <xref:System.Data.SqlTypes.SqlString>를 `String`.</xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString> 할당 하는 문을 `title` 를 `jobTitle` 첫 번째 연산자를 사용 하 고 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>함수 호출에서는 두 번째.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 클래스 또는 구조체를 사용 하는 데 사용할 연산자를 정의 해야 합니다. 클래스 또는 구조체 오버 로드에 사용할 수 있는 모든 연산자가 정의 가정 하지 마십시오. 사용 가능한 연산자 목록을 참조 하십시오. [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)합니다.  
  
 적절 한 포함 `Imports` 소스 파일의 시작 부분에 SQL 문자열에 대 한 문 (이 경우 <xref:System.Data.SqlTypes>).</xref:System.Data.SqlTypes>  
  
 프로젝트에는 System.Data 및 System.XML에 대 한 참조가 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연산자 프로시저](./operator-procedures.md)   
 [방법: 연산자 정의](./how-to-define-an-operator.md)   
 [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md)   
 [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md)   
 [확대 변환](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [축소](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [방법: 구조체 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [암시적 변환과 명시적 변환](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
