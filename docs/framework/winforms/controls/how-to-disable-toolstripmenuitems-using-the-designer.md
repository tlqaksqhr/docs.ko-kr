---
title: "방법: 디자이너를 사용하여 ToolStripMenuItems를 사용하지 않도록 설정 | Microsoft Docs"
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
  - "메뉴 항목, 비활성화"
  - "메뉴, 항목 사용 안 함"
  - "MenuStrip 컨트롤[Windows Forms], 디자이너에서 메뉴 항목을 사용하지 않도록 설정"
  - "ToolStripMenuItems, 디자이너에서 사용하지 않도록 설정"
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 디자이너를 사용하여 ToolStripMenuItems를 사용하지 않도록 설정
사용자의 동작에 따라 메뉴 항목을 활성화 또는 비활성화하여 사용자가 수행하는 명령을 제한하거나 확장할 수 있습니다.  메뉴 항목은 처음 만들 때 기본적으로 활성화되지만 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 통해 조정할 수 있습니다.  이 속성은 디자인 타임에 **속성** 창에서 조작하거나, 코드로 설정하여 프로그래밍 방식으로 조작할 수 있습니다.  자세한 내용은 [방법: ToolStripMenuItems 사용 안 함](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)을 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자인 타임에 메뉴 항목을 비활성화하려면  
  
1.  폼에서 메뉴 항목을 선택하고 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 `false`로 설정합니다.  
  
    > [!TIP]
    >  메뉴에서 첫 번째 항목 또는 최상위 항목을 비활성화하면 해당 메뉴에 포함된 모든 메뉴 항목이 비활성화됩니다.  마찬가지로 하위 메뉴 항목을 가진 메뉴 항목을 비활성화하면 해당 하위 메뉴 항목이 비활성화됩니다.  특정 메뉴의 모든 명령이 사용할 수 없는 명령일 경우 사용자 인터페이스를 명확하게 표시하기 위해 전체 메뉴를 숨기고 비활성화하는 것이 바람직한 프로그래밍 습관입니다.  메뉴를 숨기기만 하면 바로 가기 키를 사용하여 메뉴 명령에 액세스할 수 있기 때문에 숨기기와 비활성화를 모두 수행해야 합니다.  최상위 메뉴 항목의 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`로 설정하여 전체 메뉴를 숨깁니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [방법: ToolStripMenuItems 숨기기](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)   
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)