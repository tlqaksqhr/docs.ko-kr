---
title: "방법: Windows Forms NotifyIcon 구성 요소에 바로 가기 메뉴 연결 | Microsoft Docs"
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
  - "상황에 맞는 메뉴, 백그라운드 프로세스"
  - "NotifyIcon 구성 요소, 바로 가기 메뉴 연결"
  - "바로 가기 메뉴, 백그라운드 프로세스"
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: Windows Forms NotifyIcon 구성 요소에 바로 가기 메뉴 연결
> [!NOTE]
>  <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip>은 이전 버전의 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 컨트롤에 새로운 기능이 추가된 것으로, 이전 컨트롤을 대체합니다. 그러나 이전 버전과의 호환성 및 앞으로의 사용 가능성을 고려하여 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu>를 계속 유지하도록 선택할 수 있습니다.  
  
 <xref:System.Windows.Forms.NotifyIcon> 구성 요소는 작업 표시줄의 상태 알림 영역에 아이콘을 표시합니다.  일반적으로 사용자는 응용 프로그램에서 이 아이콘을 마우스 오른쪽 단추로 클릭하여 아이콘이 나타내는 응용 프로그램으로 명령을 보냅니다.  <xref:System.Windows.Forms.ContextMenu> 구성 요소에 <xref:System.Windows.Forms.NotifyIcon> 구성 요소를 연결하면 이러한 기능을 응용 프로그램에 추가할 수 있습니다.  
  
> [!NOTE]
>  시작 시 응용 프로그램을 최소화하고 작업 표시줄에 <xref:System.Windows.Forms.NotifyIcon> 구성 요소의 인스턴스를 표시하려면 기본 폼의 <xref:System.Windows.Forms.Form.WindowState%2A> 속성을 <xref:System.Windows.Forms.FormWindowState>로 설정하고 <xref:System.Windows.Forms.NotifyIcon> 구성 요소의 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성이 `true`로 설정되어 있는지 확인합니다.  
  
### 디자인 타임에 NotifyIcon 구성 요소에 바로 가기 메뉴를 연결하려면  
  
1.  폼에 <xref:System.Windows.Forms.NotifyIcon> 구성 요소를 추가하고 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 및 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성 등의 중요한 속성을 설정합니다.  
  
     자세한 내용은 [방법: Windows Forms NotifyIcon 구성 요소를 사용하여 작업 표시줄에 응용 프로그램 아이콘 추가](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)를 참조하십시오.  
  
2.  Windows Form에 <xref:System.Windows.Forms.ContextMenu> 구성 요소를 추가합니다.  
  
     런타임에 사용할 명령을 나타내는 바로 가기 메뉴에 메뉴 항목을 추가합니다.  이 때 이 메뉴 항목에 액세스 키 등의 향상 메뉴 기능을 추가하는 것도 좋습니다.  
  
3.  추가한 바로 가기 메뉴에 <xref:System.Windows.Forms.NotifyIcon> 구성 요소의 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> 속성을 설정합니다.  
  
     이 속성을 설정하면 작업 표시줄의 아이콘이 클릭될 경우 바로 가기 메뉴가 표시됩니다.  
  
### 프로그래밍 방식으로 NotifyIcon 구성 요소에 바로 가기 메뉴를 연결하려면  
  
1.  응용 프로그램에 필요한 모든 속성 설정을 사용하여\(<xref:System.Windows.Forms.NotifyIcon> 구성 요소의 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 및 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성, <xref:System.Windows.Forms.ContextMenu> 구성 요소의 메뉴 항목\) <xref:System.Windows.Forms.NotifyIcon> 클래스 및 <xref:System.Windows.Forms.ContextMenu> 클래스의 인스턴스를 만듭니다.  
  
2.  추가한 바로 가기 메뉴에 <xref:System.Windows.Forms.NotifyIcon> 구성 요소의 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> 속성을 설정합니다.  
  
     이 속성을 설정하면 작업 표시줄의 아이콘이 클릭될 경우 바로 가기 메뉴가 표시됩니다.  
  
    > [!NOTE]
    >  다음 코드 예제에서는 기본 메뉴 구조를 만듭니다.  메뉴 선택은 개발 중인 응용 프로그램에 맞게 사용자 지정합니다.  또한 해당 메뉴 항목에 대한 <xref:System.Windows.Forms.MenuItem.Click> 이벤트를 처리하는 코드를 작성합니다.  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _   
          (System.Environment.GetFolderPath _   
          (System.Environment.SpecialFolder.Personal)  _   
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
>  폼의 생성자에 다음 문을 포함하여 수행할 수 있는 `notifyIcon1` 및 `contextMenu1`을 초기화해야 합니다.  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## 참고 항목  
 <xref:System.Windows.Forms.NotifyIcon>   
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>   
 [방법: Windows Forms NotifyIcon 구성 요소를 사용하여 작업 표시줄에 응용 프로그램 아이콘 추가](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)   
 [NotifyIcon 구성 요소](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)   
 [NotifyIcon 구성 요소 개요](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)