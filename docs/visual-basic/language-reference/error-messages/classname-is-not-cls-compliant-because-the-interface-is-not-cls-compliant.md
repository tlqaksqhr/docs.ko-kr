---
title: "&#39;&lt;classname&gt;&#39; is not CLS-compliant because the interface &#39;&lt;interfacename&gt;&#39; it implements is not CLS-compliant | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc40029"
  - "vbc40029"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40029"
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# &#39;&lt;classname&gt;&#39; is not CLS-compliant because the interface &#39;&lt;interfacename&gt;&#39; it implements is not CLS-compliant
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

CLS 규격 관련 표시가 없거나 `<CLSCompliant(False)>`로 표시된 형식에서 파생되거나 이러한 형식을 구현하는 클래스나 인터페이스가 `<CLSCompliant(True)>`로 표시되어 있습니다.  
  
 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\) 규격인 클래스나 인터페이스의 경우 전체 상속 계층 구조가 해당 규격을 준수해야 합니다.  즉, 클래스나 인스턴스가 직접 또는 간접적으로 상속되는 모든 형식이 CLS 규격이어야 합니다.  마찬가지로, 클래스가 하나 이상의 인터페이스를 구현하는 경우 상속 계층 구조 전체에서 해당 인터페이스가 CLS 규격을 준수해야 합니다.  
  
 <xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 이 특성의 `isCompliant` 매개 변수를 `True`나 `False`로 설정하여 규격 준수 여부를 나타내야 합니다.  이 매개 변수의 기본값이 없으므로 값을 제공해야 합니다.  
  
 <xref:System.CLSCompliantAttribute>를 요소에 적용하지 않으면 이 요소는 CLS 규격이 아닌 것으로 간주됩니다.  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC40029  
  
### 이 오류를 해결하려면  
  
-   CLS 규격이 필요하면 다른 상속 계층 구조나 구현 체계에서 이 형식을 정의합니다.  
  
-   이 형식이 현재 상속 계층 구조나 구현 체계 내에 있어야 하는 경우 해당 정의에서 <xref:System.CLSCompliantAttribute>를 제거하거나 이 특성을 `<CLSCompliant(False)>`로 표시합니다.  
  
## 참고 항목  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)