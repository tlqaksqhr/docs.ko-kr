---
title: "방법: 구성 요소 컨트롤의 속성 노출 | Microsoft Docs"
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
  - "구성 요소 컨트롤"
  - "컨트롤[Windows Forms], 구성 요소"
  - "사용자 지정 컨트롤[Windows Forms], 속성 노출"
  - "사용자 정의 컨트롤[Windows Forms], 구성 요소 컨트롤 노출"
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 구성 요소 컨트롤의 속성 노출
복합 컨트롤을 구성하는 컨트롤을 *구성 요소 컨트롤*이라고 합니다.  이러한 컨트롤은 보통 전용으로 선언되므로 개발자가 액세스할 수 없습니다.  다음에 다른 사용자가 이 컨트롤의 속성을 사용할 수 있도록 하려면 사용자에게 이 컨트롤의 속성을 노출해야 합니다.  구성 요소 컨트롤의 속성을 노출하려면 사용자 정의 컨트롤에서 속성을 만든 다음 해당 속성의 `get` 및 `set` 접근자를 사용하여 구성 요소 컨트롤의 전용 속성을 변경해야 합니다.  
  
 `MyButton`이라는 구성 요소 단추를 포함하는 가상의 사용자 정의 컨트롤이 있다고 가정합니다.  이 예제에서는 사용자가 `ConstituentButtonBackColor` 속성을 요청하면 `MyButton`의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성에 저장된 값이 제공됩니다.  또한 사용자가 이 속성에 값을 할당하면 해당 값이 자동으로 `MyButton`의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성에 전달되고 `set` 코드가 실행되어 `MyButton`의 색을 변경합니다.  
  
 다음 예제는 구성 요소 단추의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 노출하는 방법을 보여 줍니다.  
  
```vb  
Public Property ButtonColor() as System.Drawing.Color  
   Get  
      Return MyButton.BackColor  
   End Get  
   Set(Value as System.Drawing.Color)  
      MyButton.BackColor = Value  
   End Set  
End Property  
```  
  
```csharp  
public Color ButtonColor  
{  
   get  
   {  
      return(myButton.BackColor);  
   }  
   set  
   {  
      myButton.BackColor = value;  
   }  
}  
```  
  
### 각 컨트롤의 속성을 노출시키려면  
  
1.  사용자 정의 컨트롤의 공용 속성을 만듭니다.  
  
2.  해당 속성의 `get` 섹션에서 노출할 속성의 값을 가져오는 코드를 작성합니다.  
  
3.  해당 속성의 `set` 섹션에서 속성의 값을 구성 요소 컨트롤의 노출된 속성에 전달하는 코드를 작성합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.UserControl>   
 [Windows Forms 컨트롤의 속성](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)