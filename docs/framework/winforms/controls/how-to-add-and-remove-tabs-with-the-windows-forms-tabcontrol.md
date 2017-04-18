---
title: "방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거 | Microsoft Docs"
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
  - "탭 페이지"
  - "TabControl 컨트롤[Windows Forms], 탭 추가 및 제거"
  - "TabPage 컨트롤"
  - "탭, 페이지에 추가"
  - "탭, 페이지에서 제거"
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거
기본적으로 <xref:System.Windows.Forms.TabControl> 컨트롤에는 두 개의 <xref:System.Windows.Forms.TabPage> 컨트롤이 들어 있습니다.  <xref:System.Windows.Forms.TabControl.TabPages%2A> 속성을 통해 이러한 탭에 액세스할 수 있습니다.  
  
### 프로그래밍 방식으로 탭을 추가하려면  
  
-   <xref:System.Windows.Forms.TabControl.TabPages%2A> 속성의 <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> 메서드를 사용합니다.  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### 프로그래밍 방식으로 탭을 제거하려면  
  
-   선택한 탭을 제거하려면 <xref:System.Windows.Forms.TabControl.TabPages%2A> 속성의 <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> 메서드를 사용합니다.  
  
     또는  
  
-   모든 탭을 제거하려면 <xref:System.Windows.Forms.TabControl.TabPages%2A> 속성의 <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> 메서드를 사용합니다.  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## 참고 항목  
 [TabControl 컨트롤 개요](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [방법: 탭 페이지에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)   
 [방법: 탭 페이지 사용 안 함](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)   
 [방법: Windows Forms TabControl의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)