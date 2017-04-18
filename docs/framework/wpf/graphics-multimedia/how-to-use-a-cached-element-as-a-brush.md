---
title: "방법: 캐시된 요소를 브러시로 사용 | Microsoft Docs"
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
  - "BitmapCache[WPF], using"
  - "BitmapCacheBrush[WPF], using"
  - "캐시된 요소[WPF], 브러시로 사용"
  - "CacheMode[WPF], using"
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 캐시된 요소를 브러시로 사용
<xref:System.Windows.Media.BitmapCacheBrush> 클래스를 사용하여 캐시된 요소를 효과적으로 다시 사용할 수 있습니다.  요소를 캐시하려면 <xref:System.Windows.Media.BitmapCache> 클래스의 새 인스턴스를 만들어 해당 요소의 <xref:System.Windows.UIElement.CacheMode%2A> 속성에 할당합니다.  
  
## 예제  
 다음 코드 예제에서는 캐시된 요소를 다시 사용하는 방법을 보여 줍니다.  캐시된 요소는 큰 이미지를 표시하는 <xref:System.Windows.Controls.Image> 컨트롤입니다.  <xref:System.Windows.Controls.Image> 컨트롤은 <xref:System.Windows.Media.BitmapCache> 클래스를 사용하여 비트맵으로 캐시되며, 해당 캐시는 <xref:System.Windows.Media.BitmapCacheBrush>에 할당됨으로써 다시 사용됩니다.  브러시는 25개 단추의 배경에 할당되어 효과적인 재사용 방식을 보여 줍니다.  
  
 [!code-xml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## 참고 항목  
 <xref:System.Windows.Media.BitmapCache>   
 <xref:System.Windows.Media.BitmapCacheBrush>   
 <xref:System.Windows.UIElement.CacheMode%2A>   
 [방법: 요소를 캐시하여 렌더링 성능 향상](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)