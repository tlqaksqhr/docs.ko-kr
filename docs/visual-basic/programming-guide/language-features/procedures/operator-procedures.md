---
title: 연산자 프로시저(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8fba5180da6498d280fa4192937c39d3e33168e8
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="operator-procedures-visual-basic"></a>연산자 프로시저(Visual Basic)
연산자 프로시저는 일련의 표준 연산자의 동작을 정의 하는 Visual Basic 문 (같은 `*`, `<>`, 또는 `And`) 클래스 또는 구조체 정의에서 합니다. 이 라고도 *연산자 오버 로드*합니다.  
  
## <a name="when-to-define-operator-procedures"></a>연산자 프로시저를 정의 하는 경우  
 클래스 또는 구조를 정의한 경우 해당 클래스 또는 구조체의 형식으로 변수를 선언할 수 있습니다. 경우에 따라 이러한 변수는 식의 일부로에 참여 해야 합니다. 이렇게 하려면 연산자의 피연산자 이어야 합니다.  
  
 Visual Basic의 기본 데이터 형식에 대해서만 연산자를 정의합니다. 두 개의 피연산자는 클래스 또는 구조체의 형식 또는 한 경우 연산자의 동작을 정의할 수 있습니다.  
  
 자세한 내용은 참조 [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)합니다.  
  
## <a name="types-of-operator-procedure"></a>연산자 프로시저의 형식  
 연산자 프로시저는 다음 유형 중 하나일 수 있습니다.  
  
-   클래스 또는 구조체의 형식 인수가 있는 단항 연산자의 정의입니다.  
  
-   여기서 클래스 또는 구조체의 형식 인수 중 적어도 하나는 이항 연산자의 정의입니다.  
  
-   클래스 또는 구조체의 형식 인수가 있는 변환 연산자의 정의입니다.  
  
-   클래스 또는 구조체의 형식을 반환 하는 변환 연산자의 정의입니다.  
  
 변환 연산자는 항상 단항이며 및 항상 사용 `CType` 정의 하는 연산자입니다.  
  
## <a name="declaration-syntax"></a>선언 구문  
 연산자 프로시저를 선언 하기 위한 구문은 다음과 같습니다.  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol* `(` *operand1*`[,`*operand2* `]) As` *데이터 형식*   
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 사용 된 `Widening` 또는 `Narrowing` 형식 변환 연산자에 대해서만 키워드입니다. 연산자 기호는 항상 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 형식 변환 연산자에 대 한 합니다.  
  
 이항 연산자를 정의 하는 두 개의 피연산자를 선언 및 형식 변환 연산자를 포함 하 여 단항 연산자를 정의 하는 하나의 피연산자를 선언 합니다. 모든 피연산자를 선언 해야 `ByVal`합니다.  
  
 에 대 한 매개 변수를 선언 같은 방식으로 각 피연산자를 선언 [Sub 프로시저](./sub-procedures.md)합니다.  
  
### <a name="data-type"></a>데이터 형식  
 연산자를 정의 하는 클래스 또는 구조체 정의에서 때문에 피연산자 중 하나 이상 해당 클래스 또는 구조체의 데이터 형식 이어야 합니다. 형식 변환 연산자에 대 한 피연산자 또는 반환 형식 중 하나가 클래스 또는 구조체의 데이터 형식 이어야 합니다.  
  
 자세한 내용은 참조 하십시오. [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)합니다.  
  
## <a name="calling-syntax"></a>호출 구문  
 식에서 연산자 기호를 사용 하 여 연산자 프로시저를 암시적으로 호출 합니다. 미리 정의 된 연산자에 대해 수행 하는 동일한 방식으로 피연산자를 제공 합니다.  
  
 연산자 프로시저에 대 한 암시적 호출에 대 한 구문은 다음과 같습니다.  
  
 `Dim testStruct As`  *structurename*  
  
 `Dim testNewStruct As`  *structurename*`= testStruct`*operatorsymbol*   `10`  
  
### <a name="illustration-of-declaration-and-call"></a>선언 및 호출의 그림  
 다음과 같은 구조 구성 하는 상위 및 하위 부분으로 서명 된 128 비트 정수 값을 저장합니다. 정의 `+` 두 개를 추가 하는 연산자 `veryLong` 값 및 결과 생성 `veryLong` 값입니다.  
  
 [!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 다음 예제에서는 호출을는 `+` 에 정의 된 운영자 `veryLong`합니다.  
  
 [!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 자세한 내용과 예제는 [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703)(Visual Basic 2005의 연산자 오버로드)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [Sub 프로시저](./sub-procedures.md)  
 [Function 프로시저](./function-procedures.md)  
 [속성 프로시저](./property-procedures.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [방법: 연산자 정의](./how-to-define-an-operator.md)  
 [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md)  
 [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md)  
 [방법: 연산자를 정의하는 클래스 사용](./how-to-use-a-class-that-defines-operators.md)
