---
title: "Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc42107"
  - "vbc42107"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42107"
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

'\<propertyname\>' 속성이 일부 코드 경로에 대해서만 값을 반환합니다.이 결과를 사용하면 런타임에 null 참조 예외가 발생할 수 있습니다.  
  
 속성 `Get` 프로시저에 코드를 통해 값을 반환하지 않는 경로가 하나 이상 있습니다.  
  
 다음 방법 중 하나로 속성 `Get` 프로시저에서 값을 반환할 수 있습니다.  
  
-   속성 이름에 값을 할당한 다음 `Exit Property` 문을 수행합니다.  
  
-   속성 이름에 값을 할당한 다음 `End Get` 문을 수행합니다.  
  
-   [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md)에 값을 포함합니다.  
  
 `Exit Property` 또는 `End Get`에 제어가 전달되고 속성 이름에 값을 할당하지 않은 경우 `Get` 프로시저에서는 속성 데이터 형식의 기본값을 반환합니다.  자세한 내용은 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)의 "동작"을 참조하십시오.  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC42107  
  
### 이 오류를 해결하려면  
  
-   제어 흐름 논리를 검사하고 반환의 원인이 되는 모든 문 앞에 값을 할당해야 합니다.  
  
     항상 `Return` 문을 사용하는 경우에는 프로시저의 모든 반환에서 값을 반환하게 하는 것이 더 간단합니다.  그렇게 하는 경우 `End Get` 앞의 마지막 문이 `Return` 문이어야 합니다.  
  
## 참고 항목  
 [Property 프로시저](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md)