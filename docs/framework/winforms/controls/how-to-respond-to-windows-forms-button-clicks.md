---
title: '방법: Windows Forms 단추 클릭에 응답'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
ms.openlocfilehash: 14a880c34f163dc6fece44c24d377822a741b0f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534253"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="f5b9c-102">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="f5b9c-102">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="f5b9c-103">Windows Forms의 가장 기본적인 사용법 <xref:System.Windows.Forms.Button> 컨트롤에서 단추를 클릭할 때 일부 코드를 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b9c-103">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="f5b9c-104">클릭 하는 <xref:System.Windows.Forms.Button> 제어도 생성 된 수의 다른 이벤트와 같은 <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, 및 <xref:System.Windows.Forms.Control.MouseUp> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b9c-104">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="f5b9c-105">이러한 관련된 이벤트에 대 한 이벤트 처리기를 연결 하려는 경우 수의 동작이 충돌 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b9c-105">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="f5b9c-106">예를 들어 경우 단추를 클릭 하는 사용자가 텍스트 상자에 입력 한 정보를 단추 위로 마우스 포인터를 일시 중지 해야 하지 표시 지워지는 정보를 포함 하는 도구 설명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b9c-106">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="f5b9c-107">사용자가을 두 번 클릭 하는 경우는 <xref:System.Windows.Forms.Button> 컨트롤을 클릭할 때마다은 별도로 처리 됩니다; 즉, 컨트롤이 두 번 클릭 이벤트 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b9c-107">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="f5b9c-108">단추 클릭에 응답 하려면</span><span class="sxs-lookup"><span data-stu-id="f5b9c-108">To respond to a button click</span></span>  
  
-   <span data-ttu-id="f5b9c-109">단추의 `Click` <xref:System.EventHandler> 실행 하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b9c-109">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="f5b9c-110">`Button1_Click` 컨트롤에 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b9c-110">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="f5b9c-111">자세한 내용은 참조 [하는 방법: Windows Forms에 대 한 시간 실행에서 이벤트 처리기 만들기](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b9c-111">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f5b9c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5b9c-112">See Also</span></span>  
 [<span data-ttu-id="f5b9c-113">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="f5b9c-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="f5b9c-114">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="f5b9c-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="f5b9c-115">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f5b9c-115">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
