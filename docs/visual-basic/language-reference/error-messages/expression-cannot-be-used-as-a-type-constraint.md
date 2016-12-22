---
title: "&#39;&lt;expression&gt;&#39; cannot be used as a type constraint | Microsoft Docs"
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
  - "bc32061"
  - "vbc32061"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32061"
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;expression&gt;&#39; cannot be used as a type constraint
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

제약 조건 목록에 형식 매개 변수에 유효한 제약 조건을 나타내지 않는 식이 포함되어 있습니다.  
  
 제약 조건 목록은 형식 매개 변수에 전달되는 형식 인수에 대한 요구 사항을 규정합니다.  다음 요구 사항을 조합하여 지정할 수 있습니다.  
  
-   형식 인수는 하나 이상의 인터페이스를 구현해야 합니다.  
  
-   형식 인수는 한 클래스에서만 상속해야 합니다.  
  
-   형식 인수는 만드는 코드에서 액세스할 수 있는 매개 변수 없는 생성자를 노출해야 합니다\(`New` 제약 조건 포함\).  
  
 제약 조건 목록에 특정 클래스나 인터페이스를 포함하지 않는 경우 다음 중 하나를 지정하여 일반 요구 사항을 적용할 수 있습니다.  
  
-   형식 인수는 값 형식이어야 합니다\(`Structure` 제약 조건 포함\).  
  
-   형식 인수는 참조 형식이어야 합니다\(`Class` 제약 조건 포함\).  
  
 동일한 형식 매개 변수에 대해 `Structure` 및 `Class`를 함께 지정할 수 없으며 둘 중 하나를 두 번 이상 지정할 수도 없습니다.  
  
 **오류 ID:** BC32061  
  
### 이 오류를 해결하려면  
  
-   식과 식의 요소에 대한 맞춤법이 올바른지 확인합니다.  
  
-   식이 위에 나열한 요구 사항에 맞지 않는 경우 이 식을 제약 조건 목록에서 제거합니다.  
  
-   식에서 인터페이스나 클래스를 참조하는 경우 컴파일러에 해당 인터페이스나 클래스에 대한 액세스 권한이 있는지 확인합니다.  해당 이름을 한정하고 프로젝트에 참조를 추가해야 할 수 있습니다.  자세한 내용은 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)의 "프로젝트에 대한 참조"를 참조하십시오.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Value Types and Reference Types](../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)