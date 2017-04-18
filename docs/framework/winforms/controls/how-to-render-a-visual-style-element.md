---
title: "방법: 비주얼 스타일 요소 렌더링 | Microsoft Docs"
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
  - "전문적인 모양, Windows Forms 응용 프로그램의 요소에 적용"
  - "비주얼 스타일, Windows Forms 컨트롤 렌더링"
  - "비주얼 테마, Windows Forms 응용 프로그램의 요소에 적용"
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 비주얼 스타일 요소 렌더링
<xref:System.Windows.Forms.VisualStyles?displayProperty=fullName> 네임스페이스는 비주얼 스타일에서 지원되는 Windows UI\(사용자 인터페이스\) 요소를 나타내는 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> 개체를 노출합니다.  이 항목에서는 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 클래스를 사용하여 시작 메뉴의 **로그오프** 및 **종료** 단추를 나타내는 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement>를 렌더링하는 방법을 보여 줍니다.  
  
### 비주얼 스타일 요소를 렌더링하려면  
  
1.  <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer>를 만든 다음 그리려는 요소에 설정합니다.  <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=fullName> 속성 및 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=fullName> 메서드를 사용할 때 비주얼 스타일을 사용할 수 없거나 요소가 정의되지 않은 경우 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> 생성자는 예외를 throw합니다.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2.  <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> 메서드를 호출하여 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer>가 현재 나타내고 있는 요소를 렌더링합니다.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System.Windows.Forms.Control> 클래스에서 파생된 사용자 지정 컨트롤  
  
-   사용자 지정 컨트롤을 호스팅하는 <xref:System.Windows.Forms.Form>  
  
-   <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> 및 <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName> 네임스페이스에 대한 참조  
  
## 참고 항목  
 [비주얼 스타일을 사용하여 컨트롤 렌더링](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)