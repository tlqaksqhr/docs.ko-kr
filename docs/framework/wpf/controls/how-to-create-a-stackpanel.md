---
title: '방법: StackPanel 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: 30f24d8dba7c09271a5957822439af6b64e05aca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553029"
---
# <a name="how-to-create-a-stackpanel"></a>방법: StackPanel 만들기
만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.StackPanel>합니다.  
  
## <a name="example"></a>예제  
 A <xref:System.Windows.Controls.StackPanel> 를 지정 된 방향에서 요소 쌓을 수 있습니다. 에 정의 된 속성을 사용 하 여 <xref:System.Windows.Controls.StackPanel>, 콘텐츠 이동 둘 다 수직으로 기본 설정인 또는 가로로 합니다.  
  
 5 개는 다음 예제에서는 세로로 쌓는 <xref:System.Windows.Controls.TextBlock> 가 서로 제어 <xref:System.Windows.Controls.Border> 및 <xref:System.Windows.Controls.Border.Background%2A>를 사용 하 여 <xref:System.Windows.Controls.StackPanel>합니다. 하지만 지정 되지 않은 자식 요소 <xref:System.Windows.FrameworkElement.Width%2A> 부모 창에 맞게 늘이기 있으며 자식 요소는 지정 된 <xref:System.Windows.FrameworkElement.Width%2A>, 창 내에서 가운데 맞춤 됩니다.  
  
 기본 스택 방향을 <xref:System.Windows.Controls.StackPanel> 는 세로입니다. 콘텐츠 흐름을 제어 하는 <xref:System.Windows.Controls.StackPanel>를 사용 하 여는 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 속성입니다. 사용 하 여 가로 맞춤을 제어할 수 있습니다는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성입니다.  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.StackPanel>  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/controls/stackpanel-how-to-topics.md)
