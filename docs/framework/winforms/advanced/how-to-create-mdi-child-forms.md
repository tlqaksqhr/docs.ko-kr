---
title: "방법: MDI 자식 폼 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "자식 폼"
  - "MDI, 폼 만들기"
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# 방법: MDI 자식 폼 만들기
MDI 자식 폼은 사용자 상호 작용의 중심이므로 [MDI 응용 프로그램](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)의 중요한 요소입니다.  
  
 다음 절차에서는 대부분의 워드프로세싱 응용 프로그램과 비슷하게 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 표시하는 MDI 자식 폼을 만듭니다.  <xref:System.Windows.Forms> 컨트롤을 <xref:System.Windows.Forms.DataGridView> 컨트롤과 같은 다른 컨트롤이나 컨트롤 혼합으로 대체하면 다양한 가능성을 가진 MDI 자식 창\(및 확장을 통해 MDI 응용 프로그램\)을 만들 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### MDI 자식 폼을 만들려면  
  
1.  새 Windows Forms 프로젝트를 만듭니다.  폼에 대한 **속성 창**에서 해당 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정하고 `WindowsState` 속성을 `Maximized`로 설정합니다.  
  
     그러면 폼이 자식 창의 MDI 컨테이너로 지정됩니다.  
  
2.  `Toolbox`에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 끌어서 놓습니다.  해당 `Text` 속성을 **File**로 설정합니다.  
  
3.  **Items** 속성 옆에 있는 줄임표\(...\)를 클릭한 다음 **추가**를 클릭하여 자식 도구 스트립 메뉴 항목 두 개를 추가합니다.  이러한 항목에 대한 `Text` 속성을 **New** 및 **Window**로 설정합니다.  
  
4.  **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **새 항목 추가**를 선택합니다.  
  
5.  **새 항목 추가** 대화 상자의 **템플릿** 창에서 **Windows Form**\([!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\) 또는 **Windows Forms 응용 프로그램\(.NET\)**\([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\)을 선택합니다.  **이름** 상자에서 폼의 이름을 Form2로 지정합니다.  **열기** 단추를 클릭하여 프로젝트에 폼을 추가합니다.  
  
    > [!NOTE]
    >  이 단계에서 만든 MDI 자식 폼은 표준 Windows Form입니다.  따라서 폼의 투명도를 제어할 수 있는 <xref:System.Windows.Forms.Form.Opacity%2A> 속성이 있습니다.  그러나 <xref:System.Windows.Forms.Form.Opacity%2A> 속성은 최상위 창에 사용하도록 설계되었습니다.  그리기 문제가 발생할 수 있으므로 MDI 자식 폼에는 사용하지 마세요.  
  
     이 폼은 MDI 자식 폼에 대한 템플릿이 됩니다.  
  
     **Windows Forms 디자이너**가 열리고 Form2를 표시합니다.  
  
6.  **도구 상자**에서 **RichTextBox** 컨트롤을 폼으로 끌어서 놓습니다.  
  
7.  **속성** 창에서 `Anchor` 속성을 **Top, Left**로 설정하고 `Dock` 속성을 **Fill**로 설정합니다.  
  
     이렇게 하면 폼의 크기를 조정하는 경우에도 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 MDI 자식 폼의 영역을 완전히 채웁니다.  
  
8.  **New** 메뉴 항목을 두 번 클릭하여 해당 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만듭니다.  
  
9. 다음과 비슷한 코드를 삽입하여 사용자가 **New** 메뉴 항목을 클릭할 때 새 MDI 자식 폼을 만듭니다.  
  
    > [!NOTE]
    >  다음 예제에서는 이벤트 처리기가 `MenuItem2`에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트를 처리합니다.  응용 프로그램 아키텍처의 고유 정보에 따라 **New** 메뉴 항목이 `MenuItem2`가 아닐 수도 있습니다.  
  
    ```vb  
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click  
       Dim NewMDIChild As New Form2()  
       'Set the Parent Form of the Child window.  
       NewMDIChild.MdiParent = Me  
       'Display the new form.  
       NewMDIChild.Show()  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void MDIChildNew_Click(object sender, System.EventArgs e){  
       Form2 newMDIChild = new Form2();  
       // Set the Parent Form of the Child window.  
       newMDIChild.MdiParent = this;  
       // Display the new form.  
       newMDIChild.Show();  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void menuItem2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          Form2^ newMDIChild = gcnew Form2();  
          // Set the Parent Form of the Child window.  
          newMDIChild->MdiParent = this;  
          // Display the new form.  
          newMDIChild->Show();  
       }  
    ```  
  
     [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]에서 Form1.h의 맨 위에 다음 `#include` 지시문을 추가합니다.  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. **속성** 창의 맨 위에 있는 드롭다운 목록에서 **File** 메뉴 스트립에 해당하는 메뉴 스트립을 선택하고 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성을 Window <xref:System.Windows.Forms.ToolStripMenuItem>로 설정합니다.  
  
     이렇게 하면 **Window** 메뉴가 활성 자식 창 옆에 확인 표시가 있는 열린 MDI 자식 창의 목록을 유지 관리할 수 있습니다.  
  
11. F5 키를 눌러 응용 프로그램을 실행합니다.  **File** 메뉴에서 **New**를 선택하면 **Window** 메뉴 항목에서 추적되는 새 MDI 자식 폼을 만들 수 있습니다.  
  
    > [!NOTE]
    >  MDI 자식 폼이 <xref:System.Windows.Forms.MainMenu> 구성 요소\(일반적으로 메뉴 항목의 메뉴 구조 사용\)를 포함하고 <xref:System.Windows.Forms.MainMenu> 구성 요소\(일반적으로 메뉴 항목의 메뉴 구조 사용\)가 있는 MDI 부모 폼 내에서 열린 경우 <xref:System.Windows.Forms.MenuItem.MergeType%2A> 속성\(및 필요에 따라 <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> 속성\)을 설정했으면 메뉴 항목이 자동으로 병합됩니다.  두 <xref:System.Windows.Forms.MainMenu> 구성 요소와 자식 폼의 모든 메뉴 항목에 대한 <xref:System.Windows.Forms.MenuItem.MergeType%2A> 속성을 <xref:System.Windows.Forms.MenuMerge>로 설정합니다.  또한 두 메뉴의 메뉴 항목이 원하는 순서대로 표시되도록 <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> 속성을 설정합니다.  MDI 부모 폼을 닫을 경우 MDI 부모에 대한 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생하기 전에 각 MDI 자식 폼에서 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생합니다.  MDI 자식의 <xref:System.Windows.Forms.Form.Closing> 이벤트를 취소해도 MDI 부모의 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생하지 않도록 방지되지는 않습니다. 그러나 MDI 부모의 <xref:System.Windows.Forms.Form.Closing> 이벤트에 대한 <xref:System.ComponentModel.CancelEventArgs> 인수가 이제 `true`로 설정됩니다.  <xref:System.ComponentModel.CancelEventArgs> 인수를 `false`로 설정하여 MDI 부모 및 모든 MDI 자식 폼을 강제로 닫을 수 있습니다.  
  
## 참고 항목  
 [MDI 응용 프로그램](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [방법: MDI 상위 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [방법: 활성 MDI 자식 확인](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)   
 [방법: 활성 MDI 자식으로 데이터 전송](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)   
 [방법: MDI 자식 폼 정렬](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)