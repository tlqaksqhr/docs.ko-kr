---
title: "&#39;&lt;elementname&gt;&#39; is obsolete (Visual Basic Warning) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc40008"
  - "bc40008"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40008"
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# &#39;&lt;elementname&gt;&#39; is obsolete (Visual Basic Warning)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

문에서 <xref:System.ObsoleteAttribute> 특성으로 표시된 프로그래밍 요소에 액세스하려고 하면 지시문에서 이를 경고로 처리합니다.  
  
 사용하지 않는 프로그래밍 요소의 경우 <xref:System.ObsoleteAttribute>를 적용하여 더 이상 사용하지 않는 요소로 표시할 수 있습니다.  이렇게 하는 경우 특성의 <xref:System.ObsoleteAttribute.IsError%2A> 속성을 `True` 또는 `False`로 설정할 수 있습니다.  `True`로 설정하면 요소를 사용하려는 시도를 컴파일러가 오류로 처리합니다.  `False`로 설정하거나 기본값인 `False`로 두면 요소를 사용하려는 시도가 있을 경우 컴파일러가 경고를 발생시킵니다.  
  
 <xref:System.ObsoleteAttribute>의 <xref:System.ObsoleteAttribute.IsError%2A> 속성이 `False`이기 때문에 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC40008  
  
### 이 오류를 해결하려면  
  
-   소스 코드 참조에서 요소 이름의 철자가 올바른지 확인합니다.  
  
## 참고 항목  
 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)