---
title: "Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30369"
  - "bc30369"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Shared"
  - "BC30369"
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

공유 프로시저에서 클래스의 비공유 멤버를 참조하려고 했습니다.  다음 예제에서는 이러한 상황을 보여 줍니다.  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 앞의 예제에서는 `x = 10` 대입문에서 이 오류 메시지를 생성합니다.  그 이유는 공유 프로시저가 인스턴스 변수에 액세스하려고 했기 때문입니다.  
  
 `x` 변수는 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)로 선언되지 않았으므로 인스턴스 멤버입니다.  `sample` 클래스의 각 인스턴스에는 고유한 개별 변수 `x`가 있습니다.  특정 인스턴스에서 `x`의 값을 설정하거나 변경해도 다른 인스턴스의 `x` 값에는 영향을 미치지 않습니다.  
  
 그러나 `setX` 프로시저는 `sample` 클래스의 모든 인스턴스에서 `Shared` 요소입니다.  따라서 이 프로시저는 클래스의 어느 인스턴스와도 연관되지 않고 각 인스턴스와 독립적으로 작동합니다.  `setX`는 특정 인스턴스와 연결되지 않으므로 인스턴스 변수에 액세스할 수 없습니다.  이 프로시저는 `Shared` 변수에 대해서만 작동해야 합니다.  `setX`가 공유 변수의 값을 설정하거나 변경하면 클래스의 모든 인스턴스에 새 값을 사용할 수 있습니다.  
  
 **오류 ID:** BC30369  
  
### 이 오류를 해결하려면  
  
1.  멤버를 모든 인스턴스에서 공유할지 아니면 각 인스턴스에 대해 개별적으로 사용할지 결정합니다.  
  
2.  멤버의 복사본 하나를 모든 인스턴스에서 공유하려면 멤버 선언에 `Shared` 키워드를 추가합니다.  프로시저 선언에 `Shared` 키워드를 그대로 유지합니다.  
  
3.  각 인스턴스에 멤버의 고유한 개별 복사본을 사용하려면 멤버 선언에 `Shared`를 지정하지 않습니다.  프로시저 선언에서 `Shared` 키워드를 제거합니다.  
  
## 참고 항목  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)