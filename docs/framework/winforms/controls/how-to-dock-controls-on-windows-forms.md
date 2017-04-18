---
title: "방법: Windows Forms에 컨트롤 도킹 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 도킹"
  - "Dock 속성"
  - "탐색기 스타일 응용 프로그램, 만들기"
  - "Windows Forms 컨트롤, 클라이언트 영역 채우기"
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Windows Forms에 컨트롤 도킹
폼의 가장자리에 컨트롤을 도킹하거나 컨트롤의 컨테이너\(폼 또는 컨테이너 컨트롤\)에 컨트롤을 채울 수 있습니다.  예를 들어 Windows 탐색기는 <xref:System.Windows.Forms.TreeView> 컨트롤을 창의 왼쪽에 도킹하고 <xref:System.Windows.Forms.ListView> 컨트롤을 창의 오른쪽에 도킹합니다.  표시할 수 있는 모든 Windows Forms 컨트롤은 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 사용하여 도킹 모드를 정의할 수 있습니다.  
  
> [!NOTE]
>  컨트롤은 Z 순서의 역순으로 도킹됩니다.  
  
 <xref:System.Windows.Forms.Control.Dock%2A> 속성은 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성과 상호 작용합니다.  자세한 내용은 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)를 참조하십시오.  
  
### 컨트롤을 도킹하려면  
  
1.  도킹할 컨트롤을 선택합니다.  
  
2.  속성 창에서 <xref:System.Windows.Forms.Control.Dock%2A> 속성의 오른쪽에 있는 화살표를 클릭합니다.  
  
     폼의 가장자리와 가운데를 나타내는 일련의 상자가 표시된 편집기가 나타납니다.  
  
3.  도킹하려는 가장자리에 해당하는 단추를 클릭합니다.  컨트롤을 포함하는 폼이나 컨테이너 컨트롤의 내용을 채우려면 가운데 상자를 클릭합니다.  도킹을 사용하지 않으려면 **\(없음\)**을 클릭합니다.  
  
     컨트롤의 크기는 도킹된 가장자리 경계에 맞게 자동으로 조정됩니다.  
  
    > [!NOTE]
    >  상속된 컨트롤을 도킹하려면 `Protected`를 설정해야 합니다.  컨트롤의 액세스 수준을 변경하려면 속성 창에서 컨트롤의 **Modifier** 속성을 설정합니다.  
  
## 참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)   
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)   
 [방법: FlowLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)   
 [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [방법: Windows Forms에서 컨트롤 고정](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)