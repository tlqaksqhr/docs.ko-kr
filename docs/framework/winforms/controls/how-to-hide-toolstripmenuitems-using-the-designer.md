---
title: "방법: 디자이너를 사용하여 ToolStripMenuItems 숨기기 | Microsoft Docs"
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
  - "메뉴 항목, 숨기기"
  - "MenuStrip 컨트롤[Windows Forms], 디자이너에서 메뉴 항목 숨기기"
  - "ToolStripMenuItems, 디자이너에서 메뉴 항목 숨기기"
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 디자이너를 사용하여 ToolStripMenuItems 숨기기
메뉴 항목을 숨기면 응용 프로그램의 UI\(사용자 인터페이스\)를 제어하고 사용자 명령을 제한할 수 있습니다.  메뉴의 모든 항목이 사용할 수 없는 항목일 경우 대개 전체 메뉴를 숨기는 것이 좋습니다.  이렇게 하면 사용자의 혼란을 줄일 수 있습니다.  또한 숨기는 것만으로도 사용자가 바로 가기 키를 사용하여 메뉴 명령에 액세스하는 것이 가능하므로 메뉴 또는 메뉴 항목을 숨김과 동시에 비활성화할 수 있습니다.  메뉴 항목을 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [방법: 디자이너를 사용하여 ToolStripMenuItems를 사용하지 않도록 설정](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)을 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 최상위 메뉴와 해당 하위 메뉴 항목을 숨기려면  
  
1.  최상위 메뉴 항목을 선택하고 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 또는 <xref:System.Windows.Forms.ToolStripItem.Available%2A> 속성을 `false`로 설정합니다.  
  
     최상위 메뉴 항목을 숨기는 경우 해당 메뉴 안에 있는 모든 메뉴 항목도 숨겨집니다.  <xref:System.Windows.Forms.ToolStripItem.Visible%2A>을 `false`로 설정한 다음 <xref:System.Windows.Forms.MenuStrip>이 아닌 다른 위치를 클릭하면 전체 최상위 메뉴 항목과 해당 하위 메뉴 항목이 폼에서 사라지므로 작업을 런타임으로 실행한 효과를 볼 수 있습니다.  디자인 타임에 숨겨진 최상위 메뉴 항목을 표시하려면 **구성 요소 트레이**, **문서 개요** 또는 속성 표의 맨 위에서 <xref:System.Windows.Forms.MenuStrip>을 클릭합니다.  
  
> [!NOTE]
>  병합 시나리오의 MDI\(다중 문서 인터페이스\) 자식 메뉴를 제외하면 전체 메뉴가 숨겨지는 경우는 거의 없습니다.  
  
### 하위 메뉴 항목을 숨기려면  
  
1.  하위 메뉴 항목을 선택하고 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`로 설정합니다.  
  
     하위 메뉴 항목을 숨기더라도 디자인 타임에는 추가 작업에서 쉽게 선택할 수 있도록 폼에 그대로 표시됩니다.  그러나 런타임에는 실제로 숨겨집니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>   
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>   
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)   
 [방법: 디자이너를 사용하여 ToolStripMenuItems를 사용하지 않도록 설정](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)