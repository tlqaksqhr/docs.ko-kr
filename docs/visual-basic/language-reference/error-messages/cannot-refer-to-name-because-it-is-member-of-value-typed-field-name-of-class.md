---
title: "Cannot refer to &#39;&lt;name&gt;&#39; because it is a member of the value-typed field &#39;&lt;name&gt;&#39; of class &#39;&lt;classname&gt;&#39; which has &#39;System.MarshalByRefObject&#39; as a base class | Microsoft Docs"
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
  - "vbc30310"
  - "bc30310"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30310"
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Cannot refer to &#39;&lt;name&gt;&#39; because it is a member of the value-typed field &#39;&lt;name&gt;&#39; of class &#39;&lt;classname&gt;&#39; which has &#39;System.MarshalByRefObject&#39; as a base class
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`System.MarshalByRefObject` 클래스를 사용하면 원격을 지원하는 응용 프로그램에서 응용 프로그램 도메인 경계를 벗어나는 개체에 액세스할 수 있습니다.  형식이 응용 프로그램 도메인 경계를 벗어나서 사용될 경우 해당 형식은 `MarshalByRejectObject` 클래스에서 상속해야 합니다.  개체의 멤버는 해당 멤버가 만들어진 응용 프로그램 도메인 외부에서 사용할 수 없으므로 개체 상태를 복사하면 안 됩니다.  
  
 **오류 ID:** BC30310  
  
### 이 오류를 해결하려면  
  
1.  참조를 검사하여 참조되는 멤버가 유효한지 확인하십시오.  
  
2.  `Me` 키워드를 사용하여 멤버를 명시적으로 한정하십시오.  
  
## 참고 항목  
 <xref:System.MarshalByRefObject>   
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)