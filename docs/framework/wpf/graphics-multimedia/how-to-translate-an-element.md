---
title: "방법: 요소 변환"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2f9b8363f0c3b9e0a9653dfc9864727c9460f695
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-translate-an-element"></a>방법: 요소 변환
이 예제에서는 변환 (이동) 하는 요소를 사용 하 여는 <xref:System.Windows.Media.TranslateTransform>합니다.  
  
 <xref:System.Windows.Media.TranslateTransform> 클래스 절대 위치 지정을 지원 하지 않는 패널 내에서 요소를 이동 하는 데 특히 유용 합니다. 예를 들어 적용 하 여는 <xref:System.Windows.Media.TranslateTransform> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 요소의 속성 내에서 요소를 이동할 수 있습니다는 <xref:System.Windows.Controls.StackPanel> 또는 <xref:System.Windows.Controls.DockPanel>합니다.  
  
 사용 하 여는 <xref:System.Windows.Media.TranslateTransform.X%2A> 의 속성은 <xref:System.Windows.Media.TranslateTransform> 픽셀 x 축 따라 요소를 이동 하려면 시간을 지정 하려면. 사용 하 여는 <xref:System.Windows.Media.TranslateTransform.Y%2A> 속성을 시도 하는 양 y 축 따라 요소를 이동 하려면를 픽셀 단위로 지정 합니다. 마지막으로 적용 된 <xref:System.Windows.Media.TranslateTransform> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 요소의 속성입니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Media.TranslateTransform> 요소 50 픽셀을 오른쪽 테이블과 50 픽셀 아래로 이동 하려면.  
  
## <a name="example"></a>예  
 [!code-xaml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 전체 샘플을 보려면 [2차원 변환 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
