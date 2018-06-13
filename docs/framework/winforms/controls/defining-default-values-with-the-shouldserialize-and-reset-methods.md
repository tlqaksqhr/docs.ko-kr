---
title: ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: 8d7645e8de5edee711c30bbe7edde8ba7b5b1dab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529794"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의
`ShouldSerialize` 및 `Reset` 속성이 없는 경우 속성에 대해 제공할 수 있는 선택적 메서드는는 간단한 기본값을 가집니다. 속성에 기본값을 적용 해야는 <xref:System.ComponentModel.DefaultValueAttribute> 특성 클래스 생성자에 기본값을 대신 제공 합니다. 이러한 메커니즘 중 하나를 통해 디자이너에서 다음과 같은 기능 수 있습니다.  
  
-   속성 값이 기본값에서 수정 된 경우 속성 브라우저에서 시각적 표시를 제공 합니다.  
  
-   사용자 속성을 마우스 오른쪽 단추로 클릭 하 고 선택할 수 **재설정** 속성을 기본값으로 복원 합니다.  
  
-   디자이너는 보다 효율적인 코드를 생성합니다.  
  
    > [!NOTE]
    >  적용 중 하나는 <xref:System.ComponentModel.DefaultValueAttribute> 제공 또는 `Reset` *PropertyName* 및 `ShouldSerialize` *PropertyName* 메서드. 둘 다 사용 하지 마십시오.  
  
 `Reset` *PropertyName* 메서드 다음 코드 조각에 나와 있는 것 처럼 속성을 해당 기본값으로 설정 합니다.  
  
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
>  속성이 없는 경우는 `Reset` 메서드를로 표시 되지 않으면는 <xref:System.ComponentModel.DefaultValueAttribute>, 선언에 제공 되는 기본 값이 없으면는 `Reset` 의 바로 가기 메뉴에서 해당 속성이 사용 되지 않는지에 대 한 옵션는 **속성** Visual Studio에서 Windows Forms 디자이너의 창.  
  
 Visual Studio와 같은 디자이너 사용 하 여는 `ShouldSerialize` *PropertyName* 속성이 기본값에서 변경 되었는지 여부를 확인 하 고 속성 경우에만 폼에 코드를 작성 하는 방법을 변경 되 면 되므로 보다 효율적인 코드 세대입니다. 예를 들어:  
  
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
  
 전체 코드 예제와 같습니다.  
  
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
  
 개인 변수의 값으로 액세스 하는 경우에이 경우에는 `MyFont` 속성은 `null`, 속성 브라우저에 표시 되지 `null`대신 표시는 <xref:System.Windows.Forms.Control.Font%2A> 없는 경우 부모 `null`, 또는 기본 <xref:System.Windows.Forms.Control.Font%2A> 에 정의 된 값 <xref:System.Windows.Forms.Control>합니다. 에 대 한 기본값에 따라서 `MyFont` 간단히 설정할 수 없습니다 및 <xref:System.ComponentModel.DefaultValueAttribute> 이 속성에 적용할 수 없습니다. 대신,는 `ShouldSerialize` 및 `Reset` 에 대 한 메서드를 구현 해야 합니다는 `MyFont` 속성입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 컨트롤의 속성](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [속성 정의](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 [속성 변경 이벤트](../../../../docs/framework/winforms/controls/property-changed-events.md)
