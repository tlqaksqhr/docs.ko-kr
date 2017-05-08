---
title: "방법: 복합 도형의 채우기 제어 | Microsoft Docs"
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
  - "채우기 제어 복합 도형"
  - "복합 도형 채우기 제어"
  - "복합 도형 그래픽 [WPF]"
  - "채우기 제어"
ms.assetid: c1c94575-9eca-48a5-a49a-2ec65259f229
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 복합 도형의 채우기 제어
<xref:System.Windows.Media.GeometryGroup.FillRule%2A> 의 속성을 <xref:System.Windows.Media.GeometryGroup> 또는 <xref:System.Windows.Media.PathGeometry>, 복합 도형이 지정된 된 지점 기 하 도형의 일부 인지 확인 하기 위해 사용 하 여 "규칙"을 지정 합니다. 에 대 한 두 개의 가능한 값은 <xref:System.Windows.Media.FillRule>: <xref:System.Windows.Media.FillRule> 및 <xref:System.Windows.Media.FillRule>합니다. 다음 섹션에는이 두 가지 규칙을 사용 하는 방법을 설명 합니다.  
  
 **EvenOdd:** 이 규칙 해당 지점에서 어느 방향으로 무한대로 광선을 그린 광선이 교차 하는 지정된 된 도형 내 경로 세그먼트의 수를 계산 하 여 채우기 영역에는 점이 인지 여부를 결정 합니다. 이 숫자가 홀수이면 점이 안에 있고, 짝수이면 밖에 있습니다.  
  
 예를 들어와 일련 동심원 (대상)의 구성 된 복합 도형 만듭니다를 다음 XAML을 <xref:System.Windows.Media.GeometryGroup.FillRule%2A> 로 설정 <xref:System.Windows.Media.FillRule>합니다.  
  
 [!code-xml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]  
  
 다음 그림에서는 이전 예제에서 만든 셰이프를 보여 줍니다.  
  
 ![스크린 샷: EvenOdd의 FillRule 속성](../../../../docs/framework/wpf/graphics-multimedia/media/fillruleevenoddfirstone.png "FillRuleEvenOddFirstOne")  
  
 위의 그림에서 보면 중심 및 세 번째 원이 채워져 있지 됩니다. 이 중 한 두 원 내의 모든 지점에서 가져온 광선 세그먼트 수가 짝수인 통과 때문입니다. 다음 그림을 참조 하십시오.  
  
 ![다이어그램: EvenOdd의 FillRule 속성 값](../../../../docs/framework/wpf/graphics-multimedia/media/fillruleevenodd2.png "FillRuleEvenOdd2")  
  
 **0이 아니면:** 이 규칙 해당 지점에서 어느 방향으로 무한대로 광선을 그린 다음 도형의 세그먼트가 광선과 교차 하는 위치를 검토 하 여 경로의 채우기 영역에는 점이 인지 여부를 결정 합니다. 부터 시작 하 여&0; 일 경우 추가할 각 세그먼트에서 왼쪽에서 오른쪽 빼면 각 교차할 때마다 시간 경로 세그먼트 오른쪽에서 왼쪽으로 광선과 교차 합니다. 교차 수를 계산한 후 결과가&0;이면 점이 경로의 밖에 있습니다. 그렇지 않으면 점이 내부에 있습니다.  
  
 [!code-xml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]  
  
 값이 위 예제를 사용 하 여 <xref:System.Windows.Media.FillRule> 에 대 한 <xref:System.Windows.Media.GeometryGroup.FillRule%2A> 결과적으로 다음 그림을 제공 합니다.  
  
 ![스크린 샷: NonZero의 FillRule 값](../../../../docs/framework/wpf/graphics-multimedia/media/fillrulenonzero1.png "FillRuleNonZero1")  
  
 여기에서 볼 수 있듯이 모든 링 채워집니다. 이 모든 세그먼트 같은 방향으로 실행 되므로 어느 시점에서 그린 광선이 교차 하나 또는 이상의 세그먼트와를 센의 합계가&0;이 아닌 됩니다. 예를 들어 아래 그림에 빨간색 화살표는 세그먼트가 그려지는 방향 나타내고 흰색 화살표는 가장 안쪽 원의 지점에서 실행 중인 임의의 광선을 나타냅니다. 값은&1; 광선이 교차 하는 각 세그먼트에 대해&0; 값으로 시작 세그먼트 교차할 왼쪽에서 오른쪽으로 하기 때문에 추가 됩니다.  
  
 ![다이어그램: FillRule 속성 값 NonZero와 같은](../../../../docs/framework/wpf/graphics-multimedia/media/fillrulenonzero2.png "FillRuleNonZero2")  
  
 더 잘의 동작을 설명 하기 위해 <xref:System.Windows.Media.FillRule> 서로 다른 방향에서 실행 되는 세그먼트와 함께 보다 복잡 한 셰이프 규칙은 필수입니다. XAML 코드와 한다는 점을 제외 하면 앞의 예제와 비슷한 도형을 만들고는 <xref:System.Windows.Media.PathGeometry> 대신는 <xref:System.Windows.Media.EllipseGeometry> 동심원을 완전히 닫힐 대신를 만듭니다.  
  
 [!code-xml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]  
  
 다음 그림에서는 이전 예제에서 만든 셰이프를 보여 줍니다.  
  
 ![스크린 샷: NonZero의 FillRule 속성 값](../../../../docs/framework/wpf/graphics-multimedia/media/fillrulenonzero3.png "FillRuleNonZero3")  
  
 알림 센터에서 세 번째 호 채워지지 않습니다. 다음 그림에서는 그 이유를 보여 줍니다. 그림에서 빨간색 화살표는 세그먼트를 그리는 방향을 나타냅니다. 두 개의 흰색 화살표는 채워지지 않은 "지역에서 지점 이동 하는 두 개의 임의 방사선을 나타냅니다. 그림에서 볼 수 있듯이 해당 경로에서 세그먼트를 넘나드는 특정 광선이 값의 합은&0;입니다. 앞에서 정의한 대로 합계가&0; 지점 하지 않음을 geometry (채우기의 일부가 아님)의 일부를 합 하는 동안 *하지*&0;을, 음수 값을 포함 하는 기 하 도형의 일부입니다.  
  
 ![다이어그램: NonZero의 FillRule 속성 값](../../../../docs/framework/wpf/graphics-multimedia/media/fillrulenonzero4.png "FillRuleNonZero4")  
  
 **참고:** 위해 <xref:System.Windows.Media.FillRule>, 모든 셰이프는 닫혀 있다고 간주 됩니다. 세그먼트에 간격이 있으면 닫습니다 허수 선을 그립니다. 위의 예에서 링에 작은 차이가 있습니다. 이 점을 고려 하나 광선 결과가 다를 통과 하는 다음 다른 방향으로 광선 예상할 수 있습니다. 아래 이러한 간격과 "허수 세그먼트" 중 하나의 확대 설명 하는 (적용 하기 위해 그려지는 세그먼트는 <xref:System.Windows.Media.FillRule>)를 닫습니다.  
  
 ![다이어그램: Fillrule의 경우 세그먼트가 항상 닫힘](../../../../docs/framework/wpf/graphics-multimedia/media/fillruleclosedshapes.png "FillRuleClosedShapes")  
  
## <a name="example"></a>예제  
  
## <a name="see-also"></a>참고 항목  
 [복합 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)   
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)