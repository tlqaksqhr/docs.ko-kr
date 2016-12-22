---
title: "WriteOnly (Visual Basic) | Microsoft Docs"
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
  - "WriteOnly"
  - "vb.WriteOnly"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "write-only properties"
  - "WriteOnly keyword"
  - "sensitive data, protecting"
  - "properties [Visual Basic], write-only"
  - "sensitive data"
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# WriteOnly (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

속성을 쓸 수는 있지만 읽을 수는 없도록 지정합니다.  
  
## 설명  
  
## 규칙  
 **선언 컨텍스트.** `WriteOnly` 키워드는 모듈 수준에서만 사용할 수 있습니다.  즉, `WriteOnly` 속성의 선언 컨텍스트는 클래스, 구조체 또는 모듈이어야 하며, 소스 파일, 네임스페이스 또는 프로시저일 수는 없습니다.  
  
 속성을 `WriteOnly`로 선언할 수 있지만 변수로는 선언할 수 없습니다.  
  
## WriteOnly 사용 시기  
 사용하는 코드에서 값을 설정할 수는 있어도 확인하지는 못하도록 해야 할 경우가 있습니다.  예를 들어, 주민 등록 번호나 암호 같은 중요한 데이터는 해당 데이터를 설정하지 않은 구성 요소에서 액세스하지 못하도록 보호해야 합니다.  이러한 경우 `WriteOnly` 속성을 사용하여 값을 설정할 수 있습니다.  
  
> [!IMPORTANT]
>  `WriteOnly` 속성을 정의하고 사용할 때는 다음과 같은 추가적인 보안 방법을 고려하십시오.  
  
-   **재정의.** 속성이 클래스의 멤버이면 기본값이 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)로 지정될 수 있도록 하고, `Overridable`이나 `MustOverride`로는 선언하지 않습니다.  이렇게 하면 재정의를 통해 파생 클래스에 무단 액세스하는 것을 막을 수 있습니다.  
  
-   **액세스 수준.** 속성의 중요한 데이터를 하나 이상의 변수에 저장할 경우 다른 코드에서 액세스하지 못하도록 변수를 [Private](../../../visual-basic/language-reference/modifiers/private.md)으로 선언합니다.  
  
-   **암호화.** 중요한 모든 데이터를 일반 텍스트가 아닌 암호화된 형식으로 저장하면  악의적인 코드를 통해 메모리의 해당 영역에 대한 액세스 권한을 얻게 되더라도 데이터를 사용하기가 어렵습니다.  중요한 데이터를 serialize해야 하는 경우에도 암호화가 유용합니다.  
  
-   **다시 설정.** 속성을 정의하는 클래스, 구조체 또는 모듈이 종료될 때는 중요한 데이터를 기본값이나 그 밖의 의미 없는 값으로 다시 설정합니다.  이렇게 하면 메모리의 해당 영역에 대한 일반 액세스가 허용될 경우 추가적인 보안이 적용됩니다.  
  
-   **지속성.** 가능하면 중요한 데이터를 디스크 같은 곳에 지속적으로 보관하지 않습니다.  또한 중요한 데이터를 클립보드에 기록하지 않습니다.  
  
 `WriteOnly` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## 참고 항목  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)