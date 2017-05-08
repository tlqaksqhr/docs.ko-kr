---
title: "방법: 이벤트를 사용하여 롤오버 효과 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "요소 색, 변경"
  - "요소 색, 변경"
  - "롤오버 효과"
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 이벤트를 사용하여 롤오버 효과 만들기
이 예제에서는 마우스 포인터가 요소가 차지하는 영역으로 들어가고 나갈 때 요소의 색을 변경하는 방법을 보여 줍니다.  
  
 이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일과 코드 숨김 파일로 구성됩니다.  
  
> [!NOTE]
>  이 예제에서는 이벤트를 사용하는 방법을 보여 주지만 이와 같은 효과를 얻는 데 권장되는 방법은 스타일에서 <xref:System.Windows.Trigger>를 사용하는 것입니다.  자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하십시오.  
  
## 예제  
 다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]에서는 <xref:System.Windows.Controls.TextBlock>를 둘러싸는 <xref:System.Windows.Controls.Border>로 구성된 사용자 인터페이스를 만들고 <xref:System.Windows.Input.Mouse.MouseEnter> 및 <xref:System.Windows.UIElement.MouseLeave> 이벤트 처리기를 <xref:System.Windows.Controls.Border>에 연결합니다.  
  
 [!code-xml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 다음 코드 숨김은 <xref:System.Windows.UIElement.MouseEnter> 및 <xref:System.Windows.UIElement.MouseLeave> 이벤트 처리기를 만듭니다.  마우스 포인터가 <xref:System.Windows.Controls.Border>로 들어가면 <xref:System.Windows.Controls.Border>의 배경색이 빨강으로 변경되고,  마우스 포인터가 <xref:System.Windows.Controls.Border>를 나가면 <xref:System.Windows.Controls.Border>의 배경색이 다시 흰색으로 변경됩니다.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]