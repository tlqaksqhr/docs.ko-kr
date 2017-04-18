---
title: "Windows Forms의 인쇄 추가 보안 | Microsoft Docs"
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
  - "인쇄[Windows Forms], 보안"
  - "PrintingPermission 클래스, Windows Forms 보안"
  - "보안[Windows Forms], 인쇄"
  - "Windows Forms, 인쇄"
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Windows Forms의 인쇄 추가 보안
대부분의 Windows Forms 응용 프로그램에는 인쇄 기능이 포함됩니다.  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서는 <xref:System.Drawing.Printing.PrintingPermission> 클래스를 사용하여 인쇄 기능에 대한 액세스를 제어하고 관련된 <xref:System.Drawing.Printing.PrintingPermissionLevel> 열거형 값을 사용하여 액세스 수준을 나타냅니다.  인쇄는 기본적으로 로컬 인트라넷과 인터넷 영역에서 사용할 수 있지만 액세스 수준은 두 영역 모두에서 제한됩니다.  응용 프로그램이 인쇄할 수 있는지 여부 및 사용자 상호 작용이 필요한지 여부는 응용 프로그램에 부여된 권한 값에 따라 다릅니다.  기본적으로 로컬 인트라넷 영역에는 <xref:System.Drawing.Printing.PrintingPermissionLevel> 액세스가 부여되고 인터넷 영역에는 <xref:System.Drawing.Printing.PrintingPermissionLevel> 액세스가 부여됩니다.  
  
 다음 표에서는 각 인쇄 권한 수준에서 사용할 수 있는 기능을 보여 줍니다.  
  
|PrintingPermissionLevel|설명|  
|-----------------------------|--------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|설치된 모든 프린터에 대한 모든 액세스를 제공합니다.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|프로그래밍 방식으로 기본 프린터에 인쇄할 수 있으며 제한된 인쇄 대화 상자를 통해 안전하게 인쇄할 수 있습니다.  <xref:System.Drawing.Printing.PrintingPermissionLevel>은 <xref:System.Drawing.Printing.PrintingPermissionLevel>의 하위 집합입니다.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|보다 제한된 대화 상자에서만 인쇄할 수 있습니다.  <xref:System.Drawing.Printing.PrintingPermissionLevel>은 <xref:System.Drawing.Printing.PrintingPermissionLevel>의 하위 집합입니다.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|프린터에 액세스할 수 없도록 합니다.  <xref:System.Drawing.Printing.PrintingPermissionLevel>은 <xref:System.Drawing.Printing.PrintingPermissionLevel>의 하위 집합입니다.|  
  
## 참고 항목  
 [Windows Forms의 파일 및 데이터 액세스 추가 보안](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)   
 [Windows Forms의 추가 보안 고려 사항](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)   
 [Windows Forms의 보안 개요](../../../docs/framework/winforms/security-in-windows-forms-overview.md)   
 [Windows Forms 보안](../../../docs/framework/winforms/windows-forms-security.md)