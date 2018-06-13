---
title: '방법: 슬라이더의 틱 사용자 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 667ec5d5504e18449800598f0b14548b7463bdf3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550880"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a>방법: 슬라이더의 틱 사용자 지정
만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Slider> 눈금이 있는 컨트롤입니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.Controls.Primitives.TickBar> 설정 하는 경우 표시는 <xref:System.Windows.Controls.Slider.TickPlacement%2A> 속성 이외의 값을 <xref:System.Windows.Controls.Primitives.TickPlacement.None>은 기본 값입니다.  
  
 만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.Slider> 와 <xref:System.Windows.Controls.Primitives.TickBar> 는 눈금을 표시 합니다. <xref:System.Windows.Controls.Slider.TickPlacement%2A> 및 <xref:System.Windows.Controls.Slider.TickFrequency%2A> 속성 눈금 표시와 사이의 간격의 위치를 정의 합니다. 이동 하는 경우는 <xref:System.Windows.Controls.Primitives.Thumb>, 도구 설명의 값을 표시는 <xref:System.Windows.Controls.Slider>합니다. <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> 속성 도구 설명을 수행 하는 위치를 정의 합니다. <xref:System.Windows.Controls.Primitives.Thumb> 있기 때문에 이동 눈금 표시의 위치를 일치 <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> 로 설정 된 `true`합니다.  
  
 사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.Slider.Ticks%2A> 속성을 따라 눈금을 만드는 <xref:System.Windows.Controls.Slider> 불규칙 한 간격입니다.  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Slider>  
 <xref:System.Windows.Controls.Primitives.TickBar>  
 <xref:System.Windows.Controls.Slider.TickPlacement%2A>  
 [Slider 방법 항목](http://msdn.microsoft.com/library/534be86c-afb2-425d-8186-631278a9925e)
