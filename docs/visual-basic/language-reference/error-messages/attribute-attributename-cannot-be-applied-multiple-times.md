---
title: "Attribute &#39;&lt;attributename&gt;&#39; cannot be applied multiple times | Microsoft Docs"
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
  - "bc30663"
  - "vbc30663"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30663"
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Attribute &#39;&lt;attributename&gt;&#39; cannot be applied multiple times
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

특성은 한 번만 적용할 수 있습니다.  `AttributeUsage` 특성은 특성을 두 번 이상 적용할 수 있는지 여부를 결정합니다.  
  
 **오류 ID:** BC30663  
  
### 이 오류를 해결하려면  
  
1.  특성을 한 번만 적용하도록 합니다.  
  
2.  직접 개발한 사용자 지정 특성을 사용하는 경우 `AttributeUsage` 특성을 여러 번 사용할 수 있도록 다음 예제에서와 같이 변경해 봅니다.  
  
    ```  
    <AttributeUsage(AllowMultiple := True)>  
    ```  
  
## 참고 항목  
 <xref:System.AttributeUsageAttribute>   
 [사용자 지정 특성 만들기](../Topic/Creating%20Custom%20Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [AttributeUsage](../Topic/AttributeUsage%20\(C%23%20and%20Visual%20Basic\).md)