---
title: '&#39;As Any&#39; 에서 지원 되지 않습니다 &#39;Declare&#39; 문'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d8146e339ac5cb005b99c9a1e02f1cd248c4558b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a>&#39;As Any&#39; 에서 지원 되지 않습니다 &#39;Declare&#39; 문
`Any` 데이터 형식이 사용 된 `Declare` Visual Basic 6.0 및 이전 버전의 모든 종류의 데이터를 포함할 수 있는 인수 사용을 허용 하는 문입니다. 그러나 오버 로드 하는 Visual Basic 지원 하 고 그렇게는 `Any` 데이터 형식은 사용 되지 않습니다.  
  
 **오류 ID:** BC30828  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  사용할; 특정 종류의 매개 변수를 선언 합니다. 예를 들어.  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  사용 하 여는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 지정 하려면 특성 `As Any` 때 `Void*` 호출 되는 프로시저에서 예상 하는 합니다.  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [연습: Windows API 호출](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [관리 코드에서 프로토타입 만들기](../../../framework/interop/creating-prototypes-in-managed-code.md)
