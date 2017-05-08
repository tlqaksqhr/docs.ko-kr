---
title: "방법: 컨트롤에 FocusVisualStyle 적용 | Microsoft Docs"
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
  - "FocusVisualStyle 속성"
  - "속성, FocusVisualStyle"
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 컨트롤에 FocusVisualStyle 적용
이 예제에서는 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 속성을 사용하여 리소스에서 포커스 비주얼 스타일을 만들고 이 스타일을 컨트롤에 적용하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에서 컨트롤에 키보드 포커스가 있을 때에만 적용되는 추가 컨트롤 구성을 만드는 스타일을 정의합니다.  이를 위해서 <xref:System.Windows.Controls.ControlTemplate>으로 스타일을 정의한 다음 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 속성을 설정할 때 이 스타일을 리소스로 참조합니다.  
  
 사각형 영역 바깥쪽에 테두리와 비슷한 외부 사각형이 배치됩니다.  다른 방식으로 수정하지 않으면 스타일의 크기 조정에는 포커스 비주얼 스타일이 적용되는 사각형 컨트롤의 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 및 <xref:System.Windows.FrameworkElement.ActualWidth%2A>가 사용됩니다.  이 예제에서는 <xref:System.Windows.FrameworkElement.Margin%2A>에 음수 값을 설정하여 포커스가 있는 컨트롤보다 약간 바깥쪽에 테두리가 나타나게 만듭니다.  
  
 [!code-xml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>은 명시적 스타일이나 테마 스타일에서 가져온 모든 컨트롤 템플릿에 추가할 수 있습니다. 계속해서 <xref:System.Windows.Controls.ControlTemplate>을 사용하고 해당 스타일을 <xref:System.Windows.FrameworkElement.Style%2A> 속성에 설정하여 컨트롤의 기본 스타일을 만들 수 있습니다.  
  
 포커스를 가질 수 있는 각 요소마다 다른 포커스 비주얼 스타일을 사용하는 것이 아니라 테마나 UI 전체에서 일관성 있는 포커스 비주얼 스타일을 사용해야 합니다.  자세한 내용은 [컨트롤의 포커스 스타일 지정 및 FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [컨트롤의 포커스 스타일 지정 및 FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)