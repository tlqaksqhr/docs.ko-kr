---
title: '방법: 단색으로 영역 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: 7e8e3fa5a379f02c3bb126c17bbe37fc0f3d57cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561334"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>방법: 단색으로 영역 그리기
단색으로 영역을 그리는 데 사용할 수 있습니다는 미리 정의 된 시스템 브러시와 같은 <xref:System.Windows.Media.Brushes.Red%2A> 또는 <xref:System.Windows.Media.Brushes.Blue%2A>, 또는 새를 만들 수 있습니다 <xref:System.Windows.Media.SolidColorBrush> 설명 및 해당 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 알파, 빨간색, 녹색 및 파랑 값을 사용 하 합니다. XAML에서 16진수 표기법을 사용하여 단색으로 영역을 그릴 수도 있습니다.  
  
 다음 예에서는를 사용 하 여 각이 방법을 페인트는 <xref:System.Windows.Shapes.Rectangle> 파란색입니다.  
  
## <a name="example"></a>예제  
 **미리 정의된 브러시 사용**  
  
 다음 예제에서 미리 정의 된 브러시를 사용 하 여 <xref:System.Windows.Media.Brushes.Blue%2A> 파란색 사각형을 그리는 데 합니다.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **16진수 표기법 사용**  
  
 다음 예제에서는 8자리 16진수 표기법을 사용하여 파란색 사각형을 그립니다.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **ARGB 값 사용**  
  
 다음 예제에서는 한 <xref:System.Windows.Media.SolidColorBrush> 설명 및 해당 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 파란색에 대 한 값은 ARGB를 사용 하 여 합니다.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 다른 색을 설명 하는 방법에 대 한 참조는 <xref:System.Windows.Media.Color> 구조입니다.  
  
 **관련 항목**  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Media.SolidColorBrush> 추가 예제를 참조 하 고는 [단색 및 그라데이션 개요 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) 개요입니다.  
  
 이 코드 예제는에 대해 제공 된 큰 예제의 일부는 <xref:System.Windows.Media.SolidColorBrush> 클래스입니다. 전체 샘플을 보려면 [브러시 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Brushes>
