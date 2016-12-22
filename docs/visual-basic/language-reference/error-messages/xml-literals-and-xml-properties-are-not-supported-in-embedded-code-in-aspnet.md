---
title: "XML literals and XML properties are not supported in embedded code within ASP.NET | Microsoft Docs"
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
  - "vbc31200"
  - "bc31200"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31200"
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML literals and XML properties are not supported in embedded code within ASP.NET
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

XML 리터럴 및 XML 속성은 ASP.NET의 포함 코드에서 지원되지 않습니다.XML 기능을 사용하려면 코드를 코드 숨김으로 옮기십시오.  
  
 XML 리터럴 또는 XML 축 속성을 ASP.NET 파일의 포함 코드\(`<%= =>`\) 내에 정의했습니다.  
  
 **오류 ID:** BC31200  
  
### 이 오류를 해결하려면  
  
-   XML 리터럴 또는 XML 축 속성이 포함된 코드를 ASP.NET 코드 숨김 파일로 이동합니다.  
  
## 참고 항목  
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)