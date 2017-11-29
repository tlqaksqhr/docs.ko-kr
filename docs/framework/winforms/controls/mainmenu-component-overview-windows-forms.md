---
title: "MainMenu 구성 요소 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6f5cfe3a97bbbd4d5ba2d3ba089736599b6a2190
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="mainmenu-component-overview-windows-forms"></a>MainMenu 구성 요소 개요(Windows Forms)
> [!IMPORTANT]
>  하지만 <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip> 대체 기능을 추가 하 고는 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 이전 버전의 컨트롤 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 선택 하는 경우 이전 버전과 호환성 및 이후 사용을 모두 유지 됩니다.  
  
 Windows Forms <xref:System.Windows.Forms.MainMenu> 런타임 시 구성 요소에 메뉴가 표시 됩니다. 주 메뉴 및 개별 항목의 모든 하위 메뉴는 <xref:System.Windows.Forms.MenuItem> 개체입니다.  
  
## <a name="key-properties"></a>키 속성  
 메뉴 항목을 설정 하 여 기본 항목으로 지정 될 수 있습니다는 <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> 속성을 `true`합니다. 메뉴를 클릭 하면 기본 항목이 굵은 텍스트로 나타납니다. 메뉴 항목의 <xref:System.Windows.Forms.MenuItem.Checked%2A> 속성이 `true` 또는 `false`, 메뉴 항목이 선택 되어 있는지 여부를 나타냅니다. 메뉴 항목의 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 속성에서 선택한 항목의 모양을 사용자 지정: 경우 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 로 설정 되어 `true`, 경우 항목; 옆에 표시 되는 라디오 단추 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 로 설정 된 `false`, 항목 옆에 확인 표시가 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.MainMenu>  
 <xref:System.Windows.Forms.Menu>  
 <xref:System.Windows.Forms.MenuItem>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
