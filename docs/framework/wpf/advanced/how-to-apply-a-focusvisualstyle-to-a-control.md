---
title: "방법: 컨트롤에 FocusVisualStyle 적용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f614e244293d08cd836edaf82496ca9e7b51423e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>방법: 컨트롤에 FocusVisualStyle 적용
이 예제에서는 리소스에서 포커스 비주얼 스타일을 만들고 컨트롤에 스타일을 적용 하는 방법을 보여 줍니다. 사용 하는 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 속성입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 컨트롤에 키보드에 포커스가 있을 때만 적용 되는 추가 컨트롤 구성을 만드는 스타일을 정의 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]합니다. 사용 하 여 스타일을 정의 하 여 이렇게는 <xref:System.Windows.Controls.ControlTemplate>를 설정할 때 해당 스타일 리소스로 참조 한 다음는 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 속성입니다.  
  
 외부 테두리와 비슷한 사각형이 사각형 영역 바깥쪽에 배치 됩니다. 스타일의 크기 조정에 사용 하 여을 수정 하지 않은 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 및 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 포커스 비주얼 스타일이 적용 되는 사각형 컨트롤의 합니다. 에 대해 음수 값을 설정 하는이 예제는 <xref:System.Windows.FrameworkElement.Margin%2A> 테두리 포커스가 있는 컨트롤 밖에 약간 표시 되도록 합니다.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 은 가산적 제공 되는 모든 컨트롤 템플릿 스타일에 명시적 스타일 또는 테마 스타일;에서 컨트롤에 대 한 기본 스타일 여전히 만들 수 있습니다를 사용 하 여는 <xref:System.Windows.Controls.ControlTemplate> 해당 스타일을 설정 하 고는 <xref:System.Windows.FrameworkElement.Style%2A> 속성입니다.  
  
 비주얼 스타일 테마 또는 UI를 통해 지속적으로 사용 해야 하는 포커스 포커스 각 요소에 대해 다른 하나를 사용 하는 대신 합니다. 자세한 내용은 참조 [컨트롤과 FocusVisualStyle에 포커스에 대 한 스타일 지정](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [컨트롤의 포커스 스타일 지정 및 FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)
