---
title: "&#39;&lt;attribute&gt;&#39; cannot be applied because the format of the GUID &#39;&lt;number&gt;&#39; is not correct | Microsoft Docs"
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
  - "vbc32500"
  - "bc32500"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32500"
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;attribute&gt;&#39; cannot be applied because the format of the GUID &#39;&lt;number&gt;&#39; is not correct
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`COMClassAttribute` 특성 블록에서 적절한 형식에 맞지 않는 GUID\(Globally Unique Identifier\)를 지정합니다.  `COMClassAttribute`는 GUID를 사용하여 클래스, 인터페이스 및 생성 이벤트를 고유하게 식별합니다.  
  
 GUID는 처음 8바이트는 숫자이고 나머지 8바이트는 이진 형식인 16바이트로 구성되며,  uuidgen.exe와 같은 Microsoft 유틸리티에 의해 생성되고 시간과 공간에 있어 항상 고유합니다.  
  
 **오류 ID:** BC32500  
  
### 이 오류를 해결하려면  
  
1.  COM 개체를 식별하는 데 필요한 올바른 GUID를 결정하십시오.  
  
2.  `COMClassAttribute` 특성 블록에 있는 GUID 문자열이 올바로 복사되었는지 확인합니다.  
  
## 참고 항목  
 <xref:System.Guid>   
 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)