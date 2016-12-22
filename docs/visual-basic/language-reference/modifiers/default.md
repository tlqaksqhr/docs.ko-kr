---
title: "Default (Visual Basic) | Microsoft Docs"
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
  - "vb.Default"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "defaults, properties"
  - "properties [Visual Basic], default"
  - "default properties, in Visual Basic"
  - "Default keyword [Visual Basic]"
  - "default properties"
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Default (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

속성을 해당 클래스, 구조체 또는 인터페이스의 기본 속성으로 식별합니다.  
  
## 설명  
 클래스, 구조체 또는 인터페이스는 해당 속성 중 하나만 *기본 속성*으로 지정할 수 있습니다. 이때 해당 속성은 매개 변수를 하나 이상 사용해야 합니다.  코드에서 멤버를 지정하지 않고 클래스나 구조체를 참조하면 Visual Basic에서 해당 참조는 기본 속성으로 확인됩니다.  
  
 기본 속성을 사용하면 소스 코드 문자 수가 약간 줄어들 수 있지만 코드를 읽기가 더 어려워질 수 있습니다.  호출하는 코드에서 사용자의 클래스나 구조체를 잘 모르는 데 클래스나 구조체 이름을 참조하는 경우 해당 참조가 클래스나 구조체 자체를 참조하는지, 아니면 기본 속성을 참조하는지 확실히 알 수 없습니다.  이 경우에는 컴파일러 오류나 모호한 런타임 논리 오류가 발생할 수 있습니다.  
  
 항상 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)을 사용하여 컴파일러 형식 검사를 `On`으로 설정하면 기본 속성 오류가 발생할 가능성을 다소 줄일 수 있습니다.  
  
 코드에서 미리 정의된 클래스나 구조체를 사용할 계획이라면 기본 속성을 갖고 있는지, 갖고 있다면 이름이 무엇인지 확인해야 합니다.  
  
 이러한 단점으로 인해서 기본 속성을 정의하지 않는 것을 고려할 필요가 있습니다.  또한 코드 가독성을 위해 모든 속성, 심지어 기본 속성까지도 항상 명시적으로 참조하는 것을 고려해야 합니다.  
  
 `Default` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## 참고 항목  
 [How to: Declare and Call a Default Property in Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)