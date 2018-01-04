---
title: "방법: 탭 페이지 사용 안 함"
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
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2db19d402f32bd43bb7053403428e8055755d017
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="1918e-102">방법: 탭 페이지 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="1918e-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="1918e-103">일부 경우에 Windows Forms 응용 프로그램 내에서 사용할 수 있는 데이터 액세스를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="1918e-104">탭 컨트롤;의 탭 페이지에 표시 된 데이터가 있는 경우이 예로 들 수 있습니다. 관리자는 게스트 또는 하위 수준의 사용자 옵션을 원하는 탭 페이지의 정보에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="1918e-105">탭 페이지를 프로그래밍 방식으로 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1918e-105">To disable tab pages programmatically</span></span>  
  
1.  <span data-ttu-id="1918e-106">탭 컨트롤의 처리 코드를 작성 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="1918e-107">하나의 탭에서 다음 전환할 때 발생 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2.  <span data-ttu-id="1918e-108">자격 증명을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-108">Check credentials.</span></span> <span data-ttu-id="1918e-109">에 제공 된 정보에 따라, 사용자가 탭을 볼 수 있도록 하기 전에 사용 하 여 사용자가 로그인 사용자 이름 또는 다른 형태의 자격 증명을 확인 하려는 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3.  <span data-ttu-id="1918e-110">사용자에 게 적절 한 자격 증명을 클릭 한 탭을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="1918e-111">적절 한 자격 증명이 없으면 메시지 상자가 표시 되거나 하는지 여부를 나타내는 다른 사용자 인터페이스 않습니다 하지 액세스는 초기 탭으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1918e-112">프로덕션 응용 프로그램에서이 기능을 구현 하는 경우 폼의 하는 동안이 자격 증명 검사를 수행할 수 있습니다 <xref:System.Windows.Forms.Form.Load> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="1918e-113">이렇게 하면 사용자 개입 하는 프로그래밍 하는 많은 클리너 방안을 표시 되기 전에 탭을 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="1918e-114">아래에 사용 되는 방법과 (자격 증명을 확인 하 고 해제 하는 동안 탭은 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 이벤트)는 설명 목적입니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4.  <span data-ttu-id="1918e-115">필요에 따라 두 개 이상의 탭 페이지를 사용 하도록 설정한 경우에 원본과 다른 탭 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="1918e-116">다음 예제에는 <xref:System.Windows.Forms.CheckBox> 조건으로 자격 증명을 확인 하는 탭에 대 한 액세스는 응용 프로그램에 따라 달라 집니다 대신이 대화 상자 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="1918e-117">경우는 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 이벤트가 자격 증명 확인이 true (즉, 확인란은 선택 됨)에서 선택한 탭이 고 `TabPage2` (이 예제의 기밀 정보로 탭), 다음 `TabPage2` 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="1918e-118">그렇지 않으면 `TabPage3` 표시 되 고 적절 한 액세스 권한이 없음을 나타내는 메시지 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="1918e-119">아래의 코드 포함 하는 폼을 <xref:System.Windows.Forms.CheckBox> 컨트롤 (`CredentialCheck`) 및 <xref:System.Windows.Forms.TabControl> 3 개의 탭 페이지와 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _   
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _   
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _   
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))   
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     <span data-ttu-id="1918e-120">(Visual C#, Visual c + +) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1918e-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1918e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1918e-121">See Also</span></span>  
 [<span data-ttu-id="1918e-122">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="1918e-122">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="1918e-123">방법: 탭 페이지에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="1918e-123">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="1918e-124">방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="1918e-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="1918e-125">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="1918e-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
