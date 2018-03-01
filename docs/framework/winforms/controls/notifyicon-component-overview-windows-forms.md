---
title: "NotifyIcon 구성 요소 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NotifyIcon
helpviewer_keywords:
- NotifyIcon component [Windows Forms], about NotifyIcon component
- system tray icons [Windows Forms], about system tray icons
- system tray icons [Windows Forms], using in Windows Forms
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8c909537bd4c52a546faeb83c6e9291c4de76d76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="notifyicon-component-overview-windows-forms"></a>NotifyIcon 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.NotifyIcon> 구성 요소는 일반적으로 백그라운드에서 실행되고 대체로 사용자 인터페이스를 표시하지 않는 프로세스에 대한 아이콘을 표시하는 데 사용됩니다. 예를 들어 작업 표시줄의 상태 알림 영역에서 아이콘을 클릭하여 액세스할 수 있는 바이러스 방지 프로그램이 있습니다.  
  
## <a name="key-properties-of-notifyicons"></a>NotifyIcons의 키 속성  
 각 <xref:System.Windows.Forms.NotifyIcon> 구성 요소는 상태 영역에 단일 아이콘을 표시합니다. 3개의 백그라운드 프로세스가 있고 각 프로세스에 대한 아이콘을 표시하려는 경우 <xref:System.Windows.Forms.NotifyIcon> 구성 요소 3개를 폼에 추가해야 합니다. <xref:System.Windows.Forms.NotifyIcon> 구성 요소의 키 속성은 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 및 <xref:System.Windows.Forms.NotifyIcon.Visible%2A>입니다. <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 속성은 상태 영역에 표시되는 아이콘을 설정합니다. 아이콘이 표시되려면 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성을 `true`로 설정해야 합니다.  
  
 [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]를 사용 중인 경우 <xref:System.Windows.Forms.NotifyIcon> 컨트롤에 사용할 수 있는 표준 이미지의 대규모 라이브러리에 액세스할 수 있습니다.  
  
## <a name="notifyicons-options"></a>NotifyIcons 옵션  
 풍선 설명, 바로 가기 메뉴 및 도구 설명을 <xref:System.Windows.Forms.NotifyIcon>에 연결하여 사용자를 지원할 수 있습니다.  
  
 풍선 설명을 표시할 시간 범위를 지정하고 <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> 메서드를 호출하여 <xref:System.Windows.Forms.NotifyIcon>에 대한 풍선 설명을 표시할 수 있습니다. <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> 및 <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>을 각각 사용하여 풍선 설명의 텍스트, 아이콘 및 제목을 지정할 수도 있습니다. <xref:System.Windows.Forms.NotifyIcon> 구성 요소에 연결된 도구 설명 및 바로 가기 메뉴가 있을 수도 있습니다. 자세한 내용은 참조 [ToolTip 구성 요소 개요](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md) 및 [ContextMenu 구성 요소 개요](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.NotifyIcon>  
 [NotifyIcon 구성 요소](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)
