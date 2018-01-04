---
title: "방법: 요소를 캐시하여 렌더링 성능 향상"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9cd12b811ae4dd89c645ada1f4f70b06f73b9b13
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a>방법: 요소를 캐시하여 렌더링 성능 향상
사용 하 여는 <xref:System.Windows.Media.BitmapCache> 복잡 한의 렌더링 성능을 개선 하기 위해 클래스 <xref:System.Windows.UIElement>합니다. 새 인스턴스를 만들고 요소를 캐시 하려면는 <xref:System.Windows.Media.BitmapCache> 클래스 및 요소에 할당할 <xref:System.Windows.UIElement.CacheMode%2A> 속성입니다. 다시 사용할 수는 <xref:System.Windows.Media.BitmapCache> 에 효율적으로 한 <xref:System.Windows.Media.BitmapCacheBrush>합니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 요소 애니메이션 될 때 성능을 향상 시키는 비트맵으로 캐시 하는 복잡 한 요소를 만드는 방법을 보여 줍니다. 많은 꼭 짓 점 기 하 도형을 포함 하는 캔버스입니다. A <xref:System.Windows.Media.BitmapCache> 에 할당 된 값 이며 기본값은는 <xref:System.Windows.UIElement.CacheMode%2A> 를 캔버스의 애니메이션 캐시 된 비트맵의 부드러운 크기 조정을 보여 줍니다.  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [방법: 캐시된 요소를 브러시로 사용](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
