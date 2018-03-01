---
title: "WPF 3D 성능 최대화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 3-D graphics [WPF]
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 45053762a4782544531a09c92531b26f99663016
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="maximize-wpf-3d-performance"></a>WPF 3D 성능 최대화
사용 하는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D 컨트롤을 빌드하고 3D 장면을 응용 프로그램에 포함할 성능 최적화를 고려을 고려해 야 합니다. 이 항목에서는 3D 클래스 및 속성을 사용할 때 성능을 최적화 하기 위한 권장 사항과 함께 응용 프로그램에 대 한 성능 영향을 주는의 목록을 제공 합니다.  
  
 이 항목에서는 고급 이해 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D 기능입니다. 이 문서에서 제안 "렌더링 계층 2"에 적용할-대략 픽셀 셰이더 버전 2.0 및 꼭 짓 점 셰이더 버전 2.0 지 원하는 하드웨어에으로 정의 합니다. 자세한 내용은 참조 하십시오. [그래픽 렌더링 계층](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)합니다.  
  
## <a name="performance-impact-high"></a>성능에 미치는 영향: 높음  
  
|속성|권장 사항|  
|-|-|  
|<xref:System.Windows.Media.Brush>|브러시 속도 (가장 느린으로):<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>(캐시 됨)<br /><br /> <xref:System.Windows.Media.VisualBrush>(캐시 됨)<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>(캐시 되지 않음)<br /><br /> <xref:System.Windows.Media.VisualBrush>(캐시 되지 않음)|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|설정 `Viewport3D.ClipToBounds` false가 필요할 때마다로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 명시적으로 콘텐츠를 잘라는 <xref:System.Windows.Controls.Viewport3D> Viewport3D의 사각형에 있습니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]앤티 앨리어싱된 클리핑 매우 느려질 수 있습니다 및 `ClipToBounds` 에서 기본적으로 속도가 느립니다 사용 <xref:System.Windows.Controls.Viewport3D>합니다.|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|설정 `Viewport3D.IsHitTestVisible` 불필요 때마다 false로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 의 콘텐츠를 고려 하는 <xref:System.Windows.Controls.Viewport3D> 수행 마우스 적중 테스트 하는 경우.  3D 콘텐츠의 적중된 테스트는 소프트웨어에서 수행 되 고 큰 메시 속도가 느려질 수 있습니다. <xref:System.Windows.UIElement.IsHitTestVisible%2A>기본적으로 속도가 느립니다 사용 <xref:System.Windows.Controls.Viewport3D>합니다.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|다른 재질 또는 변환이 필요한 경우에 다른 모델을 만듭니다.  그렇지 않은 경우 많은 결합 하십시오 <xref:System.Windows.Media.Media3D.GeometryModel3D> 를 소수의 큰 재질 및 변환이 같은 사용 하 여 인스턴스 <xref:System.Windows.Media.Media3D.GeometryModel3D> 및 <xref:System.Windows.Media.Media3D.MeshGeometry3D> 인스턴스.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|애니메이션 메시-당 프레임으로 메시의 개별 꼭지점 변경-은 항상 효율적 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]합니다.  파일을 각 꼭 짓 점 수정 될 때 변경 알림의 성능 영향을 최소화 하려면 시각적 트리에서 메시 꼭 짓 점별 수정을 수행 하기 전에 분리 합니다.  메시를 수정한 후 시각적 트리를 다시 연결 합니다.  또한 이러한 방식으로 애니메이션 메시의 크기를 최소화 하려고 합니다.|  
|3D 앤티 앨리어싱|렌더링 속도를 높이려면 샘플링에 사용 하지 않도록는 <xref:System.Windows.Controls.Viewport3D> 연결 된 속성을 설정 하 여 <xref:System.Windows.Media.RenderOptions.EdgeMode%2A> 를 `Aliased`합니다.  기본적으로 3D 앤티 앨리어싱 사용 되지 않는지에 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] 사용 [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)] 픽셀 당 4 샘플이 있습니다.|  
|텍스트|3D 장면에 텍스트를 라이브 (에 있기 때문에 라이브는 <xref:System.Windows.Media.DrawingBrush> 또는 <xref:System.Windows.Media.VisualBrush>) 느려질 수 있습니다. 텍스트의 이미지를 대신 사용 (통해 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>) 텍스트는 변경 하지 않는 한 합니다.|  
|<xref:System.Windows.Media.TileBrush>|사용 해야 하는 경우는 <xref:System.Windows.Media.VisualBrush> 또는 <xref:System.Windows.Media.DrawingBrush> 3D 장면에 브러시의 내용을 정적 이기 때문에 캐시 해 보십시오 브러시 (연결 된 속성 <xref:System.Windows.Media.RenderOptions.CachingHint%2A> 를 `Cache`).  최소 및 최대 눈금 무효화 임계값을 설정 (연결 된 속성과 함께 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> 및 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>) 캐시 된 브러시 다시 생성 됩니다 너무 자주 원하는 품질 수준을 그대로 유지 하면서 되도록 합니다.  기본적으로 <xref:System.Windows.Media.DrawingBrush> 및 <xref:System.Windows.Media.VisualBrush> , 캐시 되지 않습니다는 될 때마다 다시 렌더링 되어야 하는 브러시와 그린 것 브러시의 전체 내용이 먼저 다시 렌더링 해야 중간 화면으로 의미 합니다.|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect>하드웨어 가속 없이 렌더링 해야 하는 모든 영향을 받는 콘텐츠를 강제로 수행 합니다.  최상의 성능을 위해 사용 하지 마십시오 <xref:System.Windows.Media.Effects.BitmapEffect>합니다.|  
  
## <a name="performance-impact-medium"></a>성능에 미치는 영향: 보통  
  
|속성|권장 사항|  
|-|-|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|메시 꼭 짓 점을 공유 삼각형 인접으로 정의 되어 있고 해당 꼭 짓와 동일한 위치, normal, 질감 좌표, 하는 경우 각 공유 꼭 짓 점을 한 번만 정의 하며 다음이 있는 인덱스 여 삼각형을 정의 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>합니다.|  
|<xref:System.Windows.Media.ImageBrush>|크기를 명시적으로 제어할 있는 경우 질감 크기를 최소화 하려고 (사용 하는 경우는 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 및/또는 <xref:System.Windows.Media.ImageBrush>).  더 낮은 해상도 질감 시각적 품질이 저하, 품질 및 성능 사이의 올바른 균형을 찾으려고 시도 하므로 수 note 합니다.|  
|불투명도|(예: 반사) 콘텐츠 반투명 3D를 렌더링할 때 브러시 하거나 정보나 자료의 불투명도 속성을 사용 (통해 <xref:System.Windows.Media.Brush.Opacity%2A> 또는 <xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>) 별도 반투명 만드는 대신 <xref:System.Windows.Controls.Viewport3D> 설정 하 여 `Viewport3D.Opacity` 1 보다 작은 값입니다.|  
|<xref:System.Windows.Controls.Viewport3D>|수를 최소화 <xref:System.Windows.Controls.Viewport3D> 장면에서 사용 하는 개체입니다.  각 모델에 대 한 별도 Viewport3D 인스턴스를 만드는 것이 아니라 동일한 Viewport3D 많은 3D 모델을 넣습니다.|  
|<xref:System.Windows.Freezable>|일반적으로 것이 다시 사용 하려면 <xref:System.Windows.Media.Media3D.MeshGeometry3D>, <xref:System.Windows.Media.Media3D.GeometryModel3D>, 브러시 및 자료.  파생 되었기 때문 multiparentable 모두 `Freezable`합니다.|  
|<xref:System.Windows.Freezable>|호출 된 <xref:System.Windows.Freezable.Freeze%2A> 응용 프로그램에서 변경 되지 않은 메서드를 Freezable 때 해당 속성이 유지 됩니다.  고정 감소 작업 집합 및 속도 높일 수 있습니다.|  
|<xref:System.Windows.Media.Brush>|사용 하 여 <xref:System.Windows.Media.ImageBrush> 대신 <xref:System.Windows.Media.VisualBrush> 또는 <xref:System.Windows.Media.DrawingBrush> 브러시의 내용이 변경 되지 것입니다.  2D 콘텐츠를 변환할 수는 <xref:System.Windows.Controls.Image> 통해 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 한 다음에 사용 된 <xref:System.Windows.Media.ImageBrush>합니다.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|사용 하지 않는 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> 의 뒷면에 실제로 필요한 경우가 아니면 프로그램 <xref:System.Windows.Media.Media3D.GeometryModel3D>합니다.|  
|<xref:System.Windows.Media.Media3D.Light>|밝은 속도 (가장 느린으로):<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|이러한 제한에서 메시 크기를 유지 하려고 합니다.<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>: 20001 <xref:System.Windows.Media.Media3D.Point3D> 인스턴스<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>: 60003 <xref:System.Int32> 인스턴스|  
|<xref:System.Windows.Media.Media3D.Material>|자재 속도 (가장 느린으로):<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]3D 일관 된 방식에서 (검정 앰비언트 브러시, 지우기 브러시, 등) 보이지 않는 브러시를 취소 하지 않습니다.  장면에서 이러한 항목을 제거 하는 것이 좋습니다.|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|각 <xref:System.Windows.Media.Media3D.Material> 에 <xref:System.Windows.Media.Media3D.MaterialGroup> 하므로 대부분의 재질을 비롯 한 다른 렌더링 전달, 간단한 재질에도, GPU에 대 한 채우기 요구를 크게 높일 수 있습니다.  자료의 수를 최소화 하면 <xref:System.Windows.Media.Media3D.MaterialGroup>합니다.|  
  
## <a name="performance-impact-low"></a>성능에 미치는 영향: 낮음  
  
|속성|권장 사항|  
|-|-|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|애니메이션 않아도 또는 데이터 바인딩, 여러 변환을 포함 하는 변환 그룹을 사용 하는 대신 사용 하 여 단일 경우 <xref:System.Windows.Media.Media3D.MatrixTransform3D>는 그렇지 않은 경우는 독립적으로 존재 변환 그룹에 모든 변환의 제품 수를 설정 합니다.|  
|<xref:System.Windows.Media.Media3D.Light>|장면에서 조명의 수를 최소화 합니다. 장면에 너무 많은 표시등을 강제로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 소프트웨어 렌더링으로 대체 합니다.  한도 대략 110 <xref:System.Windows.Media.Media3D.DirectionalLight> 개체, 70 <xref:System.Windows.Media.Media3D.PointLight> 개체나 40 <xref:System.Windows.Media.Media3D.SpotLight> 개체입니다.|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|별도의 관리 하 여 정적 개체에서 개체를 이동 하는 별도 <xref:System.Windows.Media.Media3D.ModelVisual3D> 인스턴스.  ModelVisual3D은 보다 "과도" <xref:System.Windows.Media.Media3D.GeometryModel3D> 변형 된 범위를 캐시 하기 때문입니다.  GeometryModel3D, 모델 최적화 ModelVisual3D 장면 노드가으로 최적화 됩니다.  ModelVisual3D 장면 GeometryModel3D의 공유 인스턴스를 사용 합니다.|  
|<xref:System.Windows.Media.Media3D.Light>|장면의 광원의 수를 변경 하는 횟수를 최소화 합니다.  밝은 수가 변경 될 때마다 해당 구성이 이미 존재 합니다 (및 해당 셰이더 캐시에 따라서) 하지 않는 한 셰이더 재생성 하 고 다시 컴파일할 되도록 합니다.|  
|밝게|블랙 lights 표시 없지만 렌더링; 시간을 추가 합니다. 사용 하지 않는 것이 좋습니다.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|큰 컬렉션의 생성 시간을 최소화 하려면 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], MeshGeometry3D의 같은 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>, 및 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>, 미리 값 채우기 전에 컬렉션 크기를 조정 합니다. 가능 하면 배열 또는 목록 같은 컬렉션의 생성자 미리 입력 된 데이터 구조를 전달 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
