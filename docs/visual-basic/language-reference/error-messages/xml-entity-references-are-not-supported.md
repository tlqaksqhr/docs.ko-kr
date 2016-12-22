---
title: "XML entity references are not supported | Microsoft Docs"
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
  - "vbc31180"
  - "bc31180"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31180"
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML entity references are not supported
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

XML 1.0 사양에 정의되어 있지 않은 엔터티 참조\(예: `©`\)가 XML 리터럴의 값으로 포함되었습니다.  XML 리터럴에는 `&`, `"`, `<`, `>` 및 `'` XML 엔터티 참조만 지원됩니다.  
  
 **오류 ID:** BC31180  
  
### 이 오류를 해결하려면  
  
-   지원되지 않는 엔터티 참조를 제거합니다.  
  
## 참고 항목  
 [XML Literals and the XML 1.0 Specification](../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)