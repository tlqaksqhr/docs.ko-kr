---
title: "시스템 정보 및 Windows Forms | Microsoft Docs"
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
  - "도메인 이름, 검색"
  - "시스템 정보[Windows Forms]"
  - "SystemInformation 클래스[Windows Forms]"
  - "사용자 이름, 검색"
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 시스템 정보 및 Windows Forms
경우에 따라서는 코드에서 수행할 특정 작업을 결정하기 위해 응용 프로그램이 실행되고 있는 컴퓨터에 대한 정보를 수집해야 합니다.  예를 들어 특정 네트워크 도메인에 연결되어 있을 때만 기능을 적용할 수 있는 경우 해당 도메인을 확인하고 도메인이 없을 경우 이 기능을 사용할 수 없도록 설정하는 방법이 필요할 수 있습니다.  
  
 Windows Forms 응용 프로그램에서는 <xref:System.Windows.Forms.SystemInformation> 클래스를 사용하여 런타임에 컴퓨터에 대한 다양한 정보를 확인할 수 있습니다.  다음 예제에서는 <xref:System.Windows.Forms.SystemInformation> 클래스를 사용하여 <xref:System.Windows.Forms.SystemInformation.UserName%2A> 및 <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>을 검색하는 방법을 보여 줍니다.  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to " _  
+ Domain)  
```  
  
 <xref:System.Windows.Forms.SystemInformation> 클래스의 모든 멤버는 읽기 전용이므로 사용자 설정을 수정할 수 없습니다.  이 클래스에는 100이 넘는 멤버가 포함되어 있어서 컴퓨터에 연결된 모니터의 수\(<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>\)에서부터 Windows 탐색기의 아이콘 간격\(<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> 및 <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>\)에 이르기까지 모든 정보를 반환합니다.  
  
 <xref:System.Windows.Forms.SystemInformation> 클래스의 멤버 중 <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> 및 <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A> 등의 멤버가 유용합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.SystemInformation>   
 [Windows Forms의 전원 관리](../../../../docs/framework/winforms/advanced/power-management-in-windows-forms.md)