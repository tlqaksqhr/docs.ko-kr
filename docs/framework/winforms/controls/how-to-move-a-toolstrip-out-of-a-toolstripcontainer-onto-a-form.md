---
title: "방법: ToolStripContainer의 ToolStrip을 폼으로 이동 | Microsoft Docs"
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
  - "ToolStrip 컨트롤[Windows Forms], 폼의 부모로 지정"
  - "Windows Forms, ToolStrip 컨트롤을 부모로 지정"
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: ToolStripContainer의 ToolStrip을 폼으로 이동
다음 절차에 따라 <xref:System.Windows.Forms.ToolStripContainer>의 <xref:System.Windows.Forms.ToolStrip>을 폼으로 이동합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### ToolStripContainer의 ToolStrip을 폼으로 이동하려면  
  
1.  <xref:System.Windows.Forms.ToolStrip>를 선택합니다.  
  
2.  Ctrl\+X를 눌러 <xref:System.Windows.Forms.ToolStrip>을 잘라내거나 <xref:System.Windows.Forms.ToolStrip>을 마우스 오른쪽 단추로 클릭한 다음 상황에 맞는 메뉴에서 **잘라내기**를 선택합니다.  
  
3.  폼을 선택합니다.  
  
4.  Ctrl\+V를 눌러 <xref:System.Windows.Forms.ToolStrip>을 붙여넣거나 **편집** 메뉴에서 **붙여넣기**를 선택합니다.  
  
5.  <xref:System.Windows.Forms.ToolStrip>의 <xref:System.Windows.Forms.ToolStrip.Dock%2A> 속성을 **Top**으로 설정합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripContainer>   
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)