---
title: "방법: 요소 변환 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "클래스, TranslateTransform"
  - "그래픽, 변환"
  - "TranslateTransform 클래스"
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 요소 변환
이 예제에서는 <xref:System.Windows.Media.TranslateTransform>을 사용하여 요소를 변환\(이동\)하는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Media.TranslateTransform> 클래스는 절대 위치 지정을 지원하지 않는 패널 내에서 요소를 이동하려는 경우 특히 유용합니다.  예를 들어 요소의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 <xref:System.Windows.Media.TranslateTransform>을 적용하여 <xref:System.Windows.Controls.StackPanel> 또는 <xref:System.Windows.Controls.DockPanel> 내에서 요소를 이동할 수 있습니다.  
  
 <xref:System.Windows.Media.TranslateTransform>의 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성을 사용하여 x축을 따라 요소를 이동할 거리를 [픽셀](GTMT)로 지정합니다.  <xref:System.Windows.Media.TranslateTransform.Y%2A> 속성을 사용하여 y축을 따라 요소를 이동할 거리를 픽셀로 지정합니다.  마지막으로 요소의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 <xref:System.Windows.Media.TranslateTransform>을 적용합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.TranslateTransform>을 사용하여 오른쪽과 아래쪽으로 각각 50[픽셀](GTMT)씩 요소를 이동합니다.  
  
## 예제  
 [!code-xml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 전체 샘플을 보려면 [2\-D Transforms 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)을 참조하십시오.  
  
## 참고 항목  
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)