---
title: "&#39;&lt;membername&gt;&#39; cannot expose type &#39;&lt;typename&gt;&#39; outside the project through &lt;containertype&gt; &#39;&lt;containertypename&gt;&#39; | Microsoft Docs"
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
  - "bc30909"
  - "vbc30909"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30909"
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;membername&gt;&#39; cannot expose type &#39;&lt;typename&gt;&#39; outside the project through &lt;containertype&gt; &#39;&lt;containertypename&gt;&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

변수, 프로시저 매개 변수 또는 함수 반환이 해당 컨테이너 외부로 노출되어 있지만 원래는 컨테이너 외부로 노출되면 안 되는 형식으로 선언되었습니다.  
  
 다음 기초 코드에서는 이러한 오류가 발생하는 경우를 보여 줍니다.  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 `Protected`, `Friend`, `Protected Friend` 또는 `Private`으로 선언된 형식의 액세스는 해당 선언 컨텍스트의 외부에서 제한되어 있습니다.  이 형식을 액세스가 덜 제한된 변수의 데이터 형식으로 사용하면 용도에 맞지 않게 됩니다.  앞의 기초 코드에서 `exposedVar`는 `Public`이므로 `privateClass`를 이에 대한 액세스 권한이 없어야 하는 코드에 노출합니다.  
  
 **오류 ID:** BC30909  
  
### 이 오류를 해결하려면  
  
-   변수, 프로시저 매개 변수 또는 함수 반환의 액세스 수준을 적어도 해당 데이터 형식의 액세스 수준만큼 제한합니다.  
  
## 참고 항목  
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)