---
title: "Implicit conversion from &#39;&lt;typename1&gt;&#39; to &#39;&lt;typename2&gt;&#39; in copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc41999"
  - "bc41999"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC41999"
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Implicit conversion from &#39;&lt;typename1&gt;&#39; to &#39;&lt;typename2&gt;&#39; in copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument.
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

해당 매개 변수의 형식과 다른 형식의 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) 인수로 프로시저를 호출했습니다.  
  
 `ByRef` 인수를 전달하면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 참조를 전달하는 대신 인수 값을 프로시저의 지역 변수에 복사하는 경우가 있습니다.  이러한 경우 프로시저가 반환되면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 지역 변수 값을 호출 코드의 인수에 다시 복사해야 합니다.  
  
 `ByRef` 인수 값이 프로시저에 복사되고 인수와 매개 변수의 형식이 같으면 변환이 필요하지 않습니다.  그러나 형식이 다르면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 양방향으로 변환해야 합니다.  프로시저 인수 또는 매개 변수에 대해 `CType`이나 기타 변환 키워드를 사용할 수 없으므로 이러한 변환은 항상 암시적입니다.  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC41999  
  
### 이 오류를 해결하려면  
  
-   가능한 경우 프로시저 매개 변수와 같은 형식의 호출 인수를 사용합니다. 그러면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 변환이 필요하지 않습니다.  
  
-   매개 변수 형식과 다른 인수 형식으로 프로시저를 호출해야 하지만 호출 인수에 값을 반환하지 않아도 되는 경우에는 매개 변수를 `ByRef` 대신 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)로 정의합니다.  
  
## 참고 항목  
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Passing Arguments by Value and by Reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)