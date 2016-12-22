---
title: "How to: Determine Whether Two Objects Are Related (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "inheritance, Visual Basic objects"
  - "objects [Visual Basic], inheritance"
  - "object variables, determining relation"
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Determine Whether Two Objects Are Related (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

두 개체를 비교하여 두 개체가 만들어진 클래스 간의 관계를 확인할 수 있습니다.  <xref:System.Type?displayProperty=fullName> 클래스의 <xref:System.Type.IsInstanceOfType%2A> 메서드는 지정된 클래스가 현재 클래스에서 상속된 클래스이거나 현재 형식이 지정된 클래스에서 지원하는 인터페이스이면 `True`를 반환합니다.  
  
### 한 개체가 다른 개체의 클래스 또는 인터페이스에서 상속하는지 여부를 확인하려면  
  
1.  기본 형식이라고 생각되는 개체에 대해 <xref:System.Object.GetType%2A> 메서드를 호출합니다.  
  
2.  <xref:System.Object.GetType%2A>에서 반환된 <xref:System.Type?displayProperty=fullName> 개체에 대해 <xref:System.Type.IsInstanceOfType%2A> 메서드를 호출합니다.  
  
3.  <xref:System.Type.IsInstanceOfType%2A>의 인수 목록에서 파생된 형식이라고 생각되는 개체를 지정합니다.  
  
     지정한 개체의 인수 형식이 <xref:System.Type?displayProperty=fullName> 개체 형식에서 상속하면 <xref:System.Type.IsInstanceOfType%2A>은 `True`를 반환합니다.  
  
## 예제  
 다음 예제에서는 한 개체가 다른 개체의 클래스에서 파생된 클래스를 나타내는지 여부를 확인합니다.  
  
```  
Public Class baseClass  
End Class  
Public Class derivedClass : Inherits baseClass  
End Class  
Public Class testTheseClasses  
    Public Sub seeIfRelated()  
        Dim baseObj As Object = New baseClass()  
        Dim derivedObj As Object = New derivedClass()  
        Dim related As Boolean  
        related = baseObj.GetType().IsInstanceOfType(derivedObj)  
        MsgBox(CStr(related))  
    End Sub  
End Class  
```  
  
 <xref:System.Type.IsInstanceOfType%2A>을 호출할 때는 두 개체 변수의 위치에 주의해야 합니다.  예상되는 기본 형식은 <xref:System.Type?displayProperty=fullName> 클래스를 생성하는 데 사용되고 예상되는 파생 형식은 <xref:System.Type.IsInstanceOfType%2A> 메서드에 인수로 전달됩니다.  
  
## 참고 항목  
 <xref:System.Object.GetType%2A>   
 <xref:System.Type?displayProperty=fullName>   
 <xref:System.Type.IsInstanceOfType%2A>   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [How to: Determine Whether Two Objects Are Identical](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)