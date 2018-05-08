---
title: '성능 최적화: 응용 프로그램 리소스'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
ms.openlocfilehash: 53e906f31f32fb0f1df3f8d986daa0ae95ea9e4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="optimizing-performance-application-resources"></a>성능 최적화: 응용 프로그램 리소스
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 비슷한 형식의 요소에서 일관성 있는 모양이 나 동작을 지원할 수 있도록 응용 프로그램 리소스를 공유할 수 있습니다. 이 항목에서는 몇 가지 권장 사항 수 있는이 영역에 응용 프로그램의 성능을 개선 합니다.  
  
 리소스에 대한 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하세요.  
  
## <a name="sharing-resources"></a>리소스 공유  
 응용 프로그램 사용자 지정 컨트롤을 사용 하 여 및에 리소스를 정의 하는 경우는 <xref:System.Windows.ResourceDictionary> (또는 XAML 리소스 노드)를 정의 하는 중 하나에 포함 된 리소스 것이 좋습니다.는 <xref:System.Windows.Application> 또는 <xref:System.Windows.Window> 수준 개체에 대 한 기본 테마에 정의할 수도 사용자 지정 컨트롤입니다. 사용자 지정 컨트롤에 리소스를 정의 <xref:System.Windows.ResourceDictionary> 해당 컨트롤의 모든 인스턴스에 대 한 성능에 영향을 적용 합니다. 예를 들어 사용자 지정 컨트롤의 여러 인스턴스 및 사용자 지정 컨트롤의 리소스 정의의 일부로 정의 된 성능이 브러시 작업을 사용 하도록 설정한 경우 응용 프로그램의 작업 집합이 크게 증가 합니다.  
  
 예를 들어, 다음 사항을 고려 합니다. 사용 하는 카드 게임을 개발 하는 경우를 가정해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다. 대부분의 카드 게임 52 카드와 해당 52 서로 다른 면에 필요합니다. 카드 사용자 지정 컨트롤을 구현 하도록 결정 하 고 카드 사용자 지정 컨트롤의 리소스에서 (각 카드 그림을 나타냄) 52 브러시를 정의 합니다. 주 응용 프로그램에서 처음이 카드 사용자 지정 컨트롤의 52 인스턴스를 만듭니다. 52 인스턴스를 생성 하는 카드 사용자 지정 컨트롤의 각 인스턴스에 <xref:System.Windows.Media.Brush> 52 * 52의 합계를 제공 하는 개체를 <xref:System.Windows.Media.Brush> 응용 프로그램의 개체입니다. 브러시에 카드 사용자 지정 제어 리소스를 이동 하 여는 <xref:System.Windows.Application> 또는 <xref:System.Windows.Window> 개체 수준 또는 사용자 지정 컨트롤에 대 한 기본 테마 파일에서 이제 52 브러시를 공유 하는 이후 응용 프로그램의 작업 집합을 줄이려면 52의 인스턴스에서 카드 컨트롤입니다.  
  
## <a name="sharing-a-brush-without-copying"></a>브러시를 복사 하지 않고 공유  
 동일한 여러 요소가 있을 경우 <xref:System.Windows.Media.Brush> 개체를 리소스로 브러시를 정의한 참조에서 브러시 인라인으로 정의 하지 않고, [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]합니다. 이 메서드는 하나의 인스턴스를 만들어 다시 사용에서 브러시 인라인으로 정의 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 각 요소에 대 한 새 인스턴스를 만듭니다.  
  
 다음 태그 샘플에는 이러한 점을 보여 줍니다.  
  
 [!code-xaml[Performance#PerformanceSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>가능한 경우 정적 리소스를 사용 하 여  
 정적 리소스는 이미 정의 된 리소스에 대 한 참조를 조회 하 여 모든 XAML 속성 특성에 대 한 값을 제공 합니다. 해당 리소스에 대 한 조회 동작 하는 것은 컴파일 타임 조회 비슷합니다.  
  
 동적 리소스 반면에 초기 컴파일하는 동안 임시 식을 만들고 때문 요청 된 리소스 값이 개체를 생성 하기 위해 실제로 필요할 때까지 리소스에 대 한 조회를 연기 합니다. 해당 리소스에 대 한 조회 동작 하면 성능에 영향을 부과 런타임에 조회를와 비슷합니다. 필요한 경우에 동적 리소스를 사용 하 여 응용 프로그램에서 가능한 경우 항상 정적 리소스를 사용 합니다.  
  
 다음 태그 샘플 두 유형의 리소스 사용을 보여 줍니다.  
  
 [!code-xaml[Performance#PerformanceSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a>참고 항목  
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [응용 프로그램 성능 계획](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [하드웨어 이용](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
