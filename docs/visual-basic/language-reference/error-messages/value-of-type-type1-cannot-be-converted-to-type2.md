---
title: "Value of type &#39;type1&#39; cannot be converted to &#39;type2&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31194"
  - "bc31194"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31194"
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Value of type &#39;type1&#39; cannot be converted to &#39;type2&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

'type1' 형식의 값을 'type2'\(으\)로 변환할 수 없습니다.'Value' 속성을 사용하여 '\<parentElement\>'의 첫 번째 요소의 문자열 값을 가져올 수 있습니다.  
  
 XML 리터럴을 특정 형식으로 암시적으로 캐스팅하려고 했습니다.  XML 리터럴은 지정된 형식으로 암시적으로 캐스팅할 수 없습니다.  
  
 **오류 ID:** BC31194  
  
### 이 오류를 해결하려면  
  
-   XML 리터럴의 `Value` 속성을 사용하여 해당 값을 `String`으로 참조합니다.  다른 형식 변환 함수인 `CType` 함수를 사용하거나 <xref:System.Convert> 클래스를 사용하여 값을 지정된 형식으로 캐스팅할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Convert>   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)