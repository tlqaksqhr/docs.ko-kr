---
title: "방법: ControlTemplate에서 생성된 요소 찾기 | Microsoft Docs"
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
  - "ControlTemplates[WPF], 요소 찾기"
  - "ControlTemplate 요소 찾기"
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: ControlTemplate에서 생성된 요소 찾기
이 예제에서는 <xref:System.Windows.Controls.ControlTemplate>에 의해 생성된 요소를 찾는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.Button> 클래스에 대해 간단한 <xref:System.Windows.Controls.ControlTemplate>을 만드는 스타일을 보여 줍니다.  
  
 [!code-xml[FindGeneratedItems#CT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 템플릿이 적용된 다음 템플릿 내에서 요소를 찾기 위해 <xref:System.Windows.Controls.Control.Template%2A>의 <xref:System.Windows.FrameworkTemplate.FindName%2A> 메서드를 호출할 수 있습니다.  다음 예제에서는 컨트롤 템플릿 내에서 <xref:System.Windows.Controls.Grid>의 실제 너비 값을 표시하는 메시지 상자를 만듭니다.  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## 참고 항목  
 [DataTemplate에서 생성된 요소 찾기](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [WPF XAML 이름 범위](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)   
 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)