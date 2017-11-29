---
title: "3차원 그래픽 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D graphics [WPF]
- graphics [WPF], 3-D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 979cc7580471f616d39056f541b8374b372e8e88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="3-d-graphics-overview"></a>3차원 그래픽 개요
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 기능을 사용하여 개발자는 태그 및 프로시저 코드로 3차원 그래픽을 그리고 변환하며 이러한 그래픽에 애니메이션 효과를 줄 수 있습니다. 개발자는 [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] 및 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 그래픽을 결합하여 다양한 컨트롤을 만들거나, 복잡한 데이터 표시를 제공하거나, 응용 프로그램 인터페이스의 사용자 환경을 개선할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 지원은 모든 기능을 갖춘 게임 개발 플랫폼을 제공하기 위한 것은 아닙니다. 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 시스템의 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 기능에 대해 간략하게 설명합니다.  
 
  
<a name="threed_in_2d"></a>   
## <a name="3-d-in-a-2-d-container"></a>2차원 컨테이너의 3차원  
 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]그래픽 콘텐츠 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소에는 캡슐화 된 <xref:System.Windows.Controls.Viewport3D>, 2 차원 요소 구조에 참여할 수 있는 합니다. 그래픽 시스템 처리 <xref:System.Windows.Controls.Viewport3D> 의 다른 많은 처럼 2 차원 시각적 요소로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다. <xref:System.Windows.Controls.Viewport3D>창 처럼-뷰포트-3 차원 장면에 있습니다. 보다 정확히 말해 이는 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면이 프로젝션되는 표면입니다.  
  
 기존 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 응용 프로그램을 사용 하 여 <xref:System.Windows.Controls.Viewport3D> 표나 캔버스와 같은 다른 컨테이너 요소와 마찬가지로 합니다.  사용할 수 있지만 <xref:System.Windows.Controls.Viewport3D> 다른 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 동일한 장면 그래프에서 그리기 개체 있습니다 상호 침투할 수 없습니다 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 및 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 내에서 개체는 <xref:System.Windows.Controls.Viewport3D>합니다.  이 항목을 그리는 방법을 중점적 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 내 그래픽은 <xref:System.Windows.Controls.Viewport3D>합니다.  
  
<a name="coord_space"></a>   
## <a name="3-d-coordinate-space"></a>3차원 좌표 공간  
 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 그래픽의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 좌표계는 렌더링 영역(일반적으로 화면)의 왼쪽 위에서 원점을 찾습니다. [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 시스템에서 양의 x-축 값은 오른쪽으로 진행되고 양의 y-축 값은 아래로 진행됩니다.  그러나 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 좌표계에서는 원점이 렌더링 영역의 중앙에 있습니다. 여기서 양의 x-축 값은 오른쪽으로 진행되고 양의 y-축 값은 위로 진행되며 양의 z-축 값은 원점에서 뷰어를 향해 바깥쪽으로 진행됩니다.  
  
 ![좌표계](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-1.png "CoordSystem-1")  
기존의 2차원 및 3차원 좌표계 표현  
  
 이러한 축으로 정의되는 공간은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 개체에 대한 고정 참조 프레임입니다. 이 공간에서 모델을 빌드하고 이를 보기 위한 광원과 카메라를 만들 때는 변환 적용 시 각 모델에 대해 만드는 로컬 참조 프레임을 이 고정 참조 프레임 또는 "월드 공간"과 구분하면 유용합니다. 또한 월드 공간의 개체는 광원 및 카메라 설정에 따라 완전히 다르게 보이거나 전혀 보이지 않을 수 있지만 카메라의 위치는 월드 공간에서 개체의 위치를 변경하지 않습니다.  
  
<a name="cameras"></a>   
## <a name="cameras-and-projections"></a>카메라 및 프로젝션  
 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]에서 작업을 수행하는 개발자는 2차원 화면에서 그리기 기본 형식을 배치하는 작업에 익숙할 것입니다. [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면을 만들 경우 실제로는 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 개체의 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 표현을 만드는 것임을 기억해야 합니다. [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면은 보는 이의 시점에 따라 다르게 보이므로 시점을 지정해야 합니다. <xref:System.Windows.Media.Media3D.Camera> 클래스를 사용 하면이 관점에 대 한를 지정할 수 있습니다는 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면 합니다.  
  
 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 표면에서 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면이 표시되는 방법은 장면을 보기 표면에 대한 프로젝션으로 설명하여 이해할 수도 있습니다. <xref:System.Windows.Media.Media3D.ProjectionCamera> 다른 예상 및 보이므로 시점에 게 표시 방법을 변경 하려면 해당 속성을 지정할 수 있습니다 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 모델. A <xref:System.Windows.Media.Media3D.PerspectiveCamera> 장면 foreshortens 프로젝션을 지정 합니다.  즉,는 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 소실점 관점을 제공 합니다.  장면 좌표 공간에서의 카메라 위치, 카메라의 방향 및 시야, 장면의 "위쪽" 방향을 정의하는 벡터를 지정할 수 있습니다. 다음 다이어그램에서는 <xref:System.Windows.Media.Media3D.PerspectiveCamera>의 프로젝션 합니다.  
  
 <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> 및 <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> 의 속성 <xref:System.Windows.Media.Media3D.ProjectionCamera> 투영 카메라의의 범위를 제한 합니다. 카메라는 장면의 어느 위치에나 배치될 수 있으므로 카메라가 실제로 모델 내 또는 모델에 매우 가깝게 배치될 수 있으며 이로 인해 개체를 제대로 구별하기가 어려워집니다.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>최소 거리를 개체가 그려지지 것입니다를 지정할 수 있습니다.  반대로, <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> 인식할 수 없는 개체를 너무 멀리 떨어져 장면에 포함 되지 않습니다 보장 하는 초과 개체가 그려지지 것입니다, 카메라의 거리를 지정할 수 있습니다.  
  
 ![카메라 설정](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-6.png "CoordSystem 6")  
카메라 위치  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera>직교 프로젝션을 지정는 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 모델는 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 비주얼 화면입니다. 다른 카메라와 마찬가지로 이는 위치, 보기 방향 및 "위쪽" 방향을 지정합니다. 와 달리 <xref:System.Windows.Media.Media3D.PerspectiveCamera>그러나 <xref:System.Windows.Media.Media3D.OrthographicCamera> 단축법 관점을 포함 하지 않는 프로젝션에 설명 합니다. 즉, <xref:System.Windows.Media.Media3D.OrthographicCamera> 해당 면이는 카메라 특정 지점에서 만나는 것 대신 병렬 보기 상자에 설명 합니다. 다음 이미지를 사용 하 여 표시 된 대로 동일한 모델을 보여 줍니다 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 및 <xref:System.Windows.Media.Media3D.OrthographicCamera>합니다.  
  
 ![직교 및 원근 프로젝션](../../../../docs/framework/wpf/graphics-multimedia/media/camera-projections4.png "Camera_projections4")  
원근 및 직교 프로젝션  
  
 다음 코드에서는 일반적인 카메라 설정을 보여 줍니다.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>   
## <a name="model-and-mesh-primitives"></a>모델 및 메시 기본 형식  
  
 <xref:System.Windows.Media.Media3D.Model3D>제네릭을 나타내는 추상 기본 클래스 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 개체입니다. 빌드하는 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면에 일부 개체를 보려면 필요 하 고 장면 그래프를 구성 하는 개체에서 파생 <xref:System.Windows.Media.Media3D.Model3D>합니다. 현재는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기 하 모델링 지원 <xref:System.Windows.Media.Media3D.GeometryModel3D>합니다. <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> 이 모델의 두 메시 기본 합니다.  
  
 모델을 빌드하려면 먼저 기본 형식 또는 메시를 빌드합니다. [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 기본 형식은 단일 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 엔터티를 구성하는 꼭짓점 컬렉션입니다. 대부분의 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 시스템은 가장 간단한 닫힌 그림, 즉 세 개의 꼭짓점으로 정의되는 삼각형을 기반으로 모델링되는 기본 형식을 제공합니다.  삼각형의 세 점은 같은 평면에 있으므로 메시라는 보다 복잡한 도형을 모델링하기 위해 계속해서 삼각형을 추가할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 시스템에서 현재 제공는 <xref:System.Windows.Media.Media3D.MeshGeometry3D> 클래스 형상 지정할 수 있습니다; 현재 지원 하지 않습니다 미리 정의 된 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 구, 입방 형 forms 등의 기본 형식입니다. 만들기를 시작할는 <xref:System.Windows.Media.Media3D.MeshGeometry3D> 으로 삼각형 꼭지점 목록을 지정 하 여 해당 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 속성입니다. 로 지정 된 각 꼭 짓 점에 <xref:System.Windows.Media.Media3D.Point3D>합니다.  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서는 이 속성을 각 꼭짓점의 좌표를 나타내는 세 숫자가 그룹화된 목록으로 지정합니다. 해당 기하 도형에 따라 메시는 여러 개의 삼각형으로 구성될 수 있고 그 중 일부는 같은 모퉁이(꼭짓점)를 공유할 수 있습니다. 메시를 올바르게 그리려면 어떤 삼각형에 어떤 꼭짓점이 공유되는지에 대한 정보를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 제공해야 합니다. 삼각형 인덱스 목록을 지정 하 여이 정보를 제공는 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 속성입니다. 요소에 지정 된 순서를 지정 하는이 목록에서 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 목록 삼각형을 결정 합니다.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 앞의 예제에는 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 입방 형 메시를 정의 하는 8 개의 꼭지점을 지정 하는 목록입니다. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 속성 세 인덱스의 12 개까지 그룹의 목록을 지정 합니다.  각 번호 목록에 참조에 대 한 오프셋 하는 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 목록입니다.  예를 들어 처음 세 개의 꼭 짓 점을로 지정 된는 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 목록 됩니다 (1,1,0) (0,1,0) 및 (0,0,0). 처음 세 개의로 지정 된 인덱스는 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 목록은 0, 2, 1, 셋째, 첫 번째에 대응 하며의 포인트의 두 번째는 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 목록입니다. 그 결과 큐브 모델을 구성하는 첫 번째 삼각형은 (1,1,0)에서 (0,1,0) 및 (0,0,0)으로 이어지고 나머지 11개의 삼각형도 이와 비슷하게 결정됩니다.  
  
 계속 모델에 대 한 값을 지정 하 여 정의할 수는 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> 및 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> 속성입니다.  모델의 표면을 렌더링하려면 지정된 임의의 삼각형에서 해당 표면이 어느 방향을 바라보고 있는지에 대한 정보를 그래픽 시스템에 제공해야 합니다. 그래픽 시스템은 이 정보를 사용하여 모델에 대한 조명 계산을 수행할 수 있습니다. 즉, 광원 쪽 표면이 광원 반대쪽 표면보다 밝게 나타납니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 위치 좌표를 사용하여 기본 법선 벡터를 결정할 수 있지만 다른 법선 벡터를 지정하여 곡선 표면의 모양을 대략적으로 나타낼 수도 있습니다.  
  
 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> 속성의 컬렉션을 지정 <xref:System.Windows.Point>그래픽 시스템 메시의 꼭 짓 텍스처를 그리는 방법을 결정 하는 좌표를 매핑하는 방법을 알려 주는 s입니다. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>0과 1 사이의 값으로 지정 됩니다.  과 마찬가지로 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> 속성을 기본 질감 좌표 하지만 예를 들어 반복 패턴의 일부를 포함 하는 텍스처의 매핑을 제어 하는 다른 질감 좌표를 설정 하도록 선택할 수도 있습니다 그래픽 시스템을 계산할 수 있습니다. 질감 좌표에 대한 자세한 내용은 다음 항목 또는 Managed Direct3D SDK를 참조하세요.  
  
 다음 예제에서는 프로시저 코드로 큐브 모델의 한 면을 만드는 방법을 보여 줍니다. 큐브 전체를 단일 GeometryModel3D로 그릴 수 있지만 이 예제에서는 나중에 각 면에 별도의 질감을 적용하기 위해 큐브 면을 고유한 모델로 그립니다.  
  
 [!code-csharp[3doverview#3DOverview3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>   
## <a name="applying-materials-to-the-model"></a>모델에 재질 적용  
  
 메시가 3차원 개체로 보이도록 만들려면 카메라로 비추고 프로젝션할 수 있도록 해당 꼭짓점과 삼각형으로 정의된 표면에 질감을 적용해야 합니다. [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]를 사용 하면는 <xref:System.Windows.Media.Brush> 화면 영역에 색, 패턴, 그라데이션, 또는 기타 시각적 콘텐츠를 적용 하는 클래스입니다.  그러나 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 개체의 모양은 이 개체에 적용된 색 또는 패턴뿐만 아니라 조명 모델의 기능입니다. 실제 개체는 표면의 품질에 따라 빛을 다르게 반사합니다. 광택이 나거나 빛나는 표면은 거칠거나 윤기 없는 표면과 다르게 보이며 어떤 개체는 빛을 흡수하는 것처럼 보이는 반면 다른 개체는 빛이 납니다. [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 개체에 적용할 수 있는 동일한 브러시를 모두 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 개체에 적용할 수 있지만 직접 적용할 수는 없습니다.  
  
 모델의 표면 특징을 정의 하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용 하 여는 <xref:System.Windows.Media.Media3D.Material> 추상 클래스입니다. Material의 구체적 하위 클래스는 모델 표면의 일부 모양 특성을 결정하며 이들 각각은 SolidColorBrush, TileBrush 또는 VisualBrush를 전달할 수 있는 Brush 속성도 제공합니다.  
  
-   <xref:System.Windows.Media.Media3D.DiffuseMaterial>해당 모델 확산이 켜진 된 것 처럼 브러시 모델에 적용 됨을 지정 합니다. DiffuseMaterial을 사용하면 브러시를 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 모델에 직접 사용하는 것과 가장 비슷한 효과를 내며 모델의 표면은 빛나는 것처럼 빛을 반사하지 않습니다.  
  
-   <xref:System.Windows.Media.Media3D.SpecularMaterial>모델의 표면이 하드 또는 반짝이 반사 하이라이트 수 있는 것 처럼 브러시 모델에 적용 됨을 지정 합니다. 에 대 한 값을 지정 하 여 있는 질감에서 반사 특성 또는 "빛"이 제안 하는 정도 설정할 수 있습니다는 <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> 속성입니다.  
  
-   <xref:System.Windows.Media.Media3D.EmissiveMaterial>모델와 같은 브러시의 색을 내보내는 것 처럼 질감 적용 되도록 지정할 수 있습니다. 그러나 이로 인해 모델이 광원이 되는 것은 아니며 DiffuseMaterial 또는 SpecularMaterial을 사용하여 질감을 표현할 때와는 다른 방식으로 섀도잉에 참여합니다.  
  
 뒷면 성능 향상을 위해는 <xref:System.Windows.Media.Media3D.GeometryModel3D> (카메라에서 모델의 반대쪽에 있기 때문에 표시 되지 않는 면) 장면에서 추출 됩니다.  지정 하는 <xref:System.Windows.Media.Media3D.Material> 평면와 같은 모델의 뒷면에 적용 하려면 모델의 설정 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> 속성입니다.  
  
 빛이 나거나 반사되는 효과와 같은 일부 표면 품질을 얻으려면 모델에 여러 개의 서로 다른 브러시를 연속으로 적용해야 할 수 있습니다. 적용 하 고 여러 자료를 사용 하 여 다시 사용할 수는 <xref:System.Windows.Media.Media3D.MaterialGroup> 클래스입니다. MaterialGroup의 자식이 맨 먼저 적용되어 여러 렌더링 패스에서 지속됩니다.  
  
 다음 코드 예제에서는 브러시로 그리기 및 단색을 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 모델에 적용하는 방법을 보여 줍니다.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  
 [!code-xaml[3doverview#3DOverview3DN9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
  
 [!code-csharp[3doverview#3DOverview3DN8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
 [!code-vb[3doverview#3DOverview3DN8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>   
## <a name="illuminating-the-scene"></a>장면 비추기  
 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 그래픽의 광원은 실제 광원의 역할을 합니다. 즉, 표면이 보이도록 만듭니다. 보다 정확히 말해 광원은 프로젝션에 포함될 장면의 부분을 결정합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 광원 개체는 다양한 명암 효과를 만들며 여러 실제 광원의 동작을 기반으로 모델링됩니다. 장면에 하나 이상의 광원을 포함하지 않으면 모델이 보이지 않습니다.  
  
 기본 클래스에서 파생 되는 다음 광원 <xref:System.Windows.Media.Media3D.Light>:  
  
-   <xref:System.Windows.Media.Media3D.AmbientLight>: 모든 균일 하 게와 상관 없이 개체의 위치 또는 방향을 켜 집니다 앰비언트 조명을 제공 합니다.  
  
-   <xref:System.Windows.Media.Media3D.DirectionalLight>: 먼 광원이 것 처럼 켜 집니다.  방향 조명는 <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> 는 Vector3D 하지만 지정 된 위치가 없고로 지정 합니다.  
  
-   <xref:System.Windows.Media.Media3D.PointLight>: 근처 광원이 것 처럼 켜 집니다. PointLight는 위치가 있으며 해당 위치에서 빛을 발합니다. 장면의 개체는 광원과 관련된 해당 위치 및 거리에 따라 비춰집니다. <xref:System.Windows.Media.Media3D.PointLightBase>노출 된 <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> 넘어서면 모델 켜지 지 것입니다 조명에서 거리를 결정 하는 속성입니다. 또한 PointLight는 거리에 따라 광원의 강도가 감소되는 방식을 결정하는 감쇠 속성도 노출합니다. 광원 감쇠에 대해 상수, 선형 또는 정방형 보간을 지정할 수 있습니다.  
  
-   <xref:System.Windows.Media.Media3D.SpotLight>:에서 상속 되 <xref:System.Windows.Media.Media3D.PointLight>합니다. SpotLight는 PointLight와 유사하게 비추며 위치와 방향이 모두 있습니다. 설정한 원뿔 모양 영역의 light를 프로젝트 <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> 및 <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> 속성을도 단위로 지정 합니다.  
  
 불빛이 <xref:System.Windows.Media.Media3D.Model3D> 개체를 변환 하 고 밝은 속성, 위치, 색, 방향 및 범위를 포함 하 여 애니메이션을 적용할 수 있도록 합니다.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>   
## <a name="transforming-models"></a>모델 변환  
 모델을 만들 때 모델에는 장면에서의 특정 위치가 지정됩니다. 장면에서 이러한 모델을 이동하거나, 회전하거나, 크기를 변경하기 위해 모델 자체를 정의하는 꼭짓점을 변경하는 것은 비효율적입니다.  대신 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]에서와 같이 모델에 변환을 적용합니다.  
  
 각 모델 개체에는 <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> 속성을 이동할 수, 방향을 다시 지정 하거나 모델의 크기를 조정 합니다.  변환을 적용할 때는 변환에 의해 지정된 벡터 또는 값이 무엇이든 실제적으로 모델의 모든 점을 오프셋합니다. 즉, 모델이 정의된 좌표 공간("모델 공간")은 변환하지만 장면 전체("월드 공간")의 좌표계에서 모델의 기하 도형을 구성하는 값은 변경하지 않습니다.  
  
 모델 변환에 대한 자세한 내용은 [3차원 변환 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md)를 참조하세요.  
  
<a name="animations"></a>   
## <a name="animating-models"></a>모델에 애니메이션 효과 주기  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 구현은 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 그래픽과 동일한 타이밍 및 애니메이션 시스템에 참여합니다. 즉, 3차원 장면에 애니메이션 효과를 주려면 해당 모델의 속성에 애니메이션 효과를 줍니다. 기본 형식의 속성에 직접 애니메이션 효과를 줄 수도 있지만 일반적으로 모델의 위치나 모양을 변경하는 변환에 애니메이션 효과를 주는 것이 보다 쉽습니다. 변환에 적용할 수 있으므로 <xref:System.Windows.Media.Media3D.Model3DGroup> 개체와 개별 모델 한 애니메이션 집합 Model3DGroup의 자식 및 자식 개체의 그룹에는 애니메이션의 다른 집합에 적용할 수 있습니다. 장면의 조명 속성에 애니메이션 효과를 주어 다양한 시각적 효과를 얻을 수도 있습니다. 마지막으로 카메라 위치 또는 시야에 애니메이션 효과를 주어 프로젝션 자체에 애니메이션 효과를 주도록 선택할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 타이밍 및 애니메이션 시스템에 대한 배경 정보는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md), [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md) 및 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md) 항목을 참조하세요.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 개체에 애니메이션 효과를 주려면 타임라인을 만들고 애니메이션(시간이 지남에 따른 일부 속성 값의 변경)을 정의한 다음 애니메이션을 적용할 속성을 지정합니다. 때문에 모든 개체에는 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 장면 자식 요소인 <xref:System.Windows.Controls.Viewport3D>, 장면에 적용할 모든 애니메이션의 대상 속성은 속성 Viewport3D의 속성입니다.  
  
 모델이 제자리에서 비틀거리는 것처럼 보이게 만든다고 가정합니다. 적용 하도록 선택할 수도 있습니다는 <xref:System.Windows.Media.Media3D.RotateTransform3D> 모델에 다른에서 한 벡터의 회전 축에 애니메이션을 적용 합니다. 다음 코드 예제에서는 RotateTransform3D가 TransformGroup이 있는 모델에 적용된 여러 변환 중 하나라는 가정 하에 변환의 Rotation3D에 대한 Axis 속성에 Vector3DAnimation을 적용하는 방법을 보여 줍니다.  
  
 [!code-csharp[3doverview#3DOverview3DN1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>   
## <a name="add-3-d-content-to-the-window"></a>창에 3차원 콘텐츠 추가  
 장면을 렌더링 하려면에 모델과 조명을 추가 <xref:System.Windows.Media.Media3D.Model3DGroup>, 다음 설정의 <xref:System.Windows.Media.Media3D.Model3DGroup> 으로 <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> 의 <xref:System.Windows.Media.Media3D.ModelVisual3D>합니다. 추가 <xref:System.Windows.Media.Media3D.ModelVisual3D> 에 <xref:System.Windows.Controls.Viewport3D.Children%2A> 의 컬렉션은 <xref:System.Windows.Controls.Viewport3D>합니다. 카메라를 추가 <xref:System.Windows.Controls.Viewport3D> 설정 하 여 해당 <xref:System.Windows.Controls.Viewport3D.Camera%2A> 속성입니다.  
  
 마지막으로 추가 된 <xref:System.Windows.Controls.Viewport3D> 창에 있습니다. 경우는 <xref:System.Windows.Controls.Viewport3D> 설정 하 여 Viewport3D의 크기를 지정 하는 캔버스와 같은 레이아웃 요소 콘텐츠가 포함 되어 해당 <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.Width%2A> 속성 (에서 상속 되며, <xref:System.Windows.FrameworkElement>).  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Viewport3D>  
 <xref:System.Windows.Media.Media3D.PerspectiveCamera>  
 <xref:System.Windows.Media.Media3D.DirectionalLight>  
 <xref:System.Windows.Media.Media3D.Material>  
 [3차원 변환 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md)  
 [WPF 3D 성능 최대화](../../../../docs/framework/wpf/graphics-multimedia/maximize-wpf-3d-performance.md)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-how-to-topics.md)  
 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
