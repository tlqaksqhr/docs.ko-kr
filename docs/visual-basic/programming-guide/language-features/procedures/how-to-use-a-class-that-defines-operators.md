---
title: '방법: 연산자를 정의하는 클래스 사용(Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
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
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e0bcfaeca638dfabb841a9e935b872f76fdf957
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>방법: 연산자를 정의하는 클래스 사용(Visual Basic)
클래스 또는 고유한 연산자를 정의 하는 구조체를 사용 하는 경우에 Visual Basic에서 이러한 연산자를 액세스할 수 있습니다.  
  
 클래스 또는 구조체에서 연산자를 정의 라고도 *오버 로드* 연산자입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 액세스 SQL 구조 <xref:System.Data.SqlTypes.SqlString>, 변환 연산자를 정의 하는 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)) SQL 문자열 및 Visual Basic 문자열 사이 두 방향에서 합니다. 사용 하 여 `CType(` *SQL 문자열 식*, `String)` Visual Basic 문자열에 SQL 문자열을 변환 하 고 `CType(` *Visual Basic 문자열 식을*, <xref:System.Data.SqlTypes.SqlString> `)` 는 다른 곳에서 변환 하도록 합니다.  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 <xref:System.Data.SqlTypes.SqlString> 구조 변환 연산자 정의 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md))에서 `String` 를 <xref:System.Data.SqlTypes.SqlString> 및 다른 인스턴스로 <xref:System.Data.SqlTypes.SqlString> 를 `String`합니다. 할당 하는 문을 `title` 를 `jobTitle` 첫 번째 연산자를 사용 하 고 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수 호출에서는 두 번째입니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 클래스 또는 구조체를 사용 하는 데 사용할 연산자를 정의 해야 합니다. 클래스 또는 구조체 오버 로드에 사용할 수 있는 모든 연산자가 정의 가정 하지 마십시오. 사용 가능한 연산자 목록을 참조 하십시오. [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)합니다.  
  
 적절 한 포함 `Imports` 소스 파일의 시작 부분에 SQL 문자열에 대 한 문 (이 경우 <xref:System.Data.SqlTypes>).  
  
 프로젝트는 System.Data 및 System.XML에 대 한 참조가 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연산자 프로시저](./operator-procedures.md)  
 [방법: 연산자 정의](./how-to-define-an-operator.md)  
 [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md)  
 [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md)  
 [확장](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [방법: 구조체 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [암시적 변환과 명시적 변환](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
