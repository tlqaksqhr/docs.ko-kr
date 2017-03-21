---
title: "&quot;모든&quot; 사용할 수 없습니다 &quot;Declare&quot; 문에서 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30828
- vbc30828
dev_langs:
- VB
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: 11
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
ms.openlocfilehash: fb179ae938d4c132f61e2076248729f7ea15a13f
ms.lasthandoff: 03/13/2017

---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a>'모든' 사용할 수 없습니다 'Declare' 문에서
`Any` 데이터 형식을 사용한 `Declare` Visual Basic 6.0 및 이전 버전의 모든 종류의 데이터를 포함할 수 있는 인수 사용을 허용 하는 문입니다. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]오버 로드를 지원 하 고 그렇게는 `Any` 데이터 형식은 사용 되지 않습니다.  
  
 **오류 ID:** BC30828  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  사용할; 특정 종류의 매개 변수를 선언 합니다. 예를 들어 있습니다.  
  
     [!code-vb[VbVbalrStatements #&95;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  사용 된 <xref:System.Runtime.InteropServices.MarshalAsAttribute>특성 지정을 `As Any` 때 `Void*` 호출 되는 프로시저에서 예상 하는.</xref:System.Runtime.InteropServices.MarshalAsAttribute>  
  
     [!code-vb[VbVbalrStatements #&96;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute></xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [연습: Windows Api 호출](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)   
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [관리 코드에서 프로토타입 만들기](http://msdn.microsoft.com/library/ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d)
