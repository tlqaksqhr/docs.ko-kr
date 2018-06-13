---
title: '방법: ScrollBar의 Thumb 크기 사용자 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 689b73eb58cdfceb2ce5d4e76cbbc3d6c5af8967
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551806"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a>방법: ScrollBar의 Thumb 크기 사용자 지정
이 항목에서는 설정 하는 방법에 설명 된 <xref:System.Windows.Controls.Primitives.Thumb> 의 <xref:System.Windows.Controls.Primitives.ScrollBar> 최소 크기를 지정 하는 방법 및 고정된 크기는 <xref:System.Windows.Controls.Primitives.Thumb> 의 <xref:System.Windows.Controls.Primitives.ScrollBar>합니다.  
  
## <a name="example"></a>예제  
  
## <a name="description"></a>설명  
 다음 예제에서는 한 <xref:System.Windows.Controls.Primitives.ScrollBar> 올려진는 <xref:System.Windows.Controls.Primitives.Thumb> 고정 크기입니다. 예제에서는 <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> 속성은 <xref:System.Windows.Controls.Primitives.Thumb> 를 <xref:System.Double.NaN> 의 높이 설정 하 고는 <xref:System.Windows.Controls.Primitives.Thumb>합니다.  가로 만들려면 <xref:System.Windows.Controls.Primitives.ScrollBar> 와 <xref:System.Windows.Controls.Primitives.Thumb> 고정된 폭을의 너비를 설정는 <xref:System.Windows.Controls.Primitives.Thumb>합니다.  
  
## <a name="code"></a>코드  
 [!code-xaml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a>설명  
 다음 예제에서는 한 <xref:System.Windows.Controls.Primitives.ScrollBar> 올려진는 <xref:System.Windows.Controls.Primitives.Thumb> 최소 크기입니다. 값을 설정 하는 예제 <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>합니다. 가로 만들려면 <xref:System.Windows.Controls.Primitives.ScrollBar> 와 <xref:System.Windows.Controls.Primitives.Thumb> 최소 너비, 설정는 <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>합니다.  
  
## <a name="code"></a>코드  
 [!code-xaml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a>참고 항목  
 [ScrollBar 스타일 및 템플릿](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)
