---
title: "방법: 컨트롤 렌더링 클래스 사용 | Microsoft Docs"
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
  - "전문적인 모양, Windows Forms 컨트롤 렌더링"
  - "비주얼 스타일, Windows Forms 컨트롤 렌더링"
  - "비주얼 테마, Windows Forms 컨트롤에 적용"
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 컨트롤 렌더링 클래스 사용
이 예제에서는 <xref:System.Windows.Forms.ComboBoxRenderer> 클래스를 사용하여 콤보 상자 컨트롤의 드롭다운 화살표를 렌더링하는 방법을 보여 줍니다.  이 예제는 간단한 사용자 지정 컨트롤의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드로 구성되어 있습니다.  <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=fullName> 속성은 응용 프로그램 창의 클라이언트 영역에서 비주얼 스타일을 사용할 수 있는지 여부를 결정하는 데 사용됩니다.  비주얼 스타일이 활성 상태이면 <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=fullName> 메서드가 비주얼 스타일로 드롭다운 화살표를 렌더링하고, 그렇지 않으면 <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=fullName> 메서드가 기본 Windows 스타일로 드롭다운 화살표를 렌더링합니다.  
  
## 예제  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System.Windows.Forms.Control> 클래스에서 파생된 사용자 지정 컨트롤  
  
-   사용자 지정 컨트롤을 호스팅하는 <xref:System.Windows.Forms.Form>  
  
-   <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> 및 <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName> 네임스페이스에 대한 참조  
  
## 참고 항목  
 [비주얼 스타일을 사용하여 컨트롤 렌더링](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)