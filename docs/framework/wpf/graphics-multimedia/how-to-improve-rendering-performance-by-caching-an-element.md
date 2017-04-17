---
title: "방법: 요소를 캐시하여 렌더링 성능 향상 | Microsoft Docs"
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
  - "BitmapCache[WPF], 렌더링 성능 향상"
  - "CacheMode[WPF], 렌더링 성능 향상"
  - "성능[WPF], 요소 캐싱"
  - "렌더링 성능[WPF], 요소 캐싱"
  - "UIElement[WPF], 캐싱"
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 요소를 캐시하여 렌더링 성능 향상
<xref:System.Windows.Media.BitmapCache> 클래스를 사용하여 복합 <xref:System.Windows.UIElement>의 렌더링 성능을 향상시킬 수 있습니다.  요소를 캐시하려면 <xref:System.Windows.Media.BitmapCache> 클래스의 새 인스턴스를 만들어 해당 요소의 <xref:System.Windows.UIElement.CacheMode%2A> 속성에 할당합니다.  <xref:System.Windows.Media.BitmapCacheBrush>에서는 <xref:System.Windows.Media.BitmapCache>를 효과적으로 다시 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 복합 요소를 만들고 이를 비트맵으로 캐시하여 요소에 애니메이션 효과를 줄 때의 성능을 향상시키는 방법을 보여 줍니다.  이 요소는 꼭짓점이 여러 개인 기하 도형을 포함하는 캔버스입니다.  캔버스의 <xref:System.Windows.UIElement.CacheMode%2A>에는 기본값을 갖는 <xref:System.Windows.Media.BitmapCache>가 할당되며, 애니메이션에서는 캐시된 비트맵의 부드러운 배율 조정을 보여 줍니다.  
  
 [!code-xml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## 참고 항목  
 <xref:System.Windows.Media.BitmapCache>   
 <xref:System.Windows.Media.BitmapCacheBrush>   
 <xref:System.Windows.UIElement.CacheMode%2A>   
 [방법: 캐시된 요소를 브러시로 사용](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)