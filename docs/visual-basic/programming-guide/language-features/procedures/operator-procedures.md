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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a9e86c9c466ba236cc33153f2f341af35c622de6
ms.lasthandoff: 03/13/2017

---
# <a name="operator-procedures-visual-basic"></a>연산자 프로시저(Visual Basic)
연산자 프로시저는 일련의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 표준 연산자의 동작을 정의 하는 문 (예: `*`, `<>`, 또는 `And`) 클래스 또는 구조를 정의한 경우에 합니다. 이 라고도 *연산자 오버 로드*합니다.  
  
## <a name="when-to-define-operator-procedures"></a>연산자 프로시저를 정의 하는 경우  
 클래스 또는 구조를 정의한 경우 해당 클래스 또는 구조체의 형식으로 변수를 선언할 수 있습니다. 이러한 변수는 식의 일부로 작업에 참여 하도록 필요한 경우도 있습니다. 이 작업을 수행 하는 연산자의 피연산자는 이어야 합니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]연산자의 기본 데이터 형식에 대해서만 정의합니다. 한 경우 연산자의 동작을 정의할 수 또는 두 개의 피연산자는 클래스 또는 구조체의 형식입니다.  
  
 자세한 내용은 참조 [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)합니다.  
  
## <a name="types-of-operator-procedure"></a>연산자 프로시저의 형식  
 연산자 프로시저는 다음 유형 중 하나일 수 있습니다.  
  
-   클래스 또는 구조체의 형식 인수가 있는 단항 연산자의 정의입니다.  
  
-   여기서 클래스 또는 구조체의 형식 인수 중 적어도 하나는 이항 연산자의 정의입니다.  
  
-   인수 클래스 또는 구조체의 형식 변환 연산자의 정의입니다.  
  
-   클래스 또는 구조체의 형식을 반환 하는 변환 연산자의 정의입니다.  
  
 변환 연산자는 항상 단항이며 및 항상 사용 `CType` 정의 하는 연산자입니다.  
  
## <a name="declaration-syntax"></a>선언 구문  
 연산자 프로시저를 선언 하기 위한 구문은 다음과 같습니다.  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 사용 된 `Widening` 또는 `Narrowing` 형식 변환 연산자에 대해서만 키워드입니다. 연산자 기호는 항상 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 형식 변환 연산자에 대 한 합니다.  
  
 이항 연산자를 정의 하는 두 개의 피연산자를 선언 및 형식 변환 연산자를 포함 하 여 단항 연산자를 정의 하는 하나의 피연산자를 선언 합니다. 모든 피연산자를 선언 해야 `ByVal`합니다.  
  
 매개 변수를 선언 하면 동일한 방식으로 각 피연산자를 선언 [Sub 프로시저](./sub-procedures.md)합니다.  
  
### <a name="data-type"></a>데이터 형식  
 연산자를 정의 하는 클래스 또는 구조를 정의한 경우에 있으므로 피연산자 중 하나 이상이 해당 클래스 또는 구조체의 데이터 형식 이어야 합니다. 형식 변환 연산자에 대 한 반환 형식 또는 피연산자 클래스 또는 구조체의 데이터 형식 이어야 합니다.  
  
 자세한 내용은 다음을 참조 하십시오. [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)합니다.  
  
## <a name="calling-syntax"></a>호출 구문  
 식에서 연산자 기호를 사용 하 여 연산자 프로시저를 암시적으로 호출 합니다. 미리 정의 된 연산자와 동일한 방식으로 피연산자를 제공 합니다.  
  
 연산자 프로시저는 암시적으로 호출에 대 한 구문은 다음과 같습니다.  
  
 `Dim testStruct As`  *structurename*  
  
 `Dim testNewStruct As`  *structurename*`= testStruct`*operatorsymbol    *  `10`  
  
### <a name="illustration-of-declaration-and-call"></a>선언 및 호출의 그림  
 다음과 같은 구조는 128 비트의 부호 있는 정수 값을 구성 하는 상위 및 하위 부분으로 저장합니다. 정의 `+` 두 개를 추가 하는 연산자 `veryLong` 값 및 결과 생성 `veryLong` 값입니다.  
  
 [!code-vb[VbVbcnProcedures&23;](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 다음 예제에서는 호출을는 `+` 에 정의 된 운영자 `veryLong`합니다.  
  
 [!code-vb[VbVbcnProcedures #&24;](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 자세한 내용 및 예제에 대 한 참조 [Visual Basic 2005의 연산자 오버 로드를](http://go.microsoft.com/fwlink/?LinkId=101703)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [Sub 프로시저](./sub-procedures.md)   
 [Function 프로시저](./function-procedures.md)   
 [속성 프로시저](./property-procedures.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [방법: 연산자 정의](./how-to-define-an-operator.md)   
 [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md)   
 [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md)   
 [방법: 연산자를 정의하는 클래스 사용](./how-to-use-a-class-that-defines-operators.md)
