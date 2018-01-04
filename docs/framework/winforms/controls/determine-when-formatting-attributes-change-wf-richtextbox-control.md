---
title: "방법: Windows Forms RichTextBox 컨트롤에서 서식 특성의 변경 시기 결정"
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
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1764b55232d1883516c2cc8684e3ee1b0cb5c05b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="a805b-102">방법: Windows Forms RichTextBox 컨트롤에서 서식 특성의 변경 시기 결정</span><span class="sxs-lookup"><span data-stu-id="a805b-102">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="a805b-103">Windows Forms의 일반적인 용도 <xref:System.Windows.Forms.RichTextBox> 컨트롤 글꼴 옵션 또는 단락 스타일 등의 특성으로 텍스트 서식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a805b-103">A common use of the Windows Forms <xref:System.Windows.Forms.RichTextBox> control is formatting text with attributes such as font options or paragraph styles.</span></span> <span data-ttu-id="a805b-104">대부분의 워드프로세싱 응용 프로그램과 마찬가지로 도구 모음을 표시 하기 위해 텍스트 서식의 모든 변경 내용을 추적 하기 위해 응용 프로그램 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a805b-104">Your application may need to keep track of any changes in text formatting for the purpose of displaying a toolbar, as in many word-processing applications.</span></span>  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a><span data-ttu-id="a805b-105">서식 특성의 변경 내용에 응답 하려면</span><span class="sxs-lookup"><span data-stu-id="a805b-105">To respond to changes in formatting attributes</span></span>  
  
1.  <span data-ttu-id="a805b-106">코드를 작성은 <xref:System.Windows.Forms.RichTextBox.SelectionChanged> 이벤트 처리기 특성의 값에 따라 적절 한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a805b-106">Write code in the <xref:System.Windows.Forms.RichTextBox.SelectionChanged> event handler to perform an appropriate action depending on the value of the attribute.</span></span> <span data-ttu-id="a805b-107">다음 예에서는 변경의 값에 따라 도구 모음 단추의 모양을 <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a805b-107">The following example changes the appearance of a toolbar button depending on the value of the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="a805b-108">도구 모음 단추 컨트롤에서 삽입 지점이 이동 하는 경우에 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a805b-108">The toolbar button will only be updated when the insertion point is moved in the control.</span></span>  
  
     <span data-ttu-id="a805b-109">다음 예제에서는 포함 하는 폼을 가정는 <xref:System.Windows.Forms.RichTextBox> 제어 및 <xref:System.Windows.Forms.ToolBar> 도구 모음 단추를 포함 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a805b-109">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control and a <xref:System.Windows.Forms.ToolBar> control that contains a toolbar button.</span></span> <span data-ttu-id="a805b-110">도구 모음 및 도구 모음 단추에 대 한 자세한 내용은 참조 [하는 방법: ToolBar 컨트롤에 단추 추가](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a805b-110">For more information about toolbars and toolbar buttons, see [How to: Add Buttons to a ToolBar Control](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).</span></span>  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)   
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else   
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a805b-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a805b-111">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.SelectionChanged>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="a805b-112">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a805b-112">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="a805b-113">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a805b-113">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
