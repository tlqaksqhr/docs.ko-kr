---
title: "Windows Forms 컨트롤에서 속성 정의 | Microsoft Docs"
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
  - "사용자 지정 컨트롤[Windows Forms], 코드에서 속성 정의"
  - "속성[Windows Forms], 코드에서 정의"
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Windows Forms 컨트롤에서 속성 정의
속성에 대한 개요를 보려면 [속성 개요](../Topic/Properties%20Overview.md)를 참조하십시오.  속성을 정의할 경우 고려해야 할 몇 가지 중요한 사항은 다음과 같습니다.  
  
-   정의한 속성에 특성을 적용해야 합니다.  특성은 디자이너에서 속성을 표시하는 방법을 지정합니다.  자세한 내용은 [구성 요소의 디자인 타임 특성](../Topic/Design-Time%20Attributes%20for%20Components.md)을 참조하십시오.  
  
-   속성 변경 시 컨트롤의 시각적 표시에 영향을 줄 경우 `set` 접근자에서 <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드\(컨트롤이 <xref:System.Windows.Forms.Control>에서 상속하는 메서드\)를 호출하십시오.  그러면 <xref:System.Windows.Forms.Control.Invalidate%2A>는 컨트롤을 다시 그리는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 호출합니다.  <xref:System.Windows.Forms.Control.Invalidate%2A>를 여러 번 호출하면 <xref:System.Windows.Forms.Control.OnPaint%2A>는 효율성을 위해 한 번 호출됩니다.  
  
-   .NET Framework 클래스 라이브러리에서는 정수, 10진수, Boolean 값 등과 같은 공용 데이터 형식에 대한 형식 변환기를 제공합니다.  대개, 문자열에서 값으로\(문자열 데이터에서 다른 데이터 형식으로\) 변환하기 위해 형식 변환기가 제공됩니다.  공용 데이터 형식은 값을 문자열로, 문자열을 적절한 데이터 형식으로 변환하는 기본 형식 변환기와 연결되어 있습니다.  사용자 지정, 즉 비표준 데이터 형식의 속성을 정의하는 경우, 해당 속성과 연결될 형식 변환기를 지정하는 특성을 적용해야 합니다.  특성을 사용하여 사용자 지정 UI 형식 편집기를 속성과 연결할 수도 있습니다.  UI 형식 편집기에서는 속성이나 데이터 형식을 편집하기 위해 사용자 인터페이스를 제공합니다.  색 선택이 바로 UI 형식 편집기의 예입니다.  이 항목의 끝에는 특성의 예제가 나와 있습니다.  
  
    > [!NOTE]
    >  형식 변환기 또는 UI 형식 편집기를 사용자 지정 속성에 사용할 수 없는 경우에는 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)에서 설명한 내용을 참조하여 새로 구현할 수 있습니다.  
  
 다음 코드 부분에서는 사용자 지정 컨트롤 `FlashTrackBar`에 대해 `EndColor`라는 사용자 지정 속성을 정의합니다.  
  
```vb  
Public Class FlashTrackBar  
   Inherits Control  
   ...  
   ' Private data member that backs the EndColor property.  
   Private _endColor As Color = Color.LimeGreen  
  
   ' The Category attribute tells the designer to display  
   ' it in the Flash grouping.   
   ' The Description attribute provides a description of  
   ' the property.   
   <Category("Flash"), _  
   Description("The ending color of the bar.")>  _  
   Public Property EndColor() As Color  
      ' The public property EndColor accesses _endColor.  
      Get  
         Return _endColor  
      End Get  
      Set  
         _endColor = value  
         If Not (baseBackground Is Nothing) And showGradient Then  
            baseBackground.Dispose()  
            baseBackground = Nothing  
         End If  
         ' The Invalidate method calls the OnPaint method, which redraws    
         ' the control.  
         Invalidate()  
      End Set  
   End Property  
   ...  
End Class  
  
```  
  
```csharp  
public class FlashTrackBar : Control {  
   ...  
   // Private data member that backs the EndColor property.  
   private Color endColor = Color.LimeGreen;  
   // The Category attribute tells the designer to display  
   // it in the Flash grouping.   
   // The Description attribute provides a description of  
   // the property.   
   [  
   Category("Flash"),  
   Description("The ending color of the bar.")  
   ]  
   // The public property EndColor accesses endColor.  
   public Color EndColor {  
      get {  
         return endColor;  
      }  
      set {  
         endColor = value;  
         if (baseBackground != null && showGradient) {  
            baseBackground.Dispose();  
            baseBackground = null;  
         }  
         // The Invalidate method calls the OnPaint method, which redraws   
         // the control.  
         Invalidate();  
      }  
   }  
   ...  
}  
```  
  
 다음 코드 부분에서는 형식 변환기와 UI 형식 편집기를 `Value` 속성과 연결합니다.  이런 경우 `Value`는 정수이고 기본 형식 변환기를 포함하지만 <xref:System.ComponentModel.TypeConverterAttribute> 특성은 디자이너가 이를 백분율로 표시할 수 있도록 사용자 지정 형식 변환기\(`FlashTrackBarValueConverter`\)를 적용합니다.  UI 형식 편집기 `FlashTrackBarValueEditor`를 사용하면 백분율을 시각적으로 표시할 수 있습니다.  또한 이 예제에서는 <xref:System.ComponentModel.TypeConverterAttribute> 특성이나 <xref:System.ComponentModel.EditorAttribute> 특성에서 지정한 형식 변환기 또는 편집기를 통해 기본 변환기를 재정의하는 것도 보여 줍니다.  
  
```vb  
<Category("Flash"), _  
TypeConverter(GetType(FlashTrackBarValueConverter)), _  
Editor(GetType(FlashTrackBarValueEditor), _  
GetType(UITypeEditor)), _  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")>  _  
Public ReadOnly Property Value() As Integer  
...  
End Property  
  
```  
  
```csharp  
[  
Category("Flash"),   
TypeConverter(typeof(FlashTrackBarValueConverter)),  
Editor(typeof(FlashTrackBarValueEditor), typeof(UITypeEditor)),  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")  
]  
public int Value {  
...  
}  
```  
  
## 참고 항목  
 [Windows Forms 컨트롤의 속성](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)   
 [속성 변경 이벤트](../../../../docs/framework/winforms/controls/property-changed-events.md)   
 [Windows Forms 컨트롤의 특성](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)