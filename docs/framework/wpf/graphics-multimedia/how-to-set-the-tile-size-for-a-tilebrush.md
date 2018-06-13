---
title: '방법: TileBrush의 바둑판 크기 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: 16f0a4b3a5c9b9075126ba6d8f19d65169f70921
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561750"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>방법: TileBrush의 바둑판 크기 설정
타일 크기를 설정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.TileBrush>합니다. 기본적으로는 <xref:System.Windows.Media.TileBrush> 완전히 사용자 칠하고 있는 영역을 채우는 한 분할을 생성 합니다. 설정 하 여이 동작을 재정의할 수는 <xref:System.Windows.Media.TileBrush.Viewport%2A> 및 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성입니다.  
  
 <xref:System.Windows.Media.TileBrush.Viewport%2A> 속성에 대 한 타일 크기를 지정 된 <xref:System.Windows.Media.TileBrush>합니다. 기본적으로 값은 <xref:System.Windows.Media.TileBrush.Viewport%2A> 속성은 그려지는 영역 크기를 기준으로 합니다. 확인 하는 <xref:System.Windows.Media.TileBrush.Viewport%2A> 는 절대 타일 크기를 지정 하는 속성 설정의 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성을 <xref:System.Windows.Media.BrushMappingMode.Absolute>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush>는 유형의 <xref:System.Windows.Media.TileBrush>, 타일을 사용 하 여 사각형을 그립니다. 이 예제에서는 각 타일을 출력 영역(사각형)의 50% x 50%로 설정합니다. 결과적으로 이미지 프로젝션 4개를 사용한 사각형이 그려집니다.  
  
 다음 그림에서는 예제가 생성하는 출력을 보여 줍니다.
  
 ![이미지 브러시를 사용한 바둑판식 배열 예제](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush>, 설정 해당 <xref:System.Windows.Media.TileBrush.Viewport%2A> 를 `0,0,25,25` 및 해당 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 를 <xref:System.Windows.Media.BrushMappingMode.Absolute>, 다른 사각형을 그리는 데 사용 합니다. 결과적으로 이 브러시는 너비 및 높이가 각각 25픽셀인 타일을 생성합니다.  
  
 다음 그림에서는 예제가 생성하는 출력을 보여 줍니다.  
  
 ![Viewport가 0,0,0.25,0.25인 바둑판 모양의 TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 앞의 예제는 큰 샘플의 일부입니다. 전체 샘플을 참조 하십시오. [ImageBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160005)합니다.  
  
 이 예제에서는 <xref:System.Windows.Media.ImageBrush> 클래스는 <xref:System.Windows.Media.TileBrush.Viewport%2A> 및 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성 다른 동일 하 게 작동 <xref:System.Windows.Media.TileBrush> 개체, 즉,에 대 한 <xref:System.Windows.Media.DrawingBrush> 및 <xref:System.Windows.Media.VisualBrush>합니다. 에 대 한 자세한 내용은 <xref:System.Windows.Media.ImageBrush> 및 다른 <xref:System.Windows.Media.TileBrush> 개체 참조 [이미지, 그리기, 및 시각적 개체를 사용 하 여 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.TileBrush>  
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [TileBrush로 다른 바둑판식 배열 패턴 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)
