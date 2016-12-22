---
title: "XML comment exception must have a &#39;cref&#39; attribute | Microsoft Docs"
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
  - "bc42319"
  - "vbc42319"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42319"
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML comment exception must have a &#39;cref&#39; attribute
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

\<exception\> 태그는 메서드에서 throw할 수 있는 예외를 문서화하는 방법을 제공합니다.  필수 `cref` 특성은 설명서 생성기에서 확인하는 멤버의 이름을 지정합니다.  멤버가 있는 경우 멤버는 문서 파일에서 정규 요소 이름으로 변환됩니다.  
  
 **오류 ID:** BC42319  
  
### 이 오류를 해결하려면  
  
-   다음과 같이 `cref` 특성을 예외에 추가합니다.  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## 참고 항목  
 [\<exception\>](../../../visual-basic/language-reference/xmldoc/exception.md)   
 [How to: Create XML Documentation](../Topic/How%20to:%20Create%20XML%20Documentation%20in%20Visual%20Basic.md)   
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)