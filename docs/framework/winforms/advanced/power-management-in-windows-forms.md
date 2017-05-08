---
title: "Windows Forms의 전원 관리 | Microsoft Docs"
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
  - "배터리 상태"
  - "전원 상태"
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Windows Forms의 전원 관리
Windows Forms 응용 프로그램을 사용하면 Windows 운영 체제의 강력한 관리 기능을 사용할 수 있습니다.  응용 프로그램에서 컴퓨터의 전원 상태를 모니터링하고 상태가 변경될 경우 조치를 취할 수 있습니다.  예를 들어, 휴대용 컴퓨터에서 응용 프로그램을 실행할 경우 컴퓨터의 배터리 충전이 일정 수준 이하가 되면 응용 프로그램의 특정 기능을 해제할 수 있습니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서는 사용자가 운영 체제를 일시 중단하거나 다시 시작하는 경우 또는 AC 전원 상태나 배터리 상태가 변경되는 경우처럼 전원 상태가 변경될 때마다 발생하는 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> 이벤트를 제공합니다.  <xref:System.Windows.Forms.SystemInformation> 클래스의 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> 속성을 사용하여 다음 코드 예제에서 볼 수 있는 것처럼 현재 상태를 쿼리할 수 있습니다.  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> 속성에는 <xref:System.Windows.Forms.BatteryChargeStatus> 열거형 이외에 배터리 용량\(<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>\) 및 배터리 충전율\(<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>\)을 확인할 수 있는 열거형도 있습니다.  
  
 <xref:System.Windows.Forms.Application>의 <xref:System.Windows.Forms.Application.SetSuspendState%2A> 메서드를 사용하면 컴퓨터를 최대 절전 모드나 일시 중단 모드로 만들 수 있습니다.  `force` 인수가 `false`로 설정된 경우 운영 체제는 일시 중단 권한을 요청하는 모든 응용 프로그램으로 이벤트를 브로드캐스팅합니다.  `disableWakeEvent` 인수가 `true`로 설정된 경우에는 운영 체제가 모든 절전 모드 종료 이벤트를 사용하지 않습니다.  
  
 다음 코드 예제에서는 컴퓨터를 최대 절전 모드로 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## 참고 항목  
 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>   
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>   
 <xref:System.Windows.Forms.Application.SetSuspendState%2A>   
 <xref:Microsoft.Win32.SystemEvents.SessionSwitch>