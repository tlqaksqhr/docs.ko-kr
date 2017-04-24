---
title: "3차원 그래픽 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "3차원 그래픽"
  - "그래픽[WPF], 3차원"
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 3차원 그래픽 개요
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 기능을 사용하여 개발자는 태그 및 프로시저 코드 모두를 통해 3차원 그래픽을 그리고 변환하며 이러한 그래픽에 애니메이션 효과를 줄 수 있습니다.  개발자는 [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] 및 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 그래픽을 결합하여 다양한 컨트롤을 만들거나, 복잡한 데이터 표시를 제공하거나, 응용 프로그램 인터페이스의 사용자 경험을 개선할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 지원은 모든 기능을 갖춘 게임 개발 플랫폼을 제공하기 위한 것은 아닙니다. 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 시스템의 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 기능에 대해 간략하게 설명합니다.  
  
   
  
<a name="threed_in_2d"></a>   
## 2차원 컨테이너의 3차원  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 그래픽 콘텐츠는 2차원 요소 구조에 참여할 수 있는 요소인 <xref:System.Windows.Controls.Viewport3D>에 캡슐화됩니다.  그래픽 시스템에서는 <xref:System.Windows.Controls.Viewport3D>를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 다른 많은 요소처럼 2차원 시각적 요소로 처리합니다.  <xref:System.Windows.Controls.Viewport3D>는 3차원 장면을 보여 주는 창\(뷰포트\)으로 작동합니다.  보다 정확히 말해 이는 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면이 나타나는 표면입니다.  
  
 기존 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 응용 프로그램에서는 표나 캔버스와 같은 다른 컨테이너 요소를 사용하듯이 <xref:System.Windows.Controls.Viewport3D>를 사용합니다.  <xref:System.Windows.Controls.Viewport3D>와 다른 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 그리기 개체를 같은 장면 그래프에서 사용할 수 있지만 <xref:System.Windows.Controls.Viewport3D> 내에서 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 및 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 개체를 상호 침투할 수는 없습니다.  이 항목에서는 <xref:System.Windows.Controls.Viewport3D> 내에서 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 그래픽을 그리는 방법에 중점을 두어 설명합니다.  
  
<a name="coord_space"></a>   
## 3차원 좌표 공간  
 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 그래픽의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 좌표계 원점은 렌더링 영역\(일반적으로 화면\)의 왼쪽 위에서 시작됩니다.  [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 시스템에서 x축의 양수 값은 오른쪽으로 진행되고 y축의 양수 값은 아래로 진행됩니다.  그러나 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 좌표계에서 원점은 렌더링 영역의 중앙에서 시작됩니다. 여기서 x축의 양수 값은 오른쪽으로 진행되고 y축의 양수 값은 위로 진행되며 z축의 양수 값은 원점에서 뷰어를 향해 바깥쪽으로 진행됩니다.  
  
 ![좌표계](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-1.png "CoordSystem\-1")  
기존의 2차원 및 3차원 좌표계 표현  
  
 이러한 축으로 정의되는 공간은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 개체에 대한 고정된 참조 프레임입니다.  이 공간에서 모델을 빌드하고 이를 보기 위한 조명과 카메라를 만들 때는 변환 적용 시 각 모델에 대해 만드는 로컬 참조 프레임을 이 고정된 참조 프레임 또는 "전역 공간"과 구분하면 유용합니다.  또한 전역 공간의 개체는 조명 및 카메라 설정에 따라 완전히 다르게 보이거나 전혀 보이지 않을 수 있지만 카메라의 위치는 전역 공간에서 개체의 위치를 변경하지 않습니다.  
  
<a name="cameras"></a>   
## 카메라 및 프로젝션  
 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]에서 작업을 수행하는 개발자는 2차원 화면에서 그리기 기본 도형을 배치하는 작업에 익숙할 것입니다.  [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면을 만들 경우 실제로는 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 개체의 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 표현을 만드는 것임을 기억해야 합니다.  [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면은 보는 이의 시점에 따라 다르게 보이므로 시점을 지정해야 합니다.  <xref:System.Windows.Media.Media3D.Camera> 클래스를 사용하면 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면에 대한 이러한 시점을 지정할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 표면에서 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면이 표시되는 방법은 장면을 보기 표면에 대한 프로젝션으로 기술하여 이해할 수도 있습니다.  <xref:System.Windows.Media.Media3D.ProjectionCamera>를 사용하면 다른 프로젝션 및 해당 속성을 지정하여 보는 이가 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 모델을 보는 방법을 변경할 수 있습니다.  <xref:System.Windows.Media.Media3D.PerspectiveCamera>는 장면에 원급법을 적용하는 프로젝션을 지정합니다.  즉, <xref:System.Windows.Media.Media3D.PerspectiveCamera>는 소실점 원근감을 제공합니다.  장면 좌표 공간에서의 카메라 위치, 카메라의 방향 및 뷰 필드, 장면의 "위쪽" 방향을 정의하는 벡터를 지정할 수 있습니다.  다음 다이어그램에서는 <xref:System.Windows.Media.Media3D.PerspectiveCamera>의 프로젝션을 보여 줍니다.  
  
 <xref:System.Windows.Media.Media3D.ProjectionCamera>의 <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> 및 <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> 속성은 카메라 프로젝션의 범위를 제한합니다.  카메라는 장면의 어느 위치에든 배치될 수 있으므로 카메라가 모델 내 또는 모델에 매우 가깝게 배치될 수 있으며 이로 인해 개체를 제대로 구별하기가 어려워집니다.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>를 사용하면 개체를 그릴 수 없는 카메라로부터의 최소 거리를 지정할 수 있습니다.  반대로 <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A>를 사용하면 개체를 그릴 수 없는 카메라로부터의 거리를 지정하여 너무 멀어서 인식할 수 없는 개체가 장면에 포함되지 않도록 만들 수 있습니다.  
  
 ![카메라 설정](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-6.png "CoordSystem\-6")  
카메라 위치  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera>는 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 모델의 직교 프로젝션을 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 시각적 표면으로 지정합니다.  다른 카메라와 마찬가지로 이는 위치, 보기 방향 및 "위쪽" 방향을 지정합니다.  그러나 <xref:System.Windows.Media.Media3D.PerspectiveCamera>와는 달리 <xref:System.Windows.Media.Media3D.OrthographicCamera>는 원근 포어쇼트닝\(foreshortening\)을 포함하지 않는 프로젝션을 설명합니다.  즉, <xref:System.Windows.Media.Media3D.OrthographicCamera>는 면이 카메라의 특정 지점에서 만나는 것이 아니라 평행한 보기 상자를 기술합니다.  다음 그림에서는 동일한 모델을 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 및 <xref:System.Windows.Media.Media3D.OrthographicCamera>를 사용하여 보여 줍니다.  
  
 ![직교 및 원근 프로젝션](../../../../docs/framework/wpf/graphics-multimedia/media/camera-projections4.png "Camera\_projections4")  
원근 및 직교 프로젝션  
  
 다음 코드에서는 일반적인 카메라 설정을 보여 줍니다.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>   
## 모델 및 망상 조직 기본 도형  
 <xref:System.Windows.Media.Media3D.Model3D>는 일반 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 개체를 나타내는 추상 기본 클래스입니다.  [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면을 빌드하려면 볼 개체와 <xref:System.Windows.Media.Media3D.Model3D>에서 파생된 장면 그래프를 구성하는 개체가 있어야 합니다.  현재 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 <xref:System.Windows.Media.Media3D.GeometryModel3D>를 사용하여 기하 도형을 모델링할 수 있습니다.  이 모델의 <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> 속성은 망상 조직 기본 도형을 사용합니다.  
  
 모델을 빌드하려면 먼저 기본 도형 또는 망상 조직을 빌드합니다.  [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 기본 도형은 단일 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 엔터티를 구성하는 꼭짓점 컬렉션입니다.  대부분의 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 시스템은 가장 간단한 닫힌 그림, 즉 세 개의 꼭짓점으로 정의되는 삼각형을 기반으로 모델링되는 기본 요소를 제공합니다.  삼각형의 세 점은 같은 평면에 있으므로 망상 조직이라는 보다 복잡한 도형을 모델링하기 위해 계속해서 삼각형을 추가할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 시스템은 현재 모든 기하 도형을 지정할 수 있는 <xref:System.Windows.Media.Media3D.MeshGeometry3D> 클래스를 제공합니다. 구 및 입방체와 같은 미리 정의된 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 기본 도형은 현재 지원되지 않습니다.  먼저 삼각형의 꼭짓점 목록을 해당 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 속성으로 지정하여 <xref:System.Windows.Media.Media3D.MeshGeometry3D>를 만듭니다.  각 꼭짓점은 <xref:System.Windows.Media.Media3D.Point3D>로 지정됩니다.  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서는 이 속성을 각 꼭짓점의 좌표를 나타내는 세 숫자가 그룹화된 목록으로 지정합니다. 해당 기하 도형에 따라 망상 조직은 여러 개의 삼각형으로 구성될 수 있고 그 중 일부는 같은 모퉁이\(꼭짓점\)를 공유할 수 있습니다.  망상 조직을 올바르게 그리려면 어떤 삼각형에 어떤 꼭짓점이 공유되는지에 대한 정보를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 제공해야 합니다.  이 정보는 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 속성을 통해 삼각형 인덱스 목록을 지정하여 제공합니다.  이 목록은 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 목록에 지정된 점이 삼각형을 결정하는 순서를 지정합니다.  
  
 [!code-xml[basic3d#Basic3DXAML3DN3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 앞의 예에서 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 목록은 8개의 꼭짓점을 지정하여 입방형 망상 조직을 정의합니다.  <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 속성은 인덱스 세 개로 구성된 12개 그룹 목록을 지정합니다.  목록의 각 숫자는 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 목록으로의 오프셋을 나타냅니다.  예를 들어 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 목록으로 지정된 첫 세 개의 꼭짓점은 \(1,1,0\), \(0,1,0\), \(0,0,0\)입니다.  <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 목록으로 지정된 첫 세 개의 인덱스는 0, 2, 1이며 각각 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 목록의 첫 번째, 세 번째, 두 번째 점에 해당합니다.  그 결과 입방형 모델을 구성하는 첫 번째 삼각형은 \(1,1,0\)에서 \(0,1,0\) 및 \(0,0,0\)으로 이어지고 나머지 11개의 삼각형도 이와 비슷하게 결정됩니다.  
  
 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> 및 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> 속성 값을 지정하여 계속해서 모델을 정의할 수 있습니다.  모델의 표면을 렌더링하려면 그래픽 시스템에 임의의 삼각형에서 해당 표면이 어느 방향을 바라보고 있는지에 대한 정보가 필요합니다.  그래픽 시스템은 이 정보를 사용하여 모델에 대한 조명 계산을 수행할 수 있습니다. 즉, 광원쪽 표면이 광원 반대쪽 표면보다 밝게 나타납니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 위치 좌표를 사용하여 기본 법선 벡터를 결정할 수 있지만 다른 법선 벡터를 지정하여 곡선 표면에 근접한 모양을 만들 수도 있습니다.  
  
 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> 속성은 질감이 그려지는 방법을 결정하는 좌표를 망상 조직의 꼭짓점에 매핑하는 방법을 그래픽 시스템에 알려주는 <xref:System.Windows.Point> 컬렉션을 지정합니다.  <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>는 0과 1을 포함하는 사이 값으로 지정됩니다.  <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> 속성과 마찬가지로 그래픽 시스템은 기본 질감 좌표를 계산할 수 있지만 다른 질감 좌표를 선택하여 반복 패턴의 일부를 포함하는 등의 질감 매핑을 제어할 수도 있습니다.  질감 좌표에 대한 자세한 내용은 다음 항목 또는 관리되는 Direct3D SDK를 참조하십시오.  
  
 다음 예제에서는 입방형 모델의 한 면을 프로시저 코드로 만드는 방법을 보여 줍니다.  입방체 전체를 단일 GeometryModel3D로 그릴 수 있지만 이 예제에서는 나중에 각 면에 별도의 질감을 적용하기 위해 입방체 면을 고유한 모델로 그립니다.  
  
 [!code-csharp[3doverview#3DOverview3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>   
## 모델에 재질 적용  
 망상 조직이 3차원 개체로 보이도록 만들려면 조명을 비추고 카메라로 프로젝션할 수 있도록 해당 꼭짓점과 삼각형으로 정의된 표면에 질감을 적용해야 합니다.  [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]에서는 <xref:System.Windows.Media.Brush> 클래스를 사용하여 색, 패턴, 그라데이션 또는 기타 시각적 콘텐츠를 화면 영역에 적용합니다.  그러나 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 개체의 모양은 이 개체에 적용된 색 또는 패턴뿐만 아니라 모델에 조명을 비춘 결과로 결정됩니다.  실제 개체는 표면의 특성에 따라 빛을 다르게 반사합니다. 광택이 나거나 빛나는 표면은 거칠거나 윤기 없는 표면과 다르게 보이며 어떤 개체는 빛을 흡수하는 것처럼 보이는 반면 다른 개체는 빛이 납니다.  [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 개체에 적용할 수 있는 것과 같은 브러시를 모두 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 개체에 적용할 수 있지만 직접 적용할 수는 없습니다.  
  
 모델의 표면 특성을 정의하기 위해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 <xref:System.Windows.Media.Media3D.Material> 추상 클래스를 사용합니다.  Material의 실제적인 서브클래스는 모델 표면의 일부 모양 특성을 결정하며 이들 각각은 SolidColorBrush, TileBrush 또는 VisualBrush를 전달할 수 있는 Brush 속성도 제공합니다.  
  
-   <xref:System.Windows.Media.Media3D.DiffuseMaterial>은 확산 조명이 적용된 것처럼 브러시가 모델에 적용되도록 지정합니다.  DiffuseMaterial을 사용하면 브러시를 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 모델에 직접 사용하는 것과 가장 비슷한 효과를 내며 모델의 표면은 빛나는 것처럼 빛을 반사하지 않습니다.  
  
-   <xref:System.Windows.Media.Media3D.SpecularMaterial>은 모델의 표면이 하이라이트를 반사할 수 있는 딱딱하거나 빛나는 표면인 것처럼 브러시가 모델에 적용되도록 지정합니다.  <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> 속성 값을 지정하여 질감에 이러한 반사 특성 또는 "빛나는 효과"가 표현되는 정도를 설정할 수 있습니다.  
  
-   <xref:System.Windows.Media.Media3D.EmissiveMaterial>을 사용하면 모델이 브러시 색과 동일한 조명을 내보내는 것처럼 질감이 적용되도록 지정할 수 있습니다.  이로 인해 모델이 조명으로 변경되는 것은 아니며 모델은 DiffuseMaterial 또는 SpecularMaterial을 사용하여 질감을 표현할 때와는 다른 방식으로 그림자 지정에 참여합니다.  
  
 성능 개선을 위해 <xref:System.Windows.Media.Media3D.GeometryModel3D>의 뒷면\(카메라에서 볼 때 모델의 반대편에 있어 시야에 들어오지 않는 면\)은 장면에서 컬링됩니다.  평면과 같이 모델의 뒷면에 적용할 <xref:System.Windows.Media.Media3D.Material>을 지정하려면 모델의 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> 속성을 설정합니다.  
  
 빛이 나거나 반사되는 효과와 같은 일부 표면 특성을 얻으려면 모델에 여러 개의 서로 다른 브러시를 연속으로 적용해야 할 수 있습니다.  <xref:System.Windows.Media.Media3D.MaterialGroup> 클래스를 사용하여 여러 재질을 적용하고 다시 사용할 수 있습니다.  MaterialGroup의 자식이 맨 먼저 적용되어 여러 렌더링 패스에서 지속됩니다.  
  
 다음 코드 예제에서는 브러시로 그리기 및 단색을 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 모델에 적용하는 방법을 보여 줍니다.  
  
 [!code-xml[basic3d#Basic3DXAML3DN5](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  
 [!code-xml[3doverview#3DOverview3DN9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
  
 [!code-csharp[3doverview#3DOverview3DN8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
 [!code-vb[3doverview#3DOverview3DN8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>   
## 장면 비추기  
 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 그래픽의 조명은 실제 조명의 역할을 합니다. 즉, 표면이 보이도록 만듭니다.  보다 정확히 말해 조명은 프로젝션에 포함될 장면의 부분을 결정합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 조명 개체는 다양한 조명 및 그림자 효과를 만들며 다양한 실제 조명의 동작을 기반으로 모델링됩니다.  장면에 하나 이상의 조명을 포함하지 않으면 모델이 보이지 않습니다.  
  
 다음 조명은 기본 클래스 <xref:System.Windows.Media.Media3D.Light>에서 파생된 것입니다.  
  
-   <xref:System.Windows.Media.Media3D.AmbientLight>: 위치나 방향에 관계없이 모든 개체를 균등하게 비추는 앰비언트 조명을 제공합니다.  
  
-   <xref:System.Windows.Media.Media3D.DirectionalLight>: 광원이 멀리 떨어져 있는 것처럼 비춥니다.  방향성 조명은 <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A>이 Vector3D로 지정되지만 위치는 지정되지 않습니다.  
  
-   <xref:System.Windows.Media.Media3D.PointLight>: 광원이 가까이 있는 것처럼 비춥니다.  점 조명은 지정된 위치가 있으며 해당 위치에서 조명을 비춥니다.  장면의 개체는 조명과 관련된 해당 위치 및 거리에 따라 비춰집니다.  <xref:System.Windows.Media.Media3D.PointLightBase>는 모델에 조명이 비춰지는 최대 거리를 결정하는 <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> 속성을 노출합니다.  점 조명은 거리에 따라 조명의 강도가 감소되는 방식을 결정하는 감쇠 속성도 노출합니다.  조명 감쇠에 대해 상수, 선형 또는 정방형 보간을 지정할 수 있습니다.  
  
-   <xref:System.Windows.Media.Media3D.SpotLight>: <xref:System.Windows.Media.Media3D.PointLight>에서 상속합니다.  스폿 조명은 점 조명과 유사하게 비추며 위치와 방향이 모두 지정됩니다.  스폿 조명은 <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> 및 <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> 속성을 각도로 지정하여 원뿔 모양 영역에 조명을 비춥니다.  
  
 조명은 <xref:System.Windows.Media.Media3D.Model3D> 개체이므로 위치, 색, 방향 및 범위와 같은 조명 속성을 변환하고 해당 속성에 애니메이션 효과를 줄 수 있습니다.  
  
 [!code-xml[hittest3d#HitTest3D3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>   
## 모델 변환  
 모델을 만들 때 모델에는 장면에서의 특정 위치가 지정됩니다.  장면에서 이러한 모델을 이동하거나, 회전하거나, 크기를 변경하기 위해 모델 자체를 정의하는 꼭짓점을 변경하는 것은 비효율적입니다.  대신 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]에서와 같이 모델에 변환을 적용합니다.  
  
 각 모델 개체에는 모델을 이동하고, 방향을 다시 지정하고, 크기를 조정할 수 있는 <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> 속성이 있습니다.  변환을 적용할 때는 변환에 의해 지정된 벡터 또는 값이 무엇이든 실제적으로 모델의 모든 점을 오프셋하게 됩니다.  즉, 모델이 정의된 좌표 공간\("모델 공간"\)은 변환하지만 장면 전체\("전역 공간"\)의 좌표계에서 모델의 기하 도형을 구성하는 값은 변경하지 않습니다.  
  
 모델 변환에 대한 자세한 내용은 [3차원 변환 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md)를 참조하십시오.  
  
<a name="animations"></a>   
## 모델에 애니메이션 효과 주기  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 구현은 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 그래픽과 동일한 타이밍 및 애니메이션 시스템에 참여합니다.  즉, 3차원 장면에 애니메이션 효과를 주려면 해당 모델의 속성에 애니메이션 효과를 줍니다.  기본 도형의 속성에 직접 애니메이션 효과를 줄 수도 있지만 일반적으로 모델의 위치나 모양을 변경하는 변환에 애니메이션 효과를 주는 것이 보다 쉽습니다.  변환은 개별 모델뿐만 아니라 <xref:System.Windows.Media.Media3D.Model3DGroup> 개체에도 적용될 수 있으므로 Model3DGroup의 자식에 한 애니메이션 집합을 적용하고 자식 개체 그룹에는 또 다른 애니메이션 집합을 적용할 수 있습니다.  장면의 조명 속성에 애니메이션 효과를 주어 다양한 시각적 효과를 얻을 수도 있습니다.  마지막으로 카메라 위치 또는 뷰 필드에 애니메이션 효과를 주어 프로젝션 자체에 애니메이션 효과를 줄 수 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 타이밍 및 애니메이션 시스템에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md), [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md) 및 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md) 항목을 참조하십시오.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 개체에 애니메이션 효과를 주려면 시간 표시 막대를 만들고 애니메이션\(시간이 지남에 따른 일부 속성 값의 변경\)을 정의한 다음 애니메이션을 적용할 속성을 지정합니다.  [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면의 모든 개체는 <xref:System.Windows.Controls.Viewport3D>의 자식이므로 장면에 적용하려는 모든 애니메이션에 사용되는 속성은 Viewport3D의 속성입니다.  
  
 모델이 제자리에서 비틀거리는 것처럼 보이게 만들려는 경우  모델에 <xref:System.Windows.Media.Media3D.RotateTransform3D>를 적용하고 한 벡터에서 다른 벡터로의 회전 축에 애니메이션 효과를 줄 수 있습니다.  다음 코드 예제에서는 RotateTransform3D가 TransformGroup이 있는 모델에 적용된 여러 변환 중 하나라는 가정 하에 변환의 Rotation3D에 대한 Axis 속성에 Vector3DAnimation을 적용하는 방법을 보여 줍니다.  
  
 [!code-csharp[3doverview#3DOverview3DN1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>   
## 창에 3차원 콘텐츠 추가  
 장면을 렌더링하려면 <xref:System.Windows.Media.Media3D.Model3DGroup>에 모델과 조명을 추가한 다음 <xref:System.Windows.Media.Media3D.Model3DGroup>을 <xref:System.Windows.Media.Media3D.ModelVisual3D>의 <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A>로 설정합니다.  <xref:System.Windows.Controls.Viewport3D>의 <xref:System.Windows.Controls.Viewport3D.Children%2A> 컬렉션에 <xref:System.Windows.Media.Media3D.ModelVisual3D>를 추가합니다.  해당 <xref:System.Windows.Controls.Viewport3D.Camera%2A> 속성을 설정하여 <xref:System.Windows.Controls.Viewport3D>에 카메라를 추가합니다.  
  
 마지막으로 창에 <xref:System.Windows.Controls.Viewport3D>를 추가합니다.  <xref:System.Windows.Controls.Viewport3D>가 캔버스와 같은 레이아웃 요소의 콘텐츠로 포함될 경우에는 <xref:System.Windows.FrameworkElement>에서 상속된 해당 <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.Width%2A> 속성을 설정하여 Viewport3D의 크기를 지정합니다.  
  
 [!code-xml[hostingwpfusercontrolinwf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Viewport3D>   
 <xref:System.Windows.Media.Media3D.PerspectiveCamera>   
 <xref:System.Windows.Media.Media3D.DirectionalLight>   
 <xref:System.Windows.Media.Media3D.Material>   
 [3차원 변환 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md)   
 [WPF 3D 성능 최대화](../../../../docs/framework/wpf/graphics-multimedia/maximize-wpf-3d-performance.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-how-to-topics.md)   
 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)