---
title: "방법: 현재 위치에서 요소가 회전하도록 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae76d33a30853107cbecf0749230aefce77a866d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-an-element-spin-in-place"></a>방법: 현재 위치에서 요소가 회전하도록 만들기
요소를 사용 하 여 회전 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.RotateTransform> 및 <xref:System.Windows.Media.Animation.DoubleAnimation>합니다.  
  
 다음 예제에서는 적용는 <xref:System.Windows.Media.RotateTransform> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 요소의 속성입니다. 이 예제에서는 사용는 <xref:System.Windows.Media.Animation.DoubleAnimation> 애니메이션 효과를 줄의 <xref:System.Windows.Media.RotateTransform.Angle%2A> 의 <xref:System.Windows.Media.RotateTransform>합니다. 이 예제에서는 요소를 현재 위치에서 회전을 하려면 설정는 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 점 (0.5, 0.5)는 요소의 속성입니다.  
  
## <a name="example"></a>예  
 [!code-xaml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 더 많은 변환 예제를 포함 하는 전체 샘플을 참조 하십시오. [2 차원 변환은 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
