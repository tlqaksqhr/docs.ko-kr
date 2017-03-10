---
title: "Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc40033"
  - "vbc40033"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40033"
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

CLS 규격 관련 표시가 없거나 `<CLSCompliant(False)>`로 표시된 인터페이스의 속성, 프로시저 또는 이벤트가 `<CLSCompliant(True)>`로 표시되어 있습니다.  
  
 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\) 규격인 인터페이스의 경우 모든 해당 멤버가 해당 규격을 준수해야 합니다.  
  
 <xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 이 특성의 `isCompliant` 매개 변수를 `True`나 `False`로 설정하여 규격 준수 여부를 나타내야 합니다.  이 매개 변수의 기본값이 없으므로 값을 제공해야 합니다.  
  
 <xref:System.CLSCompliantAttribute>를 요소에 적용하지 않으면 이 요소는 CLS 규격이 아닌 것으로 간주됩니다.  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC40033  
  
### 이 오류를 해결하려면  
  
-   CLS 규격이 필요하고 인터페이스 소스 코드를 제어할 수 있는 경우 인터페이스의 모든 멤버가 CLS 규격을 준수하면 해당 인터페이스를 `<CLSCompliant(True)>`로 표시합니다.  
  
-   CLS 규격이 필요하고 인터페이스 소스 코드를 제어할 수 없거나 인터페이스가 CLS 규격이 되도록 한정되지 않는 경우에는 이 멤버를 다른 인터페이스 내에 정의합니다.  
  
-   이 멤버가 현재 인터페이스 내에 있어야 하는 경우 해당 정의에서 <xref:System.CLSCompliantAttribute>를 제거하거나 이 인터페이스를 `<CLSCompliant(False)>`로 표시합니다.  
  
## 참고 항목  
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)