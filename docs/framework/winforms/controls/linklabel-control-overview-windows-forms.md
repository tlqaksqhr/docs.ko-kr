---
title: "LinkLabel 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "LinkLabel"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Label 컨트롤[Windows Forms], Label 컨트롤 정보"
  - "LinkLabel 컨트롤[Windows Forms], LinkLabel 컨트롤 정보"
  - "링크, LinkLabel 컨트롤"
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# LinkLabel 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.LinkLabel> 컨트롤을 사용하면 Windows Forms 응용 프로그램에 웹 스타일 링크를 추가할 수 있습니다.  <xref:System.Windows.Forms.LinkLabel> 컨트롤을 사용할 수 있는 모든 대상에 <xref:System.Windows.Forms.Label> 컨트롤을 사용할 수 있습니다. 또한 텍스트 일부를 파일, 폴더 또는 웹 페이지의 링크로 설정할 수도 있습니다.  
  
## LinkLabel 컨트롤로 할 수 있는 작업  
 <xref:System.Windows.Forms.LinkLabel> 컨트롤은 <xref:System.Windows.Forms.Label> 컨트롤의 모든 속성, 메서드 및 이벤트는 물론 하이퍼링크 및 링크 색에 대한 속성도 가지고 있습니다.  <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성은 활성화된 링크의 텍스트 영역을 설정합니다.  <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 및 <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> 속성은 링크의 색을 설정합니다.  <xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트는 링크 텍스트가 선택되면 실행할 동작을 지정합니다.  
  
 <xref:System.Windows.Forms.LinkLabel> 컨트롤의 가장 간단한 용도는 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 사용하여 단일 링크를 표시하는 것이지만 <xref:System.Windows.Forms.LinkLabel.Links%2A> 속성을 사용하여 여러 하이퍼링크를 표시할 수도 있습니다.  <xref:System.Windows.Forms.LinkLabel.Links%2A> 속성을 사용하면 링크 컬렉션에 액세스할 수 있습니다.  개별 <xref:System.Windows.Forms.LinkLabel.Link> 개체의 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 속성에 데이터를 지정할 수도 있습니다.  표시할 파일의 위치 또는 웹 사이트의 주소를 저장하는 데 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 속성의 값을 사용할 수도 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.LinkLabel>   
 [Label 컨트롤 개요](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)   
 [방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)   
 [방법: Windows Forms LinkLabel 컨트롤의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)