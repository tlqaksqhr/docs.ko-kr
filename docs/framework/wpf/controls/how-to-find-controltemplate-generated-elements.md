---
title: "방법: ControlTemplate에서 생성된 요소 찾기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f81069873930af57e1f6ab2f3e0408b4d53f38b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-controltemplate-generated-elements"></a>방법: ControlTemplate에서 생성된 요소 찾기
생성 되는 요소를 찾는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 간단한 만드는 스타일을 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Button> 클래스:  
  
 [!code-xaml[FindGeneratedItems#CT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 서식 파일에 있는 요소를 찾으려면 템플릿을 적용 된 후 호출할 수 있습니다는 <xref:System.Windows.FrameworkTemplate.FindName%2A> 의 메서드는 <xref:System.Windows.Controls.Control.Template%2A>합니다. 다음 예제에서는의 실제 너비 값을 표시 하는 메시지 상자는 <xref:System.Windows.Controls.Grid> 컨트롤 템플릿 내에서:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>참고 항목  
 [DataTemplate에서 생성된 요소 찾기](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [WPF XAML 이름 범위](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
