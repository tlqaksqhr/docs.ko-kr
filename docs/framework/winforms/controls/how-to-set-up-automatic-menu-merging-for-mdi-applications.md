---
title: "방법: MDI 응용 프로그램의 자동 메뉴 병합 설정 | Microsoft Docs"
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
  - "MenuStrip, 병합"
  - "병합, 자동 메뉴"
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: MDI 응용 프로그램의 자동 메뉴 병합 설정
다음 절차에서는 <xref:System.Windows.Forms.MenuStrip>을 사용하여 MDI\(다중 문서 인터페이스\) 응용 프로그램의 자동 병합을 설정하기 위한 기본 단계를 제공합니다.  
  
### 자동 메뉴 병합을 설정하려면  
  
1.  <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정하여 MDI 부모 폼을 만듭니다.  
  
2.  MDI 부모에 <xref:System.Windows.Forms.MenuStrip>을 추가하고 이 컨트롤의 <xref:System.Windows.Forms.Form.MainMenuStrip%2A> 속성을 해당 <xref:System.Windows.Forms.MenuStrip>으로 설정합니다.  
  
3.  MDI 자식 폼을 만들고 해당 <xref:System.Windows.Forms.Form.MdiParent%2A> 속성을 부모 폼의 이름으로 설정합니다.  
  
4.  MDI 자식 폼에 <xref:System.Windows.Forms.MenuStrip>을 추가합니다.  
  
5.  자식 폼에서 <xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`로 설정합니다.  
  
6.  자식 폼이 활성화될 때 상위 폼의 <xref:System.Windows.Forms.MenuStrip>으로 병합하려는 자식 폼의 <xref:System.Windows.Forms.MenuStrip>에 메뉴 항목을 추가합니다.  
  
7.  자식 폼의 <xref:System.Windows.Forms.MenuStrip>의 메뉴 항목에 <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> 속성을 사용하여 메뉴 항목이 자식 폼에 병합되는 방식을 제어합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)