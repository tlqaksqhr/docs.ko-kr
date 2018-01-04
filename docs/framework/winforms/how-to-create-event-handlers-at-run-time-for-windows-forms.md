---
title: "방법: 런타임에 Windows Forms의 이벤트 처리기 만들기"
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
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a636e42c85ef3703a2831583aea9839e13effeaa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="2eb0b-102">방법: 런타임에 Windows Forms의 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="2eb0b-102">How to: Create Event Handlers at Run Time for Windows Forms</span></span>
<span data-ttu-id="2eb0b-103">Windows Forms 디자이너를 사용하여 이벤트를 만들 수 있을 뿐만 아니라 런타임에 이벤트 처리기를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-103">In addition to creating events using the Windows Forms Designer, you can also create an event handler at run time.</span></span> <span data-ttu-id="2eb0b-104">이렇게 하면 프로그램이 처음 시작될 때 이벤트 처리기를 연결하는 대신 런타임에 코드를 사용하여 조건에 따라 이벤트 처리기를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-104">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>  
  
### <a name="to-create-an-event-handler-at-run-time"></a><span data-ttu-id="2eb0b-105">런타임에 이벤트 처리기를 만들려면</span><span class="sxs-lookup"><span data-stu-id="2eb0b-105">To create an event handler at run time</span></span>  
  
1.  <span data-ttu-id="2eb0b-106">이벤트 처리기를 추가할 양식을 코드 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-106">Open the form in the Code Editor that you want to add an event handler to.</span></span>  
  
2.  <span data-ttu-id="2eb0b-107">처리할 이벤트의 메서드 시그니처가 있는 양식에 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-107">Add a method to your form with the method signature for the event that you want to handle.</span></span>  
  
     <span data-ttu-id="2eb0b-108">예를 들어 처리 하는 경우는 <xref:System.Windows.Forms.Control.Click> 의 이벤트는 <xref:System.Windows.Forms.Button> 컨트롤을 만들면 됩니다 다음과 같은 메서드:</span><span class="sxs-lookup"><span data-stu-id="2eb0b-108">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)  
       ' Add event handler code here.  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
    // Add event handler code here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          // Add event handler code here.  
       }  
    ```  
  
3.  <span data-ttu-id="2eb0b-109">응용 프로그램에 적합한 코드를 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-109">Add code to the event handler as appropriate to your application.</span></span>  
  
4.  <span data-ttu-id="2eb0b-110">이벤트 처리기를 만들 양식 또는 컨트롤을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-110">Determine which form or control you want to create an event handler for.</span></span>  
  
5.  <span data-ttu-id="2eb0b-111">양식의 클래스에 있는 메서드에 이벤트를 처리할 이벤트 처리기를 지정하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-111">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="2eb0b-112">다음 코드에서는 이벤트 처리기를 지정 하는 예를 들어 `button1_Click` 핸들의 <xref:System.Windows.Forms.Control.Click> 의 이벤트는 <xref:System.Windows.Forms.Button> 제어:</span><span class="sxs-lookup"><span data-stu-id="2eb0b-112">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="2eb0b-113"><xref:System.ComponentModel.EventHandlerList.AddHandler%2A> 위의 Visual Basic 코드에서 보여 주는 메서드 단추의 click 이벤트 처리기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-113">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eb0b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2eb0b-114">See Also</span></span>  
 [<span data-ttu-id="2eb0b-115">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="2eb0b-115">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="2eb0b-116">이벤트 처리기 개요</span><span class="sxs-lookup"><span data-stu-id="2eb0b-116">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)  
 [<span data-ttu-id="2eb0b-117">Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2eb0b-117">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
