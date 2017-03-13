---
title: "&#39;As Any&#39; is not supported in &#39;Declare&#39; statements | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30828"
  - "vbc30828"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30828"
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# &#39;As Any&#39; is not supported in &#39;Declare&#39; statements
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

어떤 형식의 데이터라도 포함할 수 있는 인수를 사용할 수 있도록 `Any` 데이터 형식이 Visual Basic 6.0과 이전 버전의 `Declare` 문에 사용되었습니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 오버로드를 지원하기 때문에 `Any` 데이터 형식은 사용되지 않습니다.  
  
 **오류 ID:** BC30828  
  
### 이 오류를 해결하려면  
  
1.  사용하고자 하는 특정 형식의 매개 변수를 선언합니다. 예를 들면 다음과 같습니다.  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여, 호출할 프로시저에 `Void*`가 필요할 때 `As Any`를 지정합니다.  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)   
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [관리 코드에서 프로토타입 만들기](../Topic/Creating%20Prototypes%20in%20Managed%20Code.md)