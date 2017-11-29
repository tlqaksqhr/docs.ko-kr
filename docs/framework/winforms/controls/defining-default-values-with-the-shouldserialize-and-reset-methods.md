---
title: "ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d082b0e3db1e1c115d28446cf515cf6acf60a7d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="8467f-102">ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의</span><span class="sxs-lookup"><span data-stu-id="8467f-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="8467f-103">`ShouldSerialize`및 `Reset` 속성이 없는 경우 속성에 대해 제공할 수 있는 선택적 메서드는는 간단한 기본값을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="8467f-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="8467f-104">속성에 기본값을 적용 해야는 <xref:System.ComponentModel.DefaultValueAttribute> 특성 클래스 생성자에 기본값을 대신 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8467f-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="8467f-105">이러한 메커니즘 중 하나를 통해 디자이너에서 다음과 같은 기능 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8467f-105">Either of these mechanisms enables the following features in the designer:</span></span>  
  
-   <span data-ttu-id="8467f-106">속성 값이 기본값에서 수정 된 경우 속성 브라우저에서 시각적 표시를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8467f-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>  
  
-   <span data-ttu-id="8467f-107">사용자 속성을 마우스 오른쪽 단추로 클릭 하 고 선택할 수 **재설정** 속성을 기본값으로 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8467f-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>  
  
-   <span data-ttu-id="8467f-108">디자이너는 보다 효율적인 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8467f-108">The designer generates more efficient code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8467f-109">적용 중 하나는 <xref:System.ComponentModel.DefaultValueAttribute> 제공 또는 `Reset` *PropertyName* 및 `ShouldSerialize` *PropertyName* 메서드.</span><span class="sxs-lookup"><span data-stu-id="8467f-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="8467f-110">둘 다 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8467f-110">Do not use both.</span></span>  
  
 <span data-ttu-id="8467f-111">`Reset` *PropertyName* 메서드 다음 코드 조각에 나와 있는 것 처럼 속성을 해당 기본값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8467f-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>  
  
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
>  <span data-ttu-id="8467f-112">속성이 없는 경우는 `Reset` 메서드를로 표시 되지 않으면는 <xref:System.ComponentModel.DefaultValueAttribute>, 선언에 제공 되는 기본 값이 없으면는 `Reset` 의 바로 가기 메뉴에서 해당 속성이 사용 되지 않는지에 대 한 옵션는 **속성** 에 Windows Forms 디자이너의 창 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="8467f-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="8467f-113">와 같은 디자이너 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 사용는 `ShouldSerialize` *PropertyName* 속성이 기본값에서 변경 되었는지 여부를 확인 하 고 속성 경우에만 폼에 코드를 작성 하는 방법을 변경 되 면 되므로 보다 효율적인 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8467f-113">Designers such as [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="8467f-114">예:</span><span class="sxs-lookup"><span data-stu-id="8467f-114">For example:</span></span>  
  
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
  
 <span data-ttu-id="8467f-115">전체 코드 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8467f-115">A complete code example follows.</span></span>  
  
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
  
 <span data-ttu-id="8467f-116">개인 변수의 값으로 액세스 하는 경우에이 경우에는 `MyFont` 속성은 `null`, 속성 브라우저에 표시 되지 `null`대신 표시는 <xref:System.Windows.Forms.Control.Font%2A> 없는 경우 부모 `null`, 또는 기본 <xref:System.Windows.Forms.Control.Font%2A> 에 정의 된 값 <xref:System.Windows.Forms.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="8467f-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="8467f-117">에 대 한 기본값에 따라서 `MyFont` 간단히 설정할 수 없습니다 및 <xref:System.ComponentModel.DefaultValueAttribute> 이 속성에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8467f-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="8467f-118">대신,는 `ShouldSerialize` 및 `Reset` 에 대 한 메서드를 구현 해야 합니다는 `MyFont` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8467f-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8467f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8467f-119">See Also</span></span>  
 [<span data-ttu-id="8467f-120">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="8467f-120">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [<span data-ttu-id="8467f-121">속성 정의</span><span class="sxs-lookup"><span data-stu-id="8467f-121">Defining a Property</span></span>](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 [<span data-ttu-id="8467f-122">속성 변경 이벤트</span><span class="sxs-lookup"><span data-stu-id="8467f-122">Property-Changed Events</span></span>](../../../../docs/framework/winforms/controls/property-changed-events.md)
