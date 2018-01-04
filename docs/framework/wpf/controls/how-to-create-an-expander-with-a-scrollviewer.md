---
title: "방법: ScrollViewer가 있는 Expander 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2066ccce28138cfecf4e0b4574d45783a9ba4ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a>방법: ScrollViewer가 있는 Expander 만들기
만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Expander> 이미지, 텍스트 등의 복잡 한 콘텐츠를 포함 하는 컨트롤입니다. 이 예제에서는 또한의 콘텐츠를 둘러싸는 <xref:System.Windows.Controls.Expander> 에 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다.  
  
## <a name="example"></a>예  
 만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.Expander>합니다. 이 예제에서는 사용는 <xref:System.Windows.Controls.Primitives.BulletDecorator> 제어를 정의 하기 위해 이미지 및 텍스트를 포함 하는 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>합니다. A <xref:System.Windows.Controls.ScrollViewer> 컨트롤은 확장 된 콘텐츠를 스크롤 하는 방법을 제공 합니다.  
  
 이 예제에서는 설정 하는 <xref:System.Windows.FrameworkElement.Height%2A> 속성에는 <xref:System.Windows.Controls.ScrollViewer> 대신 콘텐츠에 대. 경우는 <xref:System.Windows.FrameworkElement.Height%2A> 를 콘텐츠에 설정의 <xref:System.Windows.Controls.ScrollViewer> 사용자 콘텐츠를 스크롤할 수 없습니다. <xref:System.Windows.FrameworkElement.Width%2A> 속성이에 설정 되는 <xref:System.Windows.Controls.Expander> 컨트롤과이 설정에 적용 됩니다는 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 및 확장 된 콘텐츠입니다.  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Expander>  
 [Expander 개요](../../../../docs/framework/wpf/controls/expander-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
