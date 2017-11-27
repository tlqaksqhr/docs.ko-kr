---
title: "Windows Forms의 전원 관리"
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
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e12f39a63a4f81e6deec4512a4e18ad2bda7e5e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="power-management-in-windows-forms"></a>Windows Forms의 전원 관리
Windows Forms 응용 프로그램에 Windows 운영 체제에서 전원 관리 기능을 활용을 걸릴 수 있습니다. 응용 프로그램 컴퓨터의 전원 상태를 모니터링 하 고는 상태 변경이 발생할 때 작업을 수행할 수 있습니다. 예를 들어 응용 프로그램이 노트북 컴퓨터에서 실행 되는 경우 컴퓨터의 배터리 충전 특정 수준에 해당 하는 경우 응용 프로그램에서 특정 기능을 비활성화 하는 것이 좋습니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 제공는 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> AC 전원 상태 또는 배터리 상태 변경 될 때 또는 사용자를 일시 중단 하거나 운영 체제를 다시 시작 하는 등 전원 상태에서 변경 될 때마다 발생 하는 이벤트입니다. <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> 속성의는 <xref:System.Windows.Forms.SystemInformation> 될 수 있는 클래스에 다음 코드 예제에서는 표시 된 대로 현재 상태에 대 한 쿼리를 사용 합니다.  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 외에는 <xref:System.Windows.Forms.BatteryChargeStatus> 열거형은 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> 배터리 용량을 결정 하기 위한 열거형 속성에도 포함 되어 (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) 및 백분율 충전 된 배터리 (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).  
  
 사용할 수는 <xref:System.Windows.Forms.Application.SetSuspendState%2A> 의 메서드는 <xref:System.Windows.Forms.Application> 절전 모드로 전환 하는 컴퓨터 또는 모드를 일시 중단 합니다. 경우는 `force` 인수도 설정 되어 `false`, 운영 체제 이벤트 일시 중단 하는 권한을 요청 하 고 모든 응용 프로그램에 브로드캐스트 됩니다. 경우는 `disableWakeEvent` 인수도 설정 되어 `true`, 운영 체제 절전 모드 해제 이벤트를 모두 사용 하지 않도록 설정 합니다.  
  
 다음 코드 예제에서는 컴퓨터를 절전 모드로 전환 하는 방법을 보여 줍니다.  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>  
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>  
 <xref:System.Windows.Forms.Application.SetSuspendState%2A>  
 <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
