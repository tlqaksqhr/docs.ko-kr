---
title: "방법: 스타일에 애니메이션 효과 적용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10cd243c633e7a7e458d2026fc5e3d91d2996427
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-in-a-style"></a>방법: 스타일에 애니메이션 효과 적용
이 예에서는 스타일 내에서 속성에 애니메이션을 적용 하는 방법을 보여 줍니다. 애니메이션 스타일 적용을 스타일이 정의 된 프레임 워크 요소만 직접 지정할 수 있습니다. Freezable 개체를 대상으로 하면 해야 "dot 다운" 스타일의 요소 속성에서 합니다.  
  
 다음 예제에서는 여러 개의 애니메이션 스타일 내에서 정의 되 고에 적용 한 <xref:System.Windows.Controls.Button>합니다. 부분적으로 반투명 / 뒤에 불투명에서 사라지기 단추 위로 마우스를 이동할 때 다시, 반복적으로 합니다. 단추 밖으로 마우스를 이동할 때 완전히 불투명 하 게 됩니다. 단추를 클릭할 때 배경색을 흰색 다시 주황색에서 변경 합니다. 때문에 <xref:System.Windows.Media.SolidColorBrush> 그리는 데 사용 되는 단추를 직접 대상이 될 수 없습니다, 단추의에서 아래로 것으로 액세스 하는 것 <xref:System.Windows.Controls.Control.Background%2A> 속성입니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 Note 스타일 내에서 애니메이션을 적용할 때는 수 있다는 것에 존재 하지 않는 대상 개체입니다. 예를 들어, 다음을 사용 하 여 스타일은 <xref:System.Windows.Media.SolidColorBrush> 이 단추의 배경 속성을 설정 하지만 특정 지점 스타일을 재정의 하 고 단추의 배경을으로 설정 된 한 <xref:System.Windows.Media.LinearGradientBrush>합니다.  애니메이션 효과 적용 하는 <xref:System.Windows.Media.SolidColorBrush> ; 예외가 발생 하지 애니메이션만 자동으로 실패 합니다.  
  
 스토리 보드 대상 지정 구문에 대 한 자세한 내용은 참조는 [적기](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다. 애니메이션에 대 한 자세한 내용은 참조는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)합니다. 스타일에 대 한 자세한 내용은 참조는 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)합니다.
