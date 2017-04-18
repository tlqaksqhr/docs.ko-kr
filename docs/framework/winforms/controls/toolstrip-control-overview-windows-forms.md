---
title: "ToolStrip 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "Toolstrip"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "도구 모음[Windows Forms]"
  - "도구 모음[Windows Forms], Windows Forms의 새로운 기능"
  - "ToolStrip 컨트롤[Windows Forms], ToolStrip 컨트롤 정보"
  - "새로운 기능[Windows Forms], 도구 모음"
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# ToolStrip 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ToolStrip> 컨트롤 및 관련 클래스에서는 사용자 인터페이스 요소를 도구 모음, 상태 표시줄 및 메뉴에 통합하기 위한 공용 프레임워크를 제공합니다.  <xref:System.Windows.Forms.ToolStrip> 컨트롤은 내부 활성화 및 편집, 사용자 지정 레이아웃 및 도구 모음에서 가로 간격과 세로 간격을 공유하는 기능인 래프팅\(rafting\)을 비롯하여 다양한 디자인 타임 기능을 제공합니다.  
  
 <xref:System.Windows.Forms.ToolStrip>은 이전 버전의 컨트롤에 새로운 기능이 추가된 것으로, 이전 컨트롤을 대체합니다. 그러나 이전 버전과의 호환성 및 앞으로의 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar>를 유지하도록 선택할 수 있습니다.  
  
## ToolStrip 컨트롤의 기능  
 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 사용하여 다음 작업을 수행할 수 있습니다.  
  
-   컨테이너 간에 공용 사용자 인터페이스를 표시할 수 있습니다.  
  
-   도킹, 래프팅\(rafting\), 텍스트와 이미지가 있는 단추, 드롭다운 단추와 컨트롤, 오버플로 단추 및 <xref:System.Windows.Forms.ToolStrip> 항목의 런타임 다시 정렬 같은 레이아웃 기능과 고급 사용자 인터페이스를 지원하는 일반적인 사용자 지정 도구 모음을 쉽게 만들 수 있습니다.  
  
-   오버플로 및 런타임 항목 재정렬을 지원할 수 있습니다.  오버플로 기능을 사용하면 <xref:System.Windows.Forms.ToolStrip>에 항목을 표시할 충분한 공간이 없을 때 해당 항목이 드롭다운 메뉴로 이동합니다.  
  
-   일반적인 렌더링 모델을 통해 운영 체제의 일반적인 모양과 동작을 지원할 수 있습니다.  
  
-   모든 컨테이너와 포함된 항목에 대한 이벤트를 다른 컨트롤에 대한 이벤트를 처리할 때와 같은 방법으로 일관성 있게 처리할 수 있습니다.  
  
-   <xref:System.Windows.Forms.ToolStrip> 간 또는 <xref:System.Windows.Forms.ToolStrip> 내에서 항목을 끌어올 수 있습니다.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown>의 고급 레이아웃을 사용하여 드롭다운 컨트롤과 사용자 인터페이스 형식 편집기를 만들 수 있습니다.  
  
 <xref:System.Windows.Forms.ToolStripControlHost> 클래스를 사용하여 <xref:System.Windows.Forms.ToolStrip>의 다른 컨트롤을 사용하고 해당 <xref:System.Windows.Forms.ToolStrip> 기능을 가져올 수 있습니다.  
  
 <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 및 <xref:System.Windows.Forms.ToolStripManager>를 <xref:System.Windows.Forms.ToolStripRenderMode> 및 <xref:System.Windows.Forms.ToolStripManagerRenderMode> 열거형과 함께 사용하여 기능을 확장하거나 모양과 동작을 수정할 수 있습니다.  
  
 <xref:System.Windows.Forms.ToolStrip> 컨트롤은 매우 다양하게 구성하고 확장할 수 있으며, 모양과 동작을 사용자 지정할 수 있는 여러 가지 속성, 메서드 및 이벤트를 제공합니다.  다음은 몇 가지 중요한 멤버입니다.  
  
### 중요한 ToolStrip 멤버  
  
|Name|설명|  
|----------|--------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|<xref:System.Windows.Forms.ToolStrip>이 도킹되는 부모 컨테이너 가장자리를 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|<xref:System.Windows.Forms.ToolStrip> 클래스를 통해 끌어서 놓기와 항목 다시 정렬을 전용으로 처리할지 여부를 나타내는 값을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|<xref:System.Windows.Forms.ToolStrip>에서 항목을 레이아웃하는 방법을 나타내는 값을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|<xref:System.Windows.Forms.ToolStripItem>이 <xref:System.Windows.Forms.ToolStrip> 또는 <xref:System.Windows.Forms.ToolStripOverflowButton>에 연결되는지 여부 또는 이 둘 사이에서 부동 항목으로 유지될 수 있는지 여부를 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|<xref:System.Windows.Forms.ToolStripItem>을 클릭할 경우 <xref:System.Windows.Forms.ToolStripItem>이 드롭다운 목록의 다른 항목을 표시할지 여부를 나타내는 값을 가져옵니다.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|오버플로가 활성화된 <xref:System.Windows.Forms.ToolStrip>에 대한 오버플로 단추인 <xref:System.Windows.Forms.ToolStripItem>을 가져옵니다.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|<xref:System.Windows.Forms.ToolStrip>의 모양과 동작\(모양과 느낌\)을 사용자 지정하는 데 사용되는 <xref:System.Windows.Forms.ToolStripRenderer>를 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|<xref:System.Windows.Forms.ToolStrip>에 적용될 그리기 스타일을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|<xref:System.Windows.Forms.ToolStrip.Renderer%2A> 속성이 변경되면 발생합니다.|  
  
 여러 가지 동반 클래스를 통해 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 융통성 있게 사용할 수 있습니다.  다음은 가장 중요한 동반 클래스입니다.  
  
### 중요한 ToolStrip 동반 클래스  
  
|Name|설명|  
|----------|--------|  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Forms.MainMenu> 클래스를 대체하고 여기에 다른 기능을 추가합니다.|  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Forms.StatusBar> 클래스를 대체하고 여기에 다른 기능을 추가합니다.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Forms.ContextMenu> 클래스를 대체하고 여기에 다른 기능을 추가합니다.|  
|<xref:System.Windows.Forms.ToolStripItem>|<xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost> 또는 <xref:System.Windows.Forms.ToolStripDropDown>에 포함될 수 있는 모든 요소의 이벤트와 레이아웃을 관리하는 추상 기본 클래스입니다.|  
|<xref:System.Windows.Forms.ToolStripContainer>|다양한 방식으로 컨트롤을 정렬할 수 있는 폼 양쪽의 패널을 컨테이너에 제공합니다.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|<xref:System.Windows.Forms.ToolStrip> 개체에 대한 그리기 기능을 처리합니다.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Microsoft Office 스타일 모양을 제공합니다.|  
|<xref:System.Windows.Forms.ToolStripManager>|<xref:System.Windows.Forms.ToolStrip> 렌더링 및 래프팅\(rafting\)과 <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> 및 <xref:System.Windows.Forms.ToolStripMenuItem> 개체의 병합을 제어합니다.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|폼에 포함된 여러 <xref:System.Windows.Forms.ToolStrip> 개체에 적용되는 그리기 스타일\(사용자 지정, Windows XP 또는 Microsoft Office Professional\)을 지정합니다.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|폼에 포함된 하나의 <xref:System.Windows.Forms.ToolStrip> 개체에 적용되는 그리기 스타일\(사용자 지정, Windows XP 또는 Microsoft Office Professional\)을 지정합니다.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|정확하게 <xref:System.Windows.Forms.ToolStrip> 컨트롤은 아니지만 <xref:System.Windows.Forms.ToolStrip> 기능을 사용하려는 다른 컨트롤을 호스팅합니다.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|<xref:System.Windows.Forms.ToolStripItem>을 기본 <xref:System.Windows.Forms.ToolStrip>에 레이아웃할지 오버플로 <xref:System.Windows.Forms.ToolStrip>에 레이아웃할지 아니면 어느 쪽에도 레이아웃하지 않을지를 지정합니다.|  
  
 자세한 내용은 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md) 및 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripDropDown>