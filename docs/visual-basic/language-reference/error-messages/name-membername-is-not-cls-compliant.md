---
title: "Name &lt;membername&gt; is not CLS-compliant | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc40031"
  - "vbc40031"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40031"
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Name &lt;membername&gt; is not CLS-compliant
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

어셈블리가 `<CLSCompliant(True)>`로 표시되지만 밑줄\(`_`\)로 시작하는 이름의 멤버를 노출합니다.  
  
 프로그래밍 요소는 하나 이상의 밑줄을 포함할 수 있지만 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\) 규격이어야 하므로 밑줄로 시작하지 않아야 합니다.  [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)를 참조하십시오.  
  
 <xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 이 특성의 `isCompliant` 매개 변수를 `True`나 `False`로 설정하여 규격 준수 여부를 나타내야 합니다.  이 매개 변수의 기본값이 없으므로 값을 제공해야 합니다.  
  
 <xref:System.CLSCompliantAttribute>를 요소에 적용하지 않으면 이 요소는 CLS 규격이 아닌 것으로 간주됩니다.  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC40031  
  
### 이 오류를 해결하려면  
  
-   소스 코드를 제어할 수 있는 경우 멤버 이름이 밑줄로 시작하지 않도록 이름을 변경합니다.  
  
-   멤버 이름을 변경하지 않고 유지해야 할 경우 해당 정의에서 <xref:System.CLSCompliantAttribute>를 제거하거나 이 특성을 `<CLSCompliant(False)>`로 표시합니다.  그러면 어셈블리를 여전히 `<CLSCompliant(True)>`로 표시할 수 있습니다.  
  
## 참고 항목  
 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)