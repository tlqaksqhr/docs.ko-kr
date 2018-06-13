---
title: '방법: 결합된 기하 도형 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: 107e0342b822633ccb4f51f256c121cc80c297f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561123"
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="768a3-102">방법: 결합된 기하 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="768a3-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="768a3-103">이 예제에는 기 하 도형을 결합 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="768a3-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="768a3-104">두 기 하 도형을 함께 사용 하려면 사용을 <xref:System.Windows.Media.CombinedGeometry> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="768a3-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="768a3-105">설정의 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 결합 및 설정 하려면 두 기 하 도형 사용 하 여 속성의 <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> 기 하 도형이 함께 결합할 수는 방법을 확인 하는 경우이 속성을 `Union`, `Intersect`, `Exclude`, 또는 `Xor`.</span><span class="sxs-lookup"><span data-stu-id="768a3-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="768a3-106">두 개 이상의 기 하 도형에서 복합 geometry를 만들려면 사용는 <xref:System.Windows.Media.GeometryGroup>합니다.</span><span class="sxs-lookup"><span data-stu-id="768a3-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="768a3-107">예제</span><span class="sxs-lookup"><span data-stu-id="768a3-107">Example</span></span>  
 <span data-ttu-id="768a3-108">다음 예제에서는 <xref:System.Windows.Media.CombinedGeometry> 의 geometry 결합 모드를 사용 하 여 정의 `Exclude`합니다.</span><span class="sxs-lookup"><span data-stu-id="768a3-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="768a3-109">둘 다 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 원 반지름 하지만 센터 오프셋으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="768a3-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="768a3-110">![결합 모드의 Exclude 결과](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="768a3-110">![Results of the Exclude combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="768a3-111">결합된 기 하 도형 제외</span><span class="sxs-lookup"><span data-stu-id="768a3-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="768a3-112">다음 태그에서는 <xref:System.Windows.Media.CombinedGeometry> 의 결합 모드를 사용 하 여 정의 `Intersect`합니다.</span><span class="sxs-lookup"><span data-stu-id="768a3-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="768a3-113">둘 다 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 원 반지름 하지만 센터 오프셋으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="768a3-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="768a3-114">![결과 Intersect 결합 모드](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="768a3-114">![Results of the Intersect combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="768a3-115">Intersect 결합된 기 하 도형</span><span class="sxs-lookup"><span data-stu-id="768a3-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="768a3-116">다음 태그에서는 <xref:System.Windows.Media.CombinedGeometry> 의 결합 모드를 사용 하 여 정의 `Union`합니다.</span><span class="sxs-lookup"><span data-stu-id="768a3-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="768a3-117">둘 다 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 원 반지름 하지만 센터 오프셋으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="768a3-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="768a3-118">![Union 결합 모드의 결과](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="768a3-118">![Results of the Union combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="768a3-119">결합 된 Geometry 합집합</span><span class="sxs-lookup"><span data-stu-id="768a3-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="768a3-120">다음 태그에서는 <xref:System.Windows.Media.CombinedGeometry> 의 결합 모드를 사용 하 여 정의 `Xor`합니다.</span><span class="sxs-lookup"><span data-stu-id="768a3-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="768a3-121">둘 다 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 원 반지름 하지만 센터 오프셋으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="768a3-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="768a3-122">![Xor 결합 모드의 결과](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="768a3-122">![Results of the Xor combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="768a3-123">Xor 결합된 기 하 도형</span><span class="sxs-lookup"><span data-stu-id="768a3-123">Combined Geometry Xor</span></span>
