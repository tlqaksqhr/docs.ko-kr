---
title: "방법: TableLayoutPanel 컨트롤의 컨트롤 맞춤 및 늘이기 | Microsoft Docs"
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
  - "net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "컨트롤[Windows Forms], 맞추기"
  - "컨트롤[Windows Forms], 늘이기"
  - "TableLayoutPanel 컨트롤[Windows Forms], 컨트롤 늘이기"
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: TableLayoutPanel 컨트롤의 컨트롤 맞춤 및 늘이기
<xref:System.Windows.Forms.TableLayoutPanel>에서 <xref:System.Windows.Forms.Control.Anchor%2A> 및 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 사용하여 컨트롤을 맞추고 늘일 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 컨트롤을 맞추고 늘이려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 왼쪽 위 셀로 끌어 옵니다.  <xref:System.Windows.Forms.Button> 컨트롤이 셀 가운데에 맞춰집니다.  
  
3.  <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `Left, Right`로 설정합니다.  <xref:System.Windows.Forms.Button> 컨트롤이 셀 너비에 맞도록 늘어납니다.  
  
4.  <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `Top, Bottom`으로 설정합니다.  <xref:System.Windows.Forms.Button> 컨트롤이 셀 높이에 맞도록 늘어납니다.  
  
5.  <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성 값을 <xref:System.Windows.Forms.DockStyle>로 설정합니다.  <xref:System.Windows.Forms.Button> 컨트롤이 셀을 채우도록 확장됩니다.  
  
6.  <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성 값을 <xref:System.Windows.Forms.DockStyle>으로 설정합니다.  <xref:System.Windows.Forms.Button> 컨트롤이 원래 크기로 돌아오고 셀의 왼쪽 위 모퉁이로 이동합니다.  **Windows Forms 디자이너**의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성은 `Top, Left`로 설정되어 있습니다.  
  
7.  <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `Bottom, Right`로 설정합니다.  <xref:System.Windows.Forms.Button> 컨트롤이 셀의 오른쪽 아래 모퉁이로 이동합니다.  
  
8.  <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 <xref:System.Windows.Forms.AnchorStyles>으로 설정합니다.  <xref:System.Windows.Forms.Button> 컨트롤이 셀 가운데로 이동합니다.  
  
## 참고 항목  
 [TableLayoutPanel 컨트롤](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)