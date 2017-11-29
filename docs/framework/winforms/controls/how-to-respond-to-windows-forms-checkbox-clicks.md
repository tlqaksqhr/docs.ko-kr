---
title: "방법: Windows Forms CheckBox 클릭에 응답"
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
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f15adb84f92c9434d6835e80f08bf1d9bd500ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="1cd59-102">방법: Windows Forms CheckBox 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="1cd59-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="1cd59-103">Windows Forms를 클릭할 때마다 <xref:System.Windows.Forms.CheckBox> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd59-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="1cd59-104">확인란의 상태에 따라 작업을 수행할 수 있는 응용 프로그램을 프로그래밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd59-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="1cd59-105">CheckBox 클릭에 응답 하려면</span><span class="sxs-lookup"><span data-stu-id="1cd59-105">To respond to CheckBox clicks</span></span>  
  
1.  <span data-ttu-id="1cd59-106">에 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 사용 하 여는 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성을 컨트롤의 상태를 확인 하 고 필요한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd59-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the   
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the   
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="1cd59-107">사용자가을 두 번 클릭 하는 경우는 <xref:System.Windows.Forms.CheckBox> 컨트롤을 클릭할 때마다은 별도로 처리 됩니다; 즉, <xref:System.Windows.Forms.CheckBox> 컨트롤에 두 번 클릭 이벤트를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd59-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1cd59-108">경우는 <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> 속성은 `true` (기본값) 이면는 <xref:System.Windows.Forms.CheckBox> 를 자동으로 선택 하거나 클릭 하면 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd59-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="1cd59-109">수동으로 설정 해야 그렇지 않은 경우는 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성 때는 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd59-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="1cd59-110">사용할 수도 있습니다는 <xref:System.Windows.Forms.CheckBox> 일련의 동작을 확인 하기 위해 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1cd59-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="1cd59-111">클릭할 때 확인란이 작업의 과정을 결정 하려면</span><span class="sxs-lookup"><span data-stu-id="1cd59-111">To determine a course of action when a check box is clicked</span></span>  
  
1.  <span data-ttu-id="1cd59-112">값을 쿼리 하는 case 문을 사용 하 여는 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 일련의 동작을 결정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1cd59-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="1cd59-113">때는 <xref:System.Windows.Forms.CheckBox.ThreeState%2A> 속성이로 설정 되어 `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성 상자를 나타내는 세 가지 가능한 값을 반환할 수 상자 또는 옵션을 선택 취소 되 고 비활성화 상태는 상자가 표시 됩니다는 흐리게와 모양 옵션을 나타내는 데 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="1cd59-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select   
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="1cd59-114">경우는 <xref:System.Windows.Forms.CheckBox.ThreeState%2A> 속성이 `true`, <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성에서 반환 `true` 모두에 대 한 <xref:System.Windows.Forms.CheckState.Checked> 및 <xref:System.Windows.Forms.CheckState.Indeterminate>합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd59-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd59-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1cd59-115">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="1cd59-116">CheckBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="1cd59-116">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="1cd59-117">방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="1cd59-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [<span data-ttu-id="1cd59-118">CheckBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1cd59-118">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
