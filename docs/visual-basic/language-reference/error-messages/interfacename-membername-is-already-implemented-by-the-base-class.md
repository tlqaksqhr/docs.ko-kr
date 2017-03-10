---
title: "&#39;&lt;interfacename&gt;.&lt;membername&gt;&#39; is already implemented by the base class &#39;&lt;baseclassname&gt;&#39;. Re-implementation of &lt;type&gt; assumed | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc42015"
  - "bc42015"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42015"
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# &#39;&lt;interfacename&gt;.&lt;membername&gt;&#39; is already implemented by the base class &#39;&lt;baseclassname&gt;&#39;. Re-implementation of &lt;type&gt; assumed
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

파생 클래스의 속성, 프로시저 또는 이벤트는 `Implements` 절을 사용하여 기본 클래스에 이미 구현된 인터페이스 멤버를 지정합니다.  
  
 파생 클래스는 해당 기본 클래스에 의해 구현된 인터페이스 멤버를 다시 구현할 수 있습니다.  이는 기본 클래스 구현을 재정의하는 것과는 다릅니다.  자세한 내용은 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)를 참조하십시오.  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC42015  
  
### 이 오류를 해결하려면  
  
-   인터페이스 멤버를 다시 구현하려는 경우에는 아무런 작업을 수행하지 않아도 됩니다.  파생 클래스의 코드에서는 사용자가 `MyBase` 키워드를 사용하여 기본 클래스 구현에 액세스하지 않는 한 재구현된 멤버에 액세스합니다.  
  
-   인터페이스 멤버를 다시 구현하지 않으려면 속성, 프로시저 또는 이벤트 선언에서 `Implements` 절을 제거합니다.  
  
## 참고 항목  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)