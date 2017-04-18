---
title: "방법: Windows Forms NotifyIcon 구성 요소를 사용하여 작업 표시줄에 응용 프로그램 아이콘 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TrayIcon"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "아이콘, 작업 표시줄에 추가"
  - "NotifyIcon 구성 요소"
  - "상태 영역 아이콘"
  - "작업 표시줄, 아이콘 추가"
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Forms NotifyIcon 구성 요소를 사용하여 작업 표시줄에 응용 프로그램 아이콘 추가
Windows Forms <xref:System.Windows.Forms.NotifyIcon> 구성 요소는 작업 표시줄의 상태 알림 영역에 아이콘 하나를 표시합니다.  상태 영역에 여러 개의 아이콘을 표시하려면 폼에 여러 개의 <xref:System.Windows.Forms.NotifyIcon> 구성 요소가 있어야 합니다.  컨트롤에 표시되는 아이콘을 설정하려면 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 속성을 사용합니다.  또한 <xref:System.Windows.Forms.NotifyIcon.DoubleClick> 이벤트 처리기에 코드를 작성하여 사용자가 해당 아이콘을 두 번 클릭했을 때 특정 작업이 발생하도록 할 수 있습니다.  예를 들면, 아이콘으로 나타나는 백그라운드 프로세스를 구성하는 대화 상자가 사용자에게 표시되도록 할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.NotifyIcon> 구성 요소는 사용자에게 동작 또는 이벤트가 발생한 사실을 알리거나 특정 종류의 상태가 변경되었다는 사실을 알리는 목적으로만 사용됩니다.  응용 프로그램과 표준 상호 작용을 수행하려면 메뉴, 도구 모음 및 기타 사용자 인터페이스 요소를 사용해야 합니다.  
  
### 아이콘을 설정하려면  
  
1.  <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 속성에 값을 할당합니다.  값은  `System.Drawing.Icon`  형식이어야 하며 .ico 파일에서 로드할 수 있습니다.  아이콘 파일은 코드에서 지정할 수도 있고 **속성** 창에서 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 속성 옆의 줄임표 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭하면 나타나는 **열기** 대화 상자에서 파일을 선택하여 지정할 수도 있습니다.  
  
2.  <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성을 `true`으로 설정합니다.  
  
3.  <xref:System.Windows.Forms.NotifyIcon.Text%2A> 속성을 적절한 도구 설명 문자열로 설정합니다.  
  
     다음 코드 예제에서 아이콘의 위치로 설정된 경로는 **내 문서** 폴더입니다.  Windows 운영 체제가 실행되는 대부분의 컴퓨터에는 내 문서  폴더가 포함되어 있으므로 이 위치를 사용합니다.  또한 내 문서 폴더를 선택하면 사용자는 최소한의 시스템 액세스 수준을 갖고 응용 프로그램을 안전하게 실행할 수 있습니다.  아래 예제에서는 <xref:System.Windows.Forms.NotifyIcon> 컨트롤을 포함하는 폼을 이미 추가한 것으로 가정합니다.  또한 이름이 `Icon.ico`인 아이콘 파일을 사용합니다.  
  
     \[Visual Basic\]  
  
    ```  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
  
    ```  
  
     \[C\#\]  
  
    ```  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    notifyIcon1.Icon =   
       new System.Drawing.Icon (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Icon.ico");  
    notifyIcon1.Visible = true;  
    notifyIcon1.Text = "Antivirus program";  
  
    ```  
  
     \[cpp\]  
  
    ```  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    notifyIcon1->Icon = gcnew   
       System::Drawing::Icon(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Icon.ico"));  
    notifyIcon1->Visible = true;  
    notifyIcon1->Text = "Antivirus program";  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.NotifyIcon>   
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>   
 [방법: Windows Forms NotifyIcon 구성 요소에 바로 가기 메뉴 연결](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)   
 [NotifyIcon 구성 요소](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)   
 [NotifyIcon 구성 요소 개요](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)