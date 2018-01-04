---
title: "방법: 캐시된 요소를 브러시로 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f463c15855e267a4c246625a8d06e627852f48a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a>방법: 캐시된 요소를 브러시로 사용
사용 하 여는 <xref:System.Windows.Media.BitmapCacheBrush> 클래스를 효율적으로 캐시 된 요소를 다시 사용 합니다. 새 인스턴스를 만들고 요소를 캐시 하려면는 <xref:System.Windows.Media.BitmapCache> 클래스 및 요소에 할당할 <xref:System.Windows.UIElement.CacheMode%2A> 속성입니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 캐시 된 요소를 다시 사용 하는 방법을 보여 줍니다. 캐시 된 요소는 한 <xref:System.Windows.Controls.Image> 큰 이미지를 표시 하는 컨트롤입니다. <xref:System.Windows.Controls.Image> 컨트롤이 사용 하 여 비트맵으로 캐시 되는 <xref:System.Windows.Media.BitmapCache> 클래스 및 캐시에 할당 하 여 다시 사용 되는 <xref:System.Windows.Media.BitmapCacheBrush>합니다. 효율적인 다시 사용할 수 있도록 표시 하려면 25 단추의 배경 브러시 할당 됩니다.  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [방법: 요소를 캐시하여 렌더링 성능 향상](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)
