---
title: "WPF 3D 성능 최대화 | Microsoft Docs"
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
  - "3차원 그래픽[WPF]"
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# WPF 3D 성능 최대화
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]를 사용하여 3D 컨트롤을 빌드하고 3D 장면을 응용 프로그램에 포함할 때는 성능 최적화를 고려하는 것이 중요합니다. 이 항목에서는 응용 프로그램의 성능에 영향을 주는 3D 클래스 및 속성의 목록을 제공하고 이러한 항목을 사용할 때 성능을 최적화하는 방법을 보여 줍니다.  
  
 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D 기능에 대한 고급 지식을 갖추고 있다고 가정합니다.  이 문서에 있는 제안 사항은 "렌더링 계층 2"에 적용됩니다. 렌더링 계층 2를 간단하게 정의하자면 픽셀 셰이더 버전 2.0 및 꼭짓점 셰이더 버전 2.0을 지원하는 하드웨어입니다.  자세한 내용은 [그래픽 렌더링 계층](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)을 참조하십시오.  
  
## 성능 영향: 높음  
  
|||  
|-|-|  
|Property|권장 사항|  
|<xref:System.Windows.Media.Brush>|브러시 속도\(가장 빠름에서 가장 느림으로\):<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>\(캐시됨\)<br /><br /> <xref:System.Windows.Media.VisualBrush>\(캐시됨\)<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>\(캐시되지 않음\)<br /><br /> <xref:System.Windows.Media.VisualBrush>\(캐시되지 않음\)|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 <xref:System.Windows.Controls.Viewport3D>의 내용을 Viewport3D의 직사각형에 맞게 명시적으로 자를 필요가 없으면 항상 `Viewport3D.ClipToBounds`를 false로 설정하십시오. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 앤티 앨리어싱된 자르기는 속도가 매우 느릴 수 있으며, `ClipToBounds`는 <xref:System.Windows.Controls.Viewport3D>에서 기본적으로 사용할 수 있도록 설정되므로 속도가 느려집니다.|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 마우스 적중 테스트를 수행할 때 <xref:System.Windows.Controls.Viewport3D>의 콘텐츠를 고려할 필요가 없으면 항상 `Viewport3D.IsHitTestVisible`을 false로 설정하십시오. 3D 콘텐츠의 적중 테스트는 소프트웨어를 통해 수행되며 망상 조직이 큰 경우 속도가 느려질 수 있습니다. <xref:System.Windows.UIElement.IsHitTestVisible%2A>은 <xref:System.Windows.Controls.Viewport3D>에서 기본적으로 활성화되므로 속도가 느립니다.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|다른 재질 또는 변환이 필요한 경우에만 다른 모델을 만드십시오.  또는 재질 및 변환이 같은 여러 개의 <xref:System.Windows.Media.Media3D.GeometryModel3D> 인스턴스를 소수의 큰 <xref:System.Windows.Media.Media3D.GeometryModel3D> 및 <xref:System.Windows.Media.Media3D.MeshGeometry3D> 인스턴스로 결합하십시오.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|프레임별로 망상 조직의 개별 꼭짓점을 변경하는 망상 조직 애니메이션이 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 항상 효율적인 것은 아닙니다. 각 꼭짓점이 수정될 때 변경 알림이 성능에 주는 영향을 최소화하려면 꼭짓점별 수정을 수행하기 전에 시각적 트리에서 망상 조직을 분리하고 망상 조직을 수정한 후에 시각적 트리에 다시 연결합니다. 또한 이 방법으로 애니메이션이 적용될 망상 조직의 크기를 최소화하십시오.|  
|3D Antialiasing|렌더링 속도를 높이려면 연결된 속성 <xref:System.Windows.Media.RenderOptions.EdgeMode%2A>를 `Aliased`로 설정하여 <xref:System.Windows.Controls.Viewport3D>에서 다중 샘플링을 사용하지 않도록 하십시오.  기본적으로 3D 앤티 앨리어싱은 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]에서는 사용되지 않고 [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)]에서는 픽셀당 4개의 샘플로 사용됩니다.|  
|Text|3D 장면의 라이브 텍스트\(<xref:System.Windows.Media.DrawingBrush> 또는 <xref:System.Windows.Media.VisualBrush>에 있는 텍스트\)가 느릴 수 있습니다.  텍스트가 변경될 때까지 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>을 통해 텍스트의 이미지를 대신 사용해 보십시오.|  
|<xref:System.Windows.Media.TileBrush>|브러시의 내용이 정적이 아니어서 3D 장면에 <xref:System.Windows.Media.VisualBrush> 또는 <xref:System.Windows.Media.DrawingBrush>를 사용해야 하는 경우 브러시를 캐시해 보십시오\(연결된 속성 <xref:System.Windows.Media.RenderOptions.CachingHint%2A>를 `Cache`로 설정\).  연결된 속성 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> 및 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>을 통해 최소 및 최대 범위 무효화 임계값을 설정하여 원하는 수준의 품질의 유지하면서도 캐시된 브러시가 너무 자주 다시 생성되지 않도록 하십시오.  기본적으로 <xref:System.Windows.Media.DrawingBrush> 및 <xref:System.Windows.Media.VisualBrush>는 캐시되지 않습니다. 즉, 브러시로 칠하는 내용을 다시 렌더링해야 할 때마다 브러시의 전체 내용을 중간 표면에 먼저 다시 렌더링해야 합니다.|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect>는 영향을 받는 모든 내용이 하드웨어 가속 없이 렌더링되도록 합니다.  최상의 성능을 위해 <xref:System.Windows.Media.Effects.BitmapEffect>를 사용하지 마십시오.|  
  
## 성능 영향: 보통  
  
|||  
|-|-|  
|Property|권장 사항|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|망상 조직이 꼭짓점을 공유하는 인접 삼각형으로 정의되어 있고 해당 꼭짓점의 위치 좌표, 일반 좌표 및 질감 좌표가 동일한 경우에는 각 공유 꼭짓점을 한 번만 정의하고 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>를 사용하여 삼각형으로 인덱스별로 정의하십시오.|  
|<xref:System.Windows.Media.ImageBrush>|크기를 명시적으로 제어할 수 있을 때\(<xref:System.Windows.Media.Imaging.RenderTargetBitmap> 및\/또는 <xref:System.Windows.Media.ImageBrush>를 사용할 때\) 질감 크기를 최소화하십시오.  해상도 질감이 낮으면 시각적 품질이 저하될 수 있으므로 품질과 성능 간에 올바른 균형을 유지하십시오.|  
|Opacity|리플렉션과 같은 반투명 3D 콘텐츠를 렌더링할 때는 `Viewport3D.Opacity`를 1보다 낮은 값으로 설정하여 별도의 반투명 <xref:System.Windows.Controls.Viewport3D>를 만드는 대신 <xref:System.Windows.Media.Brush.Opacity%2A> 또는 <xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>를 통해 브러시나 재질에 불투명 속성을 사용하십시오.|  
|<xref:System.Windows.Controls.Viewport3D>|장면에서 사용하는 <xref:System.Windows.Controls.Viewport3D> 개체의 수를 최소화하십시오.  각 모델에 대한 별도의 Viewport3D 인스턴스를 만드는 대신 같은 Viewport3D에 여러 3D 모델을 넣으십시오.|  
|<xref:System.Windows.Freezable>|일반적으로 <xref:System.Windows.Media.Media3D.MeshGeometry3D>, <xref:System.Windows.Media.Media3D.GeometryModel3D>, 브러시 및 재질을 다시 사용하는 것이 좋습니다.  모두 `Freezable`에서 파생되었기 때문에 복수의 부모 항목이 있을 수 있습니다.|  
|<xref:System.Windows.Freezable>|응용 프로그램에서 속성이 변경되지 않을 경우에는 Freezable에서 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 호출하십시오.  고정으로 인해 작업 집합이 줄어들고 속도가 향상될 수 있습니다.|  
|<xref:System.Windows.Media.Brush>|브러시의 내용이 변경되지 않을 때는 <xref:System.Windows.Media.VisualBrush> 또는 <xref:System.Windows.Media.DrawingBrush> 대신 <xref:System.Windows.Media.ImageBrush>를 사용하십시오.  2D 콘텐츠는 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>을 통해 <xref:System.Windows.Controls.Image>로 변환된 다음 <xref:System.Windows.Media.ImageBrush>에서 사용될 수 있습니다.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|<xref:System.Windows.Media.Media3D.GeometryModel3D>의 뒷면을 꼭 봐야 할 경우를 제외하고는 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>을 사용하지 마십시오.|  
|<xref:System.Windows.Media.Media3D.Light>|조명 속도\(가장 빠름에서 가장 느림으로\):<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|망상 조직 크기를 다음 제한 아래로 유지하십시오.<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>: 20,001 <xref:System.Windows.Media.Media3D.Point3D> 인스턴스<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>: 60,003 <xref:System.Int32> 인스턴스|  
|<xref:System.Windows.Media.Media3D.Material>|재질 속도\(가장 빠름에서 가장 느림으로\):<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D에서는 보이지 않는 브러시\(검정 앰비언트 브러시, 지우기 브러시 등\)를 일관성 있게 생략하지 않습니다. 장면에서 이러한 항목을 제거하는 것이 좋습니다.|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|<xref:System.Windows.Media.Media3D.MaterialGroup>에 있는 각 <xref:System.Windows.Media.Media3D.Material>로 인해 다른 렌더링 패스가 발생하므로 대부분의 재질을 비롯하여 아주 간단한 재질이라도 GPU의 채우기 수요를 크게 높일 수 있습니다.  <xref:System.Windows.Media.Media3D.MaterialGroup>에서 재질 수를 최소화하십시오.|  
  
## 성능 영향: 낮음  
  
|||  
|-|-|  
|Property|권장 사항|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|애니메이션이나 데이터 바인딩이 필요하지 않은 경우에는 다수의 변환을 포함하는 변환 그룹을 사용하는 대신 단일 <xref:System.Windows.Media.Media3D.MatrixTransform3D>를 사용하십시오. 이 항목을 사용하지 않을 경우 변환 그룹에 독립적으로 존재할 모든 변환의 합이 되도록 이 항목을 설정하면 됩니다.|  
|<xref:System.Windows.Media.Media3D.Light>|장면에서 조명 수를 최소화하십시오.  장면에 조명이 너무 많으면 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 소프트웨어 렌더링을 대신 사용합니다. 상한은 약 110개의 <xref:System.Windows.Media.Media3D.DirectionalLight> 개체, 70개의 <xref:System.Windows.Media.Media3D.PointLight> 개체 또는 40개의 <xref:System.Windows.Media.Media3D.SpotLight> 개체입니다.|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|정적 개체로부터 이동하는 개체를 별도의 <xref:System.Windows.Media.Media3D.ModelVisual3D> 인스턴스에 넣어 분리하십시오.  ModelVisual3D는 변환된 경계를 캐시하기 때문에 <xref:System.Windows.Media.Media3D.GeometryModel3D>보다 "무겁습니다".  GeometryModel3D는 모델에 최적화되어 있고, ModelVisual3D는 장면 노드에 최적화되어 있습니다.  ModelVisual3D를 사용하여 GeometryModel3D의 공유 인스턴스를 장면에 넣으십시오.|  
|<xref:System.Windows.Media.Media3D.Light>|장면에서 조명의 수를 변경하는 횟수를 최소화하십시오.  해당 구성이 이미 존재하여 셰이더가 이미 캐시된 경우를 제외하고는 조명이 변경될 때마다 셰이더가 다시 생성되고 컴파일됩니다.|  
|Light|검은색 조명은 눈에 보이지 않지만 렌더링 시간을 늘립니다. 따라서 사용하지 않는 것이 좋습니다.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|MeshGeometry3D의 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> 및 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 같은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 큰 컬렉션의 생성 시간을 최소화하려면 값을 입력하기 전에 컬렉션의 크기를 미리 조정하십시오.  가능하면 배열 또는 Lists와 같이 컬렉션의 생성자가 미리 입력된 데이터 구조를 전달하십시오.|  
  
## 참고 항목  
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)