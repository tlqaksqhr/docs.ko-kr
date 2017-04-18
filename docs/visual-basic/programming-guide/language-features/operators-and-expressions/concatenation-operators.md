---
title: "Visual Basic의 연결 연산자 | Microsoft 문서"
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
- '& operator [Visual Basic], concatenation'
- concatenation operators
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators, Visual Basic strings
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
caps.latest.revision: 18
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
ms.openlocfilehash: fa11f1dcff2c333861596cbac03391403cf962c1
ms.lasthandoff: 03/13/2017

---
# <a name="concatenation-operators-in-visual-basic"></a>Visual Basic의 연결 연산자
연결 연산자는 여러 문자열을 단일 문자열로 조인합니다. 연결 연산자에는 `+` 및 `&`의 두 가지가 있습니다. 이 두 연산자는 모두 다음 예제에 나와 있는 것처럼 기본적인 연결 작업을 수행합니다.  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 이러한 연산자는 다음 예제에 나와 있는 것처럼 `String` 변수도 연결할 수 있습니다.  
  
 [!code-vb[VbVbalrOperators #&76;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]  
  
## <a name="differences-between-the-two-concatenation-operators"></a>두 연결 연산자의 차이점  
 [+ 연산자](../../../../visual-basic/language-reference/operators/addition-operator.md) 용도로 두 개의 숫자를 추가 했습니다. 그러나 숫자 피연산자와 문자열 피연산자를 연결할 수도 있습니다. `+` 연산자를 추가, 연결는 컴파일러 오류 또는 런타임에 발생 여부를 결정 하는 규칙의 복잡 한 집합이 <xref:System.InvalidCastException>예외.</xref:System.InvalidCastException>  
  
 [연산자 / /](../../../../visual-basic/language-reference/operators/concatenation-operator.md) 에 대해서만 정의 `String` 피연산자 항상 확대 변환 되는 피연산자를 `String`의 설정에 관계 없이 `Option Strict`합니다. `&` 연산자는 문자열에 대해서만 정의되며 의도하지 않은 변환을 생성할 가능성을 줄이므로 문자열 연결에 사용하는 것이 좋습니다.  
  
## <a name="performance-string-and-stringbuilder"></a>성능: String 및 StringBuilder  
 하면 성능을 개선할 수 많은 수의 연결, 삭제, 대체 등의 문자열 조작 수행 하는 경우는 <xref:System.Text.StringBuilder>클래스에 <xref:System.Text>네임 스페이스.</xref:System.Text> </xref:System.Text.StringBuilder> 만들기 및 초기화 하는 추가 명령을 소요 되는 <xref:System.Text.StringBuilder>개체 및 하며 최종 값으로 변환 하기는 `String`, 때문에이 시간을 줄일 수 있지만 <xref:System.Text.StringBuilder>더 빠르게 수행할 수 있습니다.</xref:System.Text.StringBuilder> </xref:System.Text.StringBuilder>  
  
## <a name="see-also"></a>참고 항목  
 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Visual Basic의 문자열 조작 메서드 유형](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)   
 [Visual Basic의 산술 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Visual Basic의 비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Visual Basic의 논리 및 비트 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
