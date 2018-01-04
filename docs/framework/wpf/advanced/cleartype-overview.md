---
title: "ClearType 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], ClearType technology
- ClearType [WPF], technology
ms.assetid: 7e2392e0-75dc-463d-a716-908772782431
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eaeeeee921ac5cda3a4ce09dd3ebaeeb11aea3f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cleartype-overview"></a>ClearType 개요
이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에 있는 [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] 기술에 대해 간략하게 설명합니다.  
  
  
<a name="overview"></a>   
## <a name="technology-overview"></a>기술 개요  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]은 랩톱 화면, Pocket PC 화면, 평면 모니터 등 기존의 LCD(액정 디스플레이)에서 보다 쉽게 텍스트를 읽을 수 있도록 하기 위해 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]에서 개발한 소프트웨어 기술입니다.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]은 LCD 화면의 모든 픽셀에 있는 개별 세로 색 스트라이프 요소에 액세스하는 방식으로 작동합니다. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 이전에는 컴퓨터에서 표시할 수 있는 가장 작은 단위는 픽셀이었지만, LCD 모니터에서 실행되는 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]을 사용하면 픽셀(너비 단위)의 분수 값만큼 작은 텍스트의 특징까지 표시할 수 있습니다. 해상도를 더 세밀하게 지원할수록 텍스트의 미세한 부분까지 더 선명하게 표시되므로 오랫동안 더 쉽게 읽을 수 있습니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 제공되는 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]은 [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)]에 있는 버전에 걸쳐 몇 차례 향상된 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]의 최신 버전입니다.  
  
<a name="sub-pixel_positioning"></a>   
## <a name="sub-pixel-positioning"></a>하위 픽셀 위치 지정  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]의 이전 버전에 비해 크게 향상된 점은 하위 픽셀 위치 지정을 사용한다는 것입니다. [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)]에 있는 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 구현과 달리 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에 있는 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]에서는 문자 모양이 픽셀의 시작 경계에서만 시작할 수 있는 것이 아니라 픽셀 안에서도 시작할 수 있습니다. 문자 모양의 위치 지정에 적용되는 이처럼 세밀한 추가 해상도로 인해 문자 모양의 간격과 비율이 더욱 정확하고 일관성 있게 유지됩니다.  
  
 다음 두 예에서는 하위 픽셀 위치 지정을 사용할 때 문자 모양이 모든 하위 픽셀 경계에서 시작할 수 있는 방법을 보여 줍니다. 왼쪽의 예는 하위 픽셀 위치 지정을 지원하지 않는 이전 버전의 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 렌더러를 사용하여 렌더링됩니다. 오른쪽의 예는 하위 픽셀 위치 지정을 지원하는 새 버전의 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 렌더러를 사용하여 렌더링됩니다. 오른쪽 이미지의 **e**와 **l**은 각각 서로 다른 하위 픽셀에서 시작하기 때문에 약간 다르게 렌더링됩니다. 화면에서 텍스트를 정상 크기로 볼 때는 문자 모양 이미지의 고대비로 인해 이 차이가 눈에 띄지 않습니다. 이는 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]에 통합된 정교한 색 필터링 때문에 가능합니다.  
  
 ![ClearType의 두 가지 버전으로 표시 된 텍스트](../../../../docs/framework/wpf/advanced/media/wcpsdk-mmgraphics-text-cleartype-overview-01.png "wcpsdk_mmgraphics_text_cleartype_overview_01")  
이전 버전 및 최신 버전의 ClearType으로 표시된 텍스트  
  
 다음 두 예에서는 이전 버전의 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 렌더러와 새 버전의 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 렌더러에서 만든 출력을 비교합니다. 오른쪽의 하위 픽셀 위치 지정은 화면의 글자 간격 조정을 크게 향상시키며, 특히 하위 픽셀과 전체 픽셀 사이의 차이가 문자 모양 너비의 많은 부분을 차지하는 작은 크기의 경우에는 더욱 그렇습니다. 두 번째 이미지에서는 글자 사이의 간격 조정이 더 균일합니다. 텍스트 화면의 전체적인 모양에서 하위 픽셀 위치 지정에 따른 이점이 크게 증가하여 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 기술의 중요한 발전을 보여 줍니다.  
  
 ![ClearType의 이전 버전으로 표시 된 텍스트](../../../../docs/framework/wpf/advanced/media/wcpsdk-mmgraphics-text-cleartype-overview-02.png "wcpsdk_mmgraphics_text_cleartype_overview_02")  
이전 버전 및 이후 버전의 ClearType을 통한 텍스트  
  
<a name="y-direction_antialiasing"></a>   
## <a name="y-direction-antialiasing"></a>y 방향 앤티 앨리어싱  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]의 또 다른 향상된 기능은 y 방향 앤티 앨리어싱입니다. y 방향 앤티 앨리어싱이 지원되지 않는 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)]의 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]은 x 축에서 더 좋은 해상도를 제공하지만 y 축에서는 그렇지 않습니다. 얇은 곡선의 위쪽과 아래쪽에서 들쭉날쭉한 가장자리는 가독성을 떨어뜨립니다.  
  
 다음 예는 y 방향 앤티 앨리어싱을 사용하지 않는 경우의 효과를 보여 줍니다. 이 경우 글자의 위쪽과 아래쪽의 들쭉날쭉한 가장자리가 분명하게 눈에 띕니다.  
  
 ![부분 곡선에서 가장자리가 울퉁불퉁한 텍스트](../../../../docs/framework/wpf/advanced/media/wcpsdk-mmgraphics-text-cleartype-overview-03.png "wcpsdk_mmgraphics_text_cleartype_overview_03")  
얇은 곡선의 가장자리가 들쭉날쭉한 텍스트  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]은 y 방향 수준에서 앤티 앨리어싱을 제공하여 들쭉날쭉한 가장자리를 매끄럽게 합니다. 이는 얇은 곡선의 가로와 세로 양이 거의 같은 표의 문자를 사용하는 동아시아 언어의 가독성을 향상시키는 데 특히 중요합니다.  
  
 다음 예는 y 방향 앤티 앨리어싱을 사용하는 경우의 효과를 보여 줍니다. 이 경우 글자의 위쪽과 아래쪽이 매끄러운 곡선을 나타냅니다.  
  
 ![ClearType y #45; anti 방향 &#45;텍스트 이거나, 이러한 앨리어싱](../../../../docs/framework/wpf/advanced/media/wcpsdk-mmgraphics-text-cleartype-overview-04.png "wcpsdk_mmgraphics_text_cleartype_overview_04")  
ClearType y 방향 앤티앨리어싱으로 표시된 텍스트  
  
<a name="hardware_acceleration"></a>   
## <a name="hardware-acceleration"></a>하드웨어 가속  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]은 하드웨어 가속의 이점을 활용하여 성능을 더 높이고 CPU 부하와 시스템 메모리 요구 사항을 줄일 수 있습니다. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]는 그래픽 카드의 픽셀 셰이더와 비디오 메모리를 사용하여 특히 애니메이션을 사용할 때 텍스트의 렌더링 속도를 높입니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]은 시스템 전체 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 설정을 수정하지 않습니다. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]에서 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]을 사용하지 않도록 설정하면 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 앤티 앨리어싱이 회색조 모드로 설정됩니다. 또한 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]은 [ClearType Tuner PowerToy](http://www.microsoft.com/typography/ClearTypePowerToy.mspx)의 설정을 수정하지 않습니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 아키텍처 디자인과 관련된 결정 중 하나는 더 광범위하게 보급되고 있는 고해상도 DPI 모니터를 더 효과적으로 지원하기 위해 해상도의 영향을 받지 않는 레이아웃이 있어야 한다는 것입니다. 이에 따라 일부 동아시아 글꼴의 앨리어싱된 텍스트 렌더링과 비트맵이 모두 해상도의 영향을 받기 때문에 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 이러한 렌더링과 비트맵을 지원하지 않습니다.  
  
<a name="further_information"></a>   
## <a name="further-information"></a>추가 정보  
 [ClearType 정보](http://www.microsoft.com/typography/ClearTypeInfo.mspx)  
  
 [ClearType Tuner PowerToy](http://www.microsoft.com/typography/ClearTypePowerToy.mspx)  
  
## <a name="see-also"></a>참고 항목  
 [ClearType 레지스트리 설정](../../../../docs/framework/wpf/advanced/cleartype-registry-settings.md)
