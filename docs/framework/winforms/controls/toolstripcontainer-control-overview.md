---
title: "ToolStripContainer 컨트롤 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ToolStripContainer"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "도구 모음[Windows Forms], 기본 제공 래프팅(rafting)"
  - "ToolStripContainer 컨트롤[Windows Forms], ToolStripContainer 컨트롤 정보"
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# ToolStripContainer 컨트롤 개요
<xref:System.Windows.Forms.ToolStripContainer>에는 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.StatusStrip> 컨트롤의 위치 지정과 래프팅\(rafting\)에 사용되는 패널이 왼쪽, 오른쪽, 위쪽 및 아래쪽에 있습니다.  여러 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 왼쪽 또는 오른쪽 <xref:System.Windows.Forms.ToolStripContainer>에 넣으면 세로로 스택되고  위쪽 또는 아래쪽 <xref:System.Windows.Forms.ToolStripContainer>에 넣으면 가로로 스택됩니다.  <xref:System.Windows.Forms.ToolStripContainer>의 가운데 <xref:System.Windows.Forms.ToolStripContentPanel>을 사용하여 폼에서 기존 컨트롤의 위치를 지정할 수 있습니다.  
  
 <xref:System.Windows.Forms.ToolStripContainer> 컨트롤의 일부 또는 모두를 디자인 타임에 직접 선택할 수 있으며 삭제도 가능합니다.  <xref:System.Windows.Forms.ToolStripContainer>의 각 패널은 확장과 축소가 가능하며 여기에 포함된 컨트롤에 따라 크기가 조정됩니다.  
  
### 중요한 ToolStripContainer 멤버  
  
|Name|설명|  
|----------|--------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<xref:System.Windows.Forms.ToolStripContainer>의 아래쪽 패널을 가져옵니다.|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<xref:System.Windows.Forms.ToolStripContainer>의 아래쪽 패널이 표시되는지 여부를 나타내는 값을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<xref:System.Windows.Forms.ToolStripContainer>의 왼쪽 패널을 가져옵니다.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<xref:System.Windows.Forms.ToolStripContainer>의 왼쪽 패널이 표시되는지 여부를 나타내는 값을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<xref:System.Windows.Forms.ToolStripContainer>의 오른쪽 패널을 가져옵니다.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<xref:System.Windows.Forms.ToolStripContainer>의 오른쪽 패널이 표시되는지 여부를 나타내는 값을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<xref:System.Windows.Forms.ToolStripContainer>의 위쪽 패널을 가져옵니다.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<xref:System.Windows.Forms.ToolStripContainer>의 위쪽 패널이 표시되는지 여부를 나타내는 값을 가져오거나 설정합니다.|  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStripContainer>   
 <xref:System.Windows.Forms.ToolStripContentPanel>