---
title: "Default property access is ambiguous between the inherited interface members &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename1&gt;&#39; and &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename2&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30686"
  - "bc30686"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30686"
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Default property access is ambiguous between the inherited interface members &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename1&gt;&#39; and &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename2&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

인터페이스는 각각 이름이 같은 기본 속성을 선언하는 두 인터페이스에서 상속됩니다.  컴파일러에서 한정자 없이 이 기본 속성에 대한 액세스를 확인할 수 없습니다.  다음은 이에 대한 예입니다.  
  
```  
Public Interface Iface1  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface2  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface3  
    Inherits Iface1, Iface2  
End Interface  
Public Class testClass  
    Public Sub accessDefaultProperty()  
        Dim testObj As Iface3  
        Dim testInt As Integer = testObj(1)  
    End Sub  
End Class  
```  
  
 `testObj(1)`를 지정하면 컴파일러에서 기본 속성으로 확인하려고 하지만,  상속된 인터페이스로 인해 두 개의 기본 속성을 사용할 수 있으므로 컴파일러에서 이 오류를 알립니다.  
  
 **오류 ID:** BC30686  
  
### 이 오류를 해결하려면  
  
-   이름이 같은 멤버를 상속하지 않습니다.  앞의 예제에서 `testObj`에 `Iface2` 등의 멤버가 필요 없을 경우 다음과 같이 선언합니다.  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     또는  
  
-   상속하는 인터페이스를 클래스에 구현합니다.  그러면 상속된 각 속성을 다른 이름으로 구현할 수 있습니다.  그러나 상속된 속성 중 하나만 구현하는 클래스의 기본 속성이 될 수 있습니다.  다음은 이에 대한 예입니다.  
  
    ```  
    Public Class useIface3  
        Implements Iface3  
        Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop  
            ' Insert code to define Get and Set procedures for prop1.  
        End Property  
        Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop  
            ' Insert code to define Get and Set procedures for prop2.  
        End Property  
    End Class  
    ```  
  
## 참고 항목  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)