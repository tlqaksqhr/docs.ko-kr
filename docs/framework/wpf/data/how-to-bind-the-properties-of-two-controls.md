---
title: '방법: 두 컨트롤의 속성 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 02e71bfcc41fc3d256ea95381ed27d36b289b8f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555583"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>방법: 두 컨트롤의 속성 바인딩
사용 하 여 다른의 인스턴스화된 한 컨트롤의 속성을 바인딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Data.Binding.ElementName%2A> 속성입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 바인딩하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.Panel.Background%2A> 속성은 <xref:System.Windows.Controls.Canvas> 에 <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>합니다.<xref:System.Windows.Controls.ContentControl.Content%2A> 속성의는 <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 이 예를 렌더링하면 다음과 같이 표시됩니다.  
  
 ![녹색 배경이 있는 캔버스](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")  
  
 **참고** 바인딩 대상 속성 (이 예제는 <xref:System.Windows.Controls.Panel.Background%2A> 속성)은 종속성 속성 이어야 합니다. 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [바인딩 소스 지정](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
