---
title: '방법: 구성 요소 컨트롤의 속성 노출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
ms.openlocfilehash: 8f7b5c44a5cb20b5da10df5fd630b371cc959fa8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532635"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="26465-102">방법: 구성 요소 컨트롤의 속성 노출</span><span class="sxs-lookup"><span data-stu-id="26465-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="26465-103">복합 컨트롤을 구성 하는 컨트롤 이라고 *구성 요소 컨트롤*합니다.</span><span class="sxs-lookup"><span data-stu-id="26465-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="26465-104">이러한 컨트롤은 일반적으로 전용으로 선언 및 따라서 개발자가 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26465-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="26465-105">향후 사용자에 게 이러한 컨트롤의 속성을 제공 하려는 경우 사용자에 게 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26465-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="26465-106">사용자 정의 컨트롤에서 속성을 만들고 사용 하 여 구성 요소 컨트롤의 속성을 노출 된 `get` 및 `set` 의 구성 요소 컨트롤 전용 속성의 변경 내용을 적용 하려면 해당 속성의 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="26465-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>  
  
 <span data-ttu-id="26465-107">가상의 사용자 정의 컨트롤 이라는 구성 요소 단추 있다고 가정 `MyButton`합니다.</span><span class="sxs-lookup"><span data-stu-id="26465-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="26465-108">이 예제에서는 사용자가 요청할 때는 `ConstituentButtonBackColor` 속성에 저장 된 값의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성 `MyButton` 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26465-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="26465-109">이 속성에 값을 할당 하는 사용자, 해당 값을 자동으로 전달 되는 <xref:System.Windows.Forms.Control.BackColor%2A> 속성 `MyButton` 및 `set` 코드는 실행의 색을 변경 `MyButton`합니다.</span><span class="sxs-lookup"><span data-stu-id="26465-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>  
  
 <span data-ttu-id="26465-110">다음 예제에서는 노출 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Control.BackColor%2A> 구성 단추의 속성:</span><span class="sxs-lookup"><span data-stu-id="26465-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>  
  
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
  
### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="26465-111">구성 요소 컨트롤의 속성을 노출 하려면</span><span class="sxs-lookup"><span data-stu-id="26465-111">To expose a property of a constituent control</span></span>  
  
1.  <span data-ttu-id="26465-112">사용자 정의 컨트롤에 대 한 공용 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26465-112">Create a public property for your user control.</span></span>  
  
2.  <span data-ttu-id="26465-113">에 `get` 섹션의 속성을 노출 하려는 속성의 값을 검색 하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="26465-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>  
  
3.  <span data-ttu-id="26465-114">에 `set` 섹션 속성의 구성 요소 컨트롤 노출 된 속성을 속성의 값을 전달 하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="26465-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26465-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26465-115">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 [<span data-ttu-id="26465-116">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="26465-116">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [<span data-ttu-id="26465-117">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="26465-117">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
