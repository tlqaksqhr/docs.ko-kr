---
title: "First statement of this &#39;Sub New&#39; must be a call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; (No Accessible Constructor Without Parameters) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30148"
  - "vbc30148"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30148"
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# First statement of this &#39;Sub New&#39; must be a call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; (No Accessible Constructor Without Parameters)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

'\<derivedname\>'의 기본 클래스 '\<basename\>'에 인수 없이 호출할 수 있는 액세스 가능한 'Sub New'가 없으므로 이 'Sub New'의 첫째 문은 'MyBase.New' 또는 'MyClass.New'에 대한 호출이어야 합니다.  
  
 파생 클래스에서 모든 생성자는 기본 클래스 생성자\(`MyBase.New`\)를 호출해야 합니다.  파생 클래스에 액세스 가능한 매개 변수가 없는 생성자가 기본 클래스에 있으면 `MyBase.New`를 자동으로 호출할 수 있습니다.  그렇지 않으면 기본 클래스 생성자는 매개 변수를 사용하여 직접 호출해야 합니다.  이 경우 모든 파생 클래스 생성자의 첫째 문은 기본 클래스에서 매개 변수가 있는 생성자를 호출하거나 기본 클래스 생성자를 호출하는 파생 클래스의 다른 생성자를 호출해야 합니다.  
  
 **오류 ID:** BC30148  
  
### 이 오류를 해결하려면  
  
-   필요한 매개 변수를 지정하여 `MyBase.New`를 호출하거나 이러한 호출을 수행하는 피어 생성자를 호출합니다.  
  
     예를 들어, 기본 클래스 생성자로 선언 된 경우 `Public Sub New(ByVal index as Integer)`, 첫 번째 문에서 파생된 클래스 생성자가 수 `MyBase.New(100)`.  
  
## 참고 항목  
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)