---
title: "방법: Toolbar 단추의 메뉴 이벤트 트리거"
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
- cpp
helpviewer_keywords:
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], click event handlers
- ToolBar control [Windows Forms], coding button click events
- toolbars [Windows Forms], click event handlers
ms.assetid: 98374f70-993d-4ca4-89fb-48fea6ce5b45
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7744b82e7a1e041b50b9ce1d55ac93f65b1489f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a><span data-ttu-id="abf5d-102">방법: Toolbar 단추의 메뉴 이벤트 트리거</span><span class="sxs-lookup"><span data-stu-id="abf5d-102">How to: Trigger Menu Events for Toolbar Buttons</span></span>
> [!NOTE]
>  <span data-ttu-id="abf5d-103"><xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abf5d-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="abf5d-104">하는 경우 Windows Form 기능은 <xref:System.Windows.Forms.ToolBar> 컨트롤 도구 모음 단추를 사용 하려는 사용자가 어느 단추를 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abf5d-104">If your Windows Form features a <xref:System.Windows.Forms.ToolBar> control with toolbar buttons, you will want to know which button the user clicks.</span></span>  
  
 <span data-ttu-id="abf5d-105">에 <xref:System.Windows.Forms.ToolBar.ButtonClick> 의 이벤트는 <xref:System.Windows.Forms.ToolBar> 을 평가할 수 있는 컨트롤을는 <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> 의 속성은 <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> 클래스.</span><span class="sxs-lookup"><span data-stu-id="abf5d-105">On the <xref:System.Windows.Forms.ToolBar.ButtonClick> event of the <xref:System.Windows.Forms.ToolBar> control, you can evaluate the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> property of the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class.</span></span> <span data-ttu-id="abf5d-106">아래 예제에서는 클릭한 단추를 나타내는 메시지 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="abf5d-106">In the example below, a message box is shown, indicating which button was clicked.</span></span> <span data-ttu-id="abf5d-107">자세한 내용은 <xref:System.Windows.Forms.MessageBox>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="abf5d-107">For details, see <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="abf5d-108">아래 예에서는 가정 된 <xref:System.Windows.Forms.ToolBar> 컨트롤이 Windows Form에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abf5d-108">The example below assumes a <xref:System.Windows.Forms.ToolBar> control has been added to a Windows Form.</span></span>  
  
### <a name="to-handle-the-click-event-on-a-toolbar"></a><span data-ttu-id="abf5d-109">도구 모음에서 Click 이벤트를 처리하려면</span><span class="sxs-lookup"><span data-stu-id="abf5d-109">To handle the Click event on a toolbar</span></span>  
  
1.  <span data-ttu-id="abf5d-110">프로시저에서 도구 모음 단추를 추가 <xref:System.Windows.Forms.ToolBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="abf5d-110">In a procedure, add toolbar buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
    ```vb  
    Public Sub ToolBarConfig()  
    ' Instantiate the toolbar buttons, set their Text properties  
    ' and add them to the ToolBar control.  
       ToolBar1.Buttons.Add(New ToolBarButton("One"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Two"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Three"))  
    ' Add the event handler delegate.  
       AddHandler ToolBar1.ButtonClick, AddressOf Me.ToolBar1_ButtonClick  
    End Sub  
    ```  
  
    ```csharp  
    public void ToolBarConfig()   
    {  
       toolBar1.Buttons.Add(new ToolBarButton("One"));  
       toolBar1.Buttons.Add(new ToolBarButton("Two"));  
       toolBar1.Buttons.Add(new ToolBarButton("Three"));  
  
       toolBar1.ButtonClick +=   
          new ToolBarButtonClickEventHandler(this.toolBar1_ButtonClick);  
    }  
    ```  
  
    ```cpp  
    public:  
       void ToolBarConfig()  
       {  
          toolBar1->Buttons->Add(gcnew ToolBarButton("One"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Two"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Three"));  
  
          toolBar1->ButtonClick +=   
             gcnew ToolBarButtonClickEventHandler(this,  
             &Form1::toolBar1_ButtonClick);  
       }  
    ```  
  
2.  <span data-ttu-id="abf5d-111">에 대 한 이벤트 처리기는 <xref:System.Windows.Forms.ToolBar> 컨트롤의 <xref:System.Windows.Forms.ToolBar.ButtonClick> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="abf5d-111">Add an event handler for the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ButtonClick> event.</span></span> <span data-ttu-id="abf5d-112">문을 전환 하는 경우를 사용 하 여 및 <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> 클릭 된 도구 모음 단추를 결정 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="abf5d-112">Use a case switching statement and the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class to determine the toolbar button that was clicked.</span></span> <span data-ttu-id="abf5d-113">이에 따라 적절한 메시지 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="abf5d-113">Based on this, show an appropriate message box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="abf5d-114">이 예제에서 메시지 상자는 자리 표시자로만 사용되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abf5d-114">A message box is being used solely as a placeholder in this example.</span></span> <span data-ttu-id="abf5d-115">따라서 도구 모음 단추를 클릭할 때 실행할 다른 코드를 자유롭게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abf5d-115">Feel free to add other code to execute when the toolbar buttons are clicked.</span></span>  
  
    ```vb  
    Protected Sub ToolBar1_ButtonClick(ByVal sender As Object, _  
    ByVal e As ToolBarButtonClickEventArgs)  
    ' Evaluate the Button property of the ToolBarButtonClickEventArgs  
    ' to determine which button was clicked.  
       Select Case ToolBar1.Buttons.IndexOf(e.Button)  
         Case 0  
           MessageBox.Show("First toolbar button clicked")  
         Case 1  
           MessageBox.Show("Second toolbar button clicked")  
         Case 2  
           MessageBox.Show("Third toolbar button clicked")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    protected void toolBar1_ButtonClick(object sender,  
    ToolBarButtonClickEventArgs e)  
    {  
       // Evaluate the Button property of the ToolBarButtonClickEventArgs  
       // to determine which button was clicked.  
       switch (toolBar1.Buttons.IndexOf(e.Button))  
       {  
          case 0 :  
             MessageBox.Show("First toolbar button clicked");  
             break;  
          case 1 :  
             MessageBox.Show("Second toolbar button clicked");  
             break;  
          case 2 :  
             MessageBox.Show("Third toolbar button clicked");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    protected:  
       void toolBar1_ButtonClick(System::Object ^ sender,  
          ToolBarButtonClickEventArgs ^ e)  
       {  
         // Evaluate the Button property of the ToolBarButtonClickEventArgs  
         // to determine which button was clicked.  
          switch (toolBar1->Buttons->IndexOf(e->Button))  
          {  
             case 0 :  
                MessageBox::Show("First toolbar button clicked");  
                break;  
             case 1 :  
                MessageBox::Show("Second toolbar button clicked");  
                break;  
             case 2 :  
                MessageBox::Show("Third toolbar button clicked");  
                break;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="abf5d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abf5d-116">See Also</span></span>  
 <xref:System.Windows.Forms.ToolBar>  
 [<span data-ttu-id="abf5d-117">방법: ToolBar 컨트롤에 단추 추가</span><span class="sxs-lookup"><span data-stu-id="abf5d-117">How to: Add Buttons to a ToolBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)  
 [<span data-ttu-id="abf5d-118">방법: ToolBar 단추의 아이콘 정의</span><span class="sxs-lookup"><span data-stu-id="abf5d-118">How to: Define an Icon for a ToolBar Button</span></span>](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [<span data-ttu-id="abf5d-119">ToolBar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="abf5d-119">ToolBar Control</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)
