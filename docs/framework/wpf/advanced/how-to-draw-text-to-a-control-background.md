---
title: '방법: 컨트롤의 배경에 텍스트 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: f79ec4f2c394fdc9462f4fd00942673b4536d713
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-text-to-a-control39s-background"></a>방법: 컨트롤의 배경에 텍스트 그리기
텍스트 문자열을 변환 하 여 컨트롤의 배경에 직접 텍스트를 그릴 수 있습니다는 <xref:System.Windows.Media.FormattedText> 개체를 다음 개체를 컨트롤의 그리기 <xref:System.Windows.Media.DrawingContext>합니다. 파생 된 개체의 배경 그리기가이 기술을 사용할 수도 있습니다 <xref:System.Windows.Controls.Panel>와 같은 <xref:System.Windows.Controls.Canvas> 및 <xref:System.Windows.Controls.StackPanel>합니다.  
  
 ![텍스트를 배경으로 표시 하는 컨트롤](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")  
사용자 지정 텍스트 배경이 있는 컨트롤의 예  
  
## <a name="example"></a>예제  
 컨트롤의 배경에 그리려면 만들 새 <xref:System.Windows.Media.DrawingBrush> 개체 및 개체의 변환 된 텍스트를 그립니다. <xref:System.Windows.Media.DrawingContext>합니다. 그런 다음 새 할당 <xref:System.Windows.Media.DrawingBrush> 컨트롤의 배경 속성에 있습니다.  
  
 다음 코드 예제에서는 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Media.FormattedText> 개체와의 배경에 그리기는 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.Button> 개체입니다.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.FormattedText>  
 [서식 있는 텍스트 그리기](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
