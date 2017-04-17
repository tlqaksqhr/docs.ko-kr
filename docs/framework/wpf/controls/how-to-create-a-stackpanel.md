---
title: "방법: StackPanel 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "StackPanel 컨트롤 만들기"
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: StackPanel 만들기
만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.StackPanel>합니다.  
  
## <a name="example"></a>예제  
 A <xref:System.Windows.Controls.StackPanel> 를 지정 된 방향으로 요소를 쌓을 수 있습니다. 에 정의 된 속성을 사용 하 여 <xref:System.Windows.Controls.StackPanel>, 콘텐츠 진행 될 수 있습니다 세로 형태로 정리 하는 기본 설정 또는 가로로 합니다.  
  
 5 개는 다음 예제에서는 세로로 쌓는 <xref:System.Windows.Controls.TextBlock> 가 서로 제어 <xref:System.Windows.Controls.Border> 및 <xref:System.Windows.Controls.Border.Background%2A>를 사용 하 여 <xref:System.Windows.Controls.StackPanel>합니다. 지정 되지 않은 자식 요소 <xref:System.Windows.FrameworkElement.Width%2A> 부모 창에 맞게 확장 합니다; 그러나 자식 요소는 지정 된 <xref:System.Windows.FrameworkElement.Width%2A>, 창 내에서 가운데 맞춤 됩니다.  
  
 기본 스택 방향을 <xref:System.Windows.Controls.StackPanel> 는 세로입니다. 콘텐츠 흐름을 제어 하는 <xref:System.Windows.Controls.StackPanel>를 사용 하 여는 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 속성입니다. 사용 하 여 가로 맞춤을 제어할 수는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성입니다.  
  
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
 [개요 패널](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [방법 도움말 항목](../../../../docs/framework/wpf/controls/stackpanel-how-to-topics.md)