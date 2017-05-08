---
title: "ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "사용자 지정 컨트롤[Windows Forms], 속성 메서드"
  - "Reset 메서드"
  - "ShouldPersist 메서드"
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의
속성에 간단한 기본값이 없을 경우 `ShouldSerialize` 및 `Reset` 메서드를 선택적으로 해당 속성에 제공할 수 있습니다.  그러나 속성에 간단한 기본값이 있는 경우에는 <xref:System.ComponentModel.DefaultValueAttribute>를 적용하고 해당 기본값을 특성 클래스 생성자에 대신 제공해야 합니다.  어떠한 메커니즘을 사용하더라도 디자이너에서는 다음 기능을 수행할 수 있습니다.  
  
-   속성이 기본값에서 수정되면 속성 브라우저에 시각적으로 표시됩니다.  
  
-   속성을 마우스 오른쪽 단추로 클릭하고 **다시 설정**을 선택하여 속성의 기본값을 복원할 수 있습니다.  
  
-   디자이너에서 보다 효율적인 코드를 만듭니다.  
  
    > [!NOTE]
    >  <xref:System.ComponentModel.DefaultValueAttribute>를 적용하거나 `Reset`*PropertyName* 및 `ShouldSerialize`*PropertyName* 메서드를 제공합니다.  두 가지를 함께 사용하지 마십시오.  
  
 `Reset` *PropertyName* 메서드는 아래 코드 조각에 표시된 것처럼 속성을 기본값으로 설정합니다.  
  
```vb  
Public Sub ResetMyFont()  
   MyFont = Nothing  
End Sub  
```  
  
```csharp  
public void ResetMyFont() {  
   MyFont = null;  
}  
```  
  
> [!NOTE]
>  속성에 `Reset` 메서드가 없고, 속성이 <xref:System.ComponentModel.DefaultValueAttribute>로 표시되어 있지 않고, 해당 선언에 기본값이 없는 경우, [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]의 Windows Forms 디자이너에 있는 **속성** 창의 바로 가기 메뉴에서 해당 속성에 대해 `Reset` 옵션을 사용할 수 없습니다.  
  
 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]와 같은 디자이너에서는 `ShouldSerialize`*PropertyName* 메서드를 사용하여 속성이 기본값에서 변경되었는지 여부를 확인하고 속성이 변경된 경우에만 해당 폼 안에 코드를 작성하여 보다 효율적으로 코드를 생성합니다.  예를 들면 다음과 같습니다.  
  
```vb  
'Returns true if the font has changed; otherwise, returns false.  
' The designer writes code to the form only if true is returned.  
Public Function ShouldSerializeMyFont() As Boolean  
   Return Not (thefont Is Nothing)  
End Function  
```  
  
```csharp  
// Returns true if the font has changed; otherwise, returns false.  
// The designer writes code to the form only if true is returned.  
public bool ShouldSerializeMyFont() {  
   return thefont != null;  
}  
```  
  
 전체 코드 예제는 다음과 같습니다.  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class MyControl  
   Inherits Control  
  
   ' Declare an instance of the Font class  
   ' and set its default value to Nothing.  
   Private thefont As Font = Nothing  
  
   ' The MyFont property.   
   Public Property MyFont() As Font  
      ' Note that the Font property never  
      ' returns null.  
      Get  
         If Not (thefont Is Nothing) Then  
            Return thefont  
         End If  
         If Not (Parent Is Nothing) Then  
            Return Parent.Font  
         End If  
         Return Control.DefaultFont  
      End Get  
      Set  
         thefont = value  
      End Set  
   End Property  
  
   Public Function ShouldSerializeMyFont() As Boolean  
      Return Not (thefont Is Nothing)  
   End Function  
  
   Public Sub ResetMyFont()  
      MyFont = Nothing  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class MyControl : Control {  
   // Declare an instance of the Font class  
   // and set its default value to null.  
   private Font thefont = null;  
  
   // The MyFont property.      
   public Font MyFont {  
      // Note that the MyFont property never  
      // returns null.  
      get {  
         if (thefont != null) return thefont;  
         if (Parent != null) return Parent.Font;  
         return Control.DefaultFont;  
      }  
      set {  
         thefont = value;  
      }  
   }  
  
   public bool ShouldSerializeMyFont() {  
      return thefont != null;  
   }  
  
   public void ResetMyFont() {  
      MyFont = null;  
   }  
}  
```  
  
 이 경우 `MyFont` 속성에서 액세스한 전용 변수 값이 `null`이더라도 속성 브라우저는 `null`을 표시하지 않습니다. 대신 부모의 <xref:System.Windows.Forms.Control.Font%2A> 속성이 `null`이 아닌 경우 이 속성을 표시하거나 <xref:System.Windows.Forms.Control>에 정의된 기본 <xref:System.Windows.Forms.Control.Font%2A> 값을 표시합니다.  따라서 `MyFont` 기본값은 간단하게 설정할 수 없고 이 속성에 <xref:System.ComponentModel.DefaultValueAttribute>를 적용할 수 없습니다.  대신 `MyFont` 속성에 대해 `ShouldSerialize` 및 `Reset` 메서드를 구현해야 합니다.  
  
## 참고 항목  
 [Windows Forms 컨트롤의 속성](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [속성 정의](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)   
 [속성 변경 이벤트](../../../../docs/framework/winforms/controls/property-changed-events.md)