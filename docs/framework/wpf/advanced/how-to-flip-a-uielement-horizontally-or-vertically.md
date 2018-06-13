---
title: '방법: UIElement를 좌우 또는 상하 대칭 이동'
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 89dcf668f1fe361480dabdab227a35ea40c344a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544397"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a>방법: UIElement를 좌우 또는 상하 대칭 이동
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.ScaleTransform> 대칭는 <xref:System.Windows.UIElement> 가로 또는 세로로 합니다. 이 예제에서는 <xref:System.Windows.Controls.Button> 컨트롤 (의 형식을 <xref:System.Windows.UIElement>) 적용 하 여 대칭 이동는 <xref:System.Windows.Media.ScaleTransform> 를 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성입니다.  
  
## <a name="example"></a>예제  
 다음 그림에는 대칭 이동 하려면 단추 보여 줍니다.  
  
 ![변형이 없는 단추](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")  
UIElement 대칭 이동  
  
 다음 단추를 생성 하는 코드를 보여 줍니다.  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a>예제  
 단추를 가로로 대칭 이동 하려면 만듭니다는 <xref:System.Windows.Media.ScaleTransform> 설정 하 고 해당 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 속성을-1입니다. 적용 된 <xref:System.Windows.Media.ScaleTransform> 단추의에 <xref:System.Windows.UIElement.RenderTransform%2A> 속성입니다.  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 ![단추에 대 한 가로 대칭 이동 된 &#40;0, 0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")  
ScaleTransform을 적용 한 후 단추  
  
## <a name="example"></a>예제  
 앞의 그림에서 볼 수 있습니다, 단추 대칭 되는 이동 되었습니다. 단추 왼쪽된 위 모서리에서 대칭 때문입니다. 적용 하려는 위치에 있는 단추를 대칭 이동 된 <xref:System.Windows.Media.ScaleTransform> 센터에 모퉁이가 아니라 합니다. 쉽게 적용할 수는 <xref:System.Windows.Media.ScaleTransform> 센터 단추의 설정 하는 단추에 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성을 0.5, 0.5입니다.  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 ![가운데를 중심으로 가로 대칭 이동 된 단추](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")  
0.5, RenderTransformOrigin 되는 단추 0.5  
  
## <a name="example"></a>예제  
 단추를 세로로 대칭 이동 하려면 설정는 <xref:System.Windows.Media.ScaleTransform> 개체의 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 속성 대신 해당 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 속성입니다.  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 ![가운데를 중심으로 세로 대칭 이동 된 단추](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")  
세로로 대칭 이동 된 단추  
  
## <a name="see-also"></a>참고 항목  
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
