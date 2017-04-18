---
title: "경로 태그 구문 | Microsoft Docs"
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
  - "PathGeometry 클래스"
  - "XAML의 특성 사용"
  - "XAML 특성 사용"
  - "PathGeometry 클래스"
  - "그래픽, PathGeometry 클래스"
  - "XAML 개체 요소 사용"
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# 경로 태그 구문
그러나 경로에 대해서는 [셰이프 및 WPF 개요에서 기본 그리기](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md) 및 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md),이 항목에서는 설명 자세히 경로 기 하 도형 더 조밀 하 게 사용 하 여 지정 하는 데 사용할 수는 강력 하 고 복잡 한 미니 언어 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.  
  
 이 항목에는 다음과 같은 섹션이 포함되어 있습니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목을 이해 하려면의 기본 기능에 잘 알고 있어야 <xref:System.Windows.Media.Geometry> 개체입니다. 자세한 내용은 참조는 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)합니다.  
  
<a name="abouthisdocument"></a>   
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>StreamGeometry 및 PathFigureCollection 미니 언어  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기하학적 경로 설명 하는 데 미니 언어를 제공 하는 두 개의 클래스를 제공 합니다. <xref:System.Windows.Media.StreamGeometry> 및 <xref:System.Windows.Media.PathFigureCollection>합니다.  
  
-   사용 하면는 <xref:System.Windows.Media.StreamGeometry> 미니 언어 형식의 속성을 설정할 때 <xref:System.Windows.Media.Geometry>와 같은 <xref:System.Windows.UIElement.Clip%2A> 속성은 <xref:System.Windows.UIElement> 또는 <xref:System.Windows.Shapes.Path.Data%2A> 속성은 <xref:System.Windows.Shapes.Path> 요소입니다. 다음 예제에서는 특성 구문을 사용 하 여 한 <xref:System.Windows.Media.StreamGeometry>합니다.  
  
     [!code-xml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
-   사용 하면는 <xref:System.Windows.Media.PathFigureCollection> 설정할 때 미니 언어는 <xref:System.Windows.Media.PathGeometry.Figures%2A> 속성은 <xref:System.Windows.Media.PathGeometry>합니다. 다음 예제는 특성 구문을 사용 하 여 한 <xref:System.Windows.Media.PathFigureCollection> 에 대 한 한 <xref:System.Windows.Media.PathGeometry>합니다.  
  
     [!code-xml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 앞의 예제에서 볼 수 있습니다, 두 개의 미니 언어는 매우 비슷합니다. 사용할 수는 항상는 <xref:System.Windows.Media.PathGeometry> 사용할 수 있는 경우에는 <xref:System.Windows.Media.StreamGeometry>따라서; 어느 사용 해야 하는? 사용 하 여는 <xref:System.Windows.Media.StreamGeometry> ; 만든 후 경로 수정 하려면 필요 하지 않은 경우 사용 된 <xref:System.Windows.Media.PathGeometry> 경로 수정 해야 하는 경우.  
  
 간의 차이점에 대 한 자세한 내용은 <xref:System.Windows.Media.PathGeometry> 및 <xref:System.Windows.Media.StreamGeometry> 개체 참조는 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)합니다.  
  
### <a name="a-note-about-white-space"></a>공백에 대 한 참고  
 간단 하 게 단일 공간, 이어지는 구문 섹션에 나와 있지만 여러 개의 공간 단일 공백으로 표시 되는 경우에 허용 됩니다.  
  
 두 숫자를 쉼표 또는 공백 구분 않아도 실제로 있지만이 방법은 수만 경우 결과 문자열은 모호 하지 않습니다. 예를 들어, `2..3` 은 실제로: "2"로 지정 합니다. 및 ".&3;"입니다. 마찬가지로, `2-3` 은 "2"와 "-3"입니다. 공백이 필요 하지 않은 하기 전이나 후 명령 중 하나입니다.  
  
### <a name="syntax"></a>구문  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 사용 구문에 대 한 특성을 <xref:System.Windows.Media.StreamGeometry> 는 선택적 구성 <xref:System.Windows.Media.FillRule> 값 및 하나 이상의 그림 설명 합니다.  
  
|StreamGeometry XAML 특성 사용|  
|-----------------------------------------|  
|`<`*object* *property* `="`[                                         `fillRule`]                                          `figureDescription`[                                         `figureDescription`]*`" ... />`|  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 사용 구문에 대 한 특성을 <xref:System.Windows.Media.PathFigureCollection> 하나 이상의 그림 설명으로 구성 됩니다.  
  
|PathFigureCollection XAML 특성 사용|  
|-----------------------------------------------|  
|`<`*object* *property* `="` `figureDescription`[                                         `figureDescription`]*`" ... />`|  
  
|용어|설명|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=fullName><br /><br /> 지정 여부는 <xref:System.Windows.Media.StreamGeometry> 사용 하는 <xref:System.Windows.Media.FillRule> 또는 <xref:System.Windows.Media.FillRule><xref:System.Windows.Media.PathGeometry.FillRule%2A>합니다.<br /><br /> -   `F0`지정 된 <xref:System.Windows.Media.FillRule> 채우기 규칙입니다.<br />-   `F1`지정 된 <xref:System.Windows.Media.FillRule> 채우기 규칙입니다.<br /><br /> 하위 경로 기본 동작을 사용 하 여이 명령을 생략 하면 <xref:System.Windows.Media.FillRule>합니다. 이 명령을 지정 하려면, 먼저 배치 해야 있습니다.|  
|*figureDescription*|이동 명령, 이루어져 그림 그리기 명령 및 선택적 닫기 명령입니다.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|그림의 시작점을 지정 하는 이동 명령 참조는 [이동 명령을](#themovecommand) 섹션입니다.|  
|*drawCommands*|그림의 내용을 설명 하는 하나 이상의 그리기 명령입니다. 참조는 [그리기 명령](#drawcommands) 섹션입니다.|  
|*closeCommand*|그림을 닫는 선택적 닫기 명령입니다. 참조는 [닫기 명령을](#closecommand) 섹션입니다.|  
  
<a name="themovecommand"></a>   
## <a name="move-command"></a>이동 명령  
 새 그림의 시작점을 지정합니다.  
  
|구문|  
|------------|  
|`M`*시작점*<br /><br /> 또는<br /><br /> `m`*시작점*|  
  
|용어|설명|  
|----------|-----------------|  
|*시작점*|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> 새 그림의 시작점입니다.|  
  
 대문자 `M` 나타내는 `startPoint` 절대값; 인지 소문자 `m` 함을 나타냅니다 `startPoint` 이전 지점에 대 한 오프셋은 또는 (0,&0;) 존재 하지 않을 경우. 이동 명령 뒤에 여러 요소를 열거 하는 경우 줄 명령을 지정 했지만 해당 지점으로 선이 그려집니다.  
  
<a name="drawcommands"></a>   
## <a name="draw-commands"></a>그리기 명령  
 그리기 명령은 여러 도형 명령으로 구성 될 수 있습니다. 다음 셰이프 명령을 사용할 수 있습니다: 선, 가로줄, 세로줄, 입방 형&3; 차원 곡선, 이차 베 지 어 곡선, 부드러운 입방 형&3; 차원 곡선, 부드러운 정방형&3; 차원 곡선 및 타원형 원호 합니다.  
  
 대문자 또는 소문자를 사용 하 여 각 명령을 입력: 대문자 절대 값을 표시 하 고 소문자 대문자나: 해당 세그먼트에 대 한 제어 지점을 위 예의 기준으로 합니다. 둘 이상의 명령이 동일한 유형의 순차적으로 입력할 때 중복 되는 명령 entry; 생략할 수 있습니다. 예를 들어 `L 100,200 300,400` 같습니다 `L 100,200 L 300,400`합니다. 다음 표에 **이동** 및 **그리기** 명령입니다.  
  
### <a name="line-command"></a>명령줄  
 현재 요소와 지정 된 끝점 간의 직선을 만듭니다.                           `l 20 30`및 `L 20,30` 유효한의 예는 **줄** 명령입니다.  
  
|구문|  
|------------|  
|`L`*끝점*<br /><br /> 또는<br /><br /> `l`*끝점*|  
  
|용어|설명|  
|----------|-----------------|  
|*끝점*|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> 선의 끝점입니다.|  
  
### <a name="horizontal-line-command"></a>가로줄 명령  
 지정한 x 좌표와 현재 지점과 가로줄을 만듭니다.                          `H 90`유효한 가로줄 명령의 예입니다.  
  
|구문|  
|------------|  
|`H`  *x*<br /><br /> 또는<br /><br /> `h`  *x*|  
  
|용어|설명|  
|----------|-----------------|  
|*x*|<xref:System.Double?displayProperty=fullName><br /><br /> 선의 끝점에 대 한 x 좌표입니다.|  
  
### <a name="vertical-line-command"></a>세로 선 명령  
 현재 요소와 지정 된 y-좌표 간의 세로 선을 만듭니다.                          `v 90`유효한 세로줄 명령의 예입니다.  
  
|구문|  
|------------|  
|`V`  *y*<br /><br /> 또는<br /><br /> `v`  *y*|  
  
|용어|설명|  
|----------|-----------------|  
|*y*|<xref:System.Double?displayProperty=fullName><br /><br /> 선의 끝점에 대 한 y 좌표입니다.|  
  
### <a name="cubic-bezier-curve-command"></a>입방 형&3; 차원 곡선 명령  
 지정한 두 개의 제어점을 사용 하 여 현재 요소와 지정 된 끝점 간의 입방 형&3; 차원 곡선을 만듭니다 ( `controlPoint`1 및 `controlPoint`2).                          `C 100,200 200,400 300,200`유효한 곡선 명령의 예입니다.  
  
|구문|  
|------------|  
|`C` `controlPoint`1`controlPoint`2`endPoint`<br /><br /> 또는<br /><br /> `c` `controlPoint`1`controlPoint`2`endPoint`|  
  
|용어|설명|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> 시작 곡선의 접선을 결정 하는 곡선의 첫째 제어점|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> 곡선의 끝 접선을 결정 하는 곡선의 둘째 제어점|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> 곡선을 그릴 지점입니다.|  
  
### <a name="quadratic-bezier-curve-command"></a>정방형&3; 차원 곡선 명령  
 지정한 제어점을 사용 하 여 현재 요소와 지정 된 끝점 간의 정방형 베 지 어 곡선을 만듭니다 ( `controlPoint`).                          `q 100,200 300,200`유효한 정방형 베 지 어 곡선 명령의 예입니다.  
  
|구문|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> 또는<br /><br /> `q` `controlPoint` `endPoint`|  
  
|용어|설명|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> 시작 및 끝 곡선의 접선을 결정 하는 곡선의 제어점입니다.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> 곡선을 그릴 지점입니다.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>부드러운 입방 형&3; 차원 곡선 명령  
 현재 요소와 지정 된 끝점 간의 입방 형&3; 차원 곡선을 만듭니다. 첫 번째는 현재 시점을 기준으로 이전 명령의 두 번째 제어 지점으로 반영으로 간주 됩니다. 이전 명령이 또는 이전 명령이 입방 형&3; 차원 곡선 명령 또는 부드러운 입방 형&3; 차원 곡선 명령이 없는 경우에 첫 번째 시작 하는 현재 지점과 일치를 가정 합니다. 두 번째 제어점, 곡선의 끝에 대 한 제어 지점으로 지정 됩니다 `controlPoint`2입니다. 예를 들어 `S 100,200 200,300` 은 유효한 부드러운 입방 형 3 차원 곡선 명령입니다.  
  
|구문|  
|------------|  
|`S` `controlPoint`2`endPoint`<br /><br /> 또는<br /><br /> `s` `controlPoint`2`endPoint`|  
  
|용어|설명|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> 곡선의 끝 접선을 결정 하는 곡선의 제어점입니다.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> 곡선을 그릴 지점입니다.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>부드러운 정방형 베 지 어 곡선 명령  
 현재 요소와 지정 된 끝점 간의 정방형 베 지 어 곡선을 만듭니다. 현재 시점을 기준으로 이전 명령의 제어 지점으로 반영 제어점 가정 합니다. 이전 명령이 시작 이전 명령이 정방형 베 지 어 곡선 명령 또는 부드러운 정방형 베 지 어 곡선 명령 하지 않았으면 현재 지점과 일치 하는 경우.  
  
|구문|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> 또는<br /><br /> `t` `controlPoint` `endPoint`|  
  
|용어|설명|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> 시작 및 곡선의 접선을 결정 하는 곡선의 제어점입니다.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> 곡선을 그릴 지점입니다.|  
  
### <a name="elliptical-arc-command"></a>타원형 원호 명령  
 현재 요소와 지정 된 끝점 간의 타원형 원호를 만듭니다.  
  
|구문|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> 또는<br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
|용어|설명|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=fullName><br /><br /> 원호의 X 및 y 반지름입니다.|  
|`rotationAngle`|<xref:System.Double?displayProperty=fullName><br /><br /> 각도 타원의 회전입니다.|  
|`isLargeArcFlag`|호의 각도 180도 해야 하는 경우 1로 설정 큰; 그렇지 않으면 0으로 설정 합니다.|  
|`sweepDirectionFlag`|양의 각도 방향의 호가 그려지는 경우 1로 설정 그렇지 않으면 0으로 설정 합니다.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> 호를 그리는 점입니다.|  
  
<a name="closecommand"></a>   
## <a name="the-close-command"></a>닫기 명령  
 현재 그림을 끝내 고 현재 지점을 그림의 시작 지점에 연결 하는 선을 만듭니다. 이 명령은 마지막 세그먼트와 그림의 첫 번째 세그먼트 사이 선 조인 (위)를 만듭니다.  
  
|구문|  
|------------|  
|`Z`<br /><br /> 또는<br /><br /> `z`|  
  
<a name="pointsyntax"></a>   
## <a name="point-syntax"></a>점 구문  
 점의 x 및 y 좌표를 설명합니다.  
  
|구문|  
|------------|  
|`x` `,` `y`<br /><br /> 또는<br /><br /> `x` `y`|  
  
|용어|설명|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=fullName><br /><br /> 점의 x 좌표입니다.|  
|`y`|<xref:System.Double?displayProperty=fullName><br /><br /> 점의 y 좌표입니다.|  
  
<a name="specialvalues"></a>   
## <a name="special-values"></a>특수 값  
 표준 숫자 값을 대신 다음과 같은 특수 값도 사용할 수 있습니다. 이러한 값 대/소문자를 구분 하지 않습니다.  
  
 Infinity  
 나타냅니다 <xref:System.Double.PositiveInfinity?displayProperty=fullName>합니다.  
  
 -Infinity  
 나타냅니다 <xref:System.Double.NegativeInfinity?displayProperty=fullName>합니다.  
  
 NaN  
 나타냅니다 <xref:System.Double.NaN?displayProperty=fullName>합니다.  
  
 과학적 표기법을 사용할 수도 있습니다. 예를 들어 `+1.e17` 은 유효한 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.StreamGeometry>   
 <xref:System.Windows.Media.PathGeometry>   
 <xref:System.Windows.Media.PathFigureCollection>   
 [모양 및 WPF 개요에서 기본 그리기](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [방법 도움말 항목](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)