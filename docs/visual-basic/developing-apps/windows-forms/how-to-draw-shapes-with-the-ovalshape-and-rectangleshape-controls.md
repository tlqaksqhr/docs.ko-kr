---
title: "방법: OvalShape 및 RectangleShape 컨트롤을 사용하여 도형 그리기(Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OvalShape control [Visual Basic]
- shapes, drawing
- RectangleShape control [Visual Basic]
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53d91d10cc4735bbae521d17d05045cc7ea75fbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls-visual-studio"></a>방법: OvalShape 및 RectangleShape 컨트롤을 사용하여 도형 그리기(Visual Studio)
<xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 컨트롤을 사용하여 디자인 타임과 런타임에 폼이나 컨테이너에서 원 또는 타원을 그릴 수 있습니다. <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 컨트롤을 사용하면 폼이나 컨테이너에서 정사각형, 직사각형 또는 모서리가 둥근 직사각형을 그릴 수 있습니다. 이 컨트롤을 사용하여 디자인 타임 및 런타임에 도형을 그릴 수도 있습니다.  
  
 테두리 너비, 색 및 스타일을 변경하여 도형의 모양을 사용자 지정할 수 있습니다. 도형의 배경은 기본적으로 투명합니다. 단색, 패턴, 그라데이션 채우기(색 간 전환) 또는 이미지를 표시하도록 배경을 사용자 지정할 수 있습니다.  
  
### <a name="to-draw-a-simple-shape-at-design-time"></a>디자인 타임에 간단한 도형을 그리려면  
  
1.  끌어서는 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 또는 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 에서 제어는 **Visual Basic PowerPacks** 탭 (참조를 설치 하려면 [Visual Basic Power Packs 컨트롤](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md))에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.  
  
2.  크기 조정 및 이동 핸들을 끌어 도형의 크기와 위치를 조정합니다.  
  
     크기 조정 하 고 변경 하 여 셰이프를 배치할 수도 있습니다는 `Size` 및 `Position` 속성에는 **속성** 창.  
  
     모퉁이가 둥근 사각형을 만들려면 선택는 `CornerRadius` 속성에는 **속성** 창이 0 보다 큰 값으로 설정 합니다.  
  
3.  에 **속성** 창에서 필요에 따라 추가 속성을 설정 하 여 도형의 모양을 변경 합니다.  
  
### <a name="to-draw-a-simple-shape-at-run-time"></a>런타임에 간단한 도형을 그리려면  
  
1.  **프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.  
  
2.  에 **참조 추가** 대화 상자에서 **Microsoft.VisualBasic.PowerPacks.VS**, 클릭 하 고 **확인**합니다.  
  
3.  에 **코드 편집기**, 추가 `Imports` 또는 `using` 모듈 맨 위에 있는 문:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  `Event` 프로시저에 다음 코드를 추가합니다.  
  
     [!code-csharp[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## <a name="customizing-shapes"></a>도형 사용자 지정  
 기본 설정을 사용하는 경우 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 및 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 컨트롤은 너비가 1픽셀이고 배경이 투명한 검은색 실선 테두리로 표시됩니다. 속성을 설정하여 테두리의 너비, 스타일 및 색을 변경할 수 있습니다. 추가 속성을 사용하면 도형의 배경을 단색, 패턴, 그라데이션 채우기 또는 이미지로 변경할 수 있습니다.  
  
 도형의 배경색을 변경하기 전에 여러 속성이 상호 작용하는 방법을 파악해야 합니다.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A>로 설정되어 있지 않으면 <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque> 속성 설정을 사용해도 아무 효과가 없습니다.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>로 설정되어 있으면 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>는 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>를 재정의합니다.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> 또는 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>과 같은 패턴 값으로 설정되어 있으면 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>에 해당 패턴이 표시됩니다. <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A>로 설정되어 있으면 배경은 <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>로 표시됩니다.  
  
-   그라데이션 채우기를 표시하려면 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> 속성을 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>로 설정해야 하며 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> 속성은 <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None> 이외의 값으로 설정해야 합니다.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> 속성을 이미지로 설정하면 다른 모든 배경 설정이 재정의됩니다.  
  
#### <a name="to-draw-a-circle-that-has-a-custom-border"></a>사용자 지정 테두리가 있는 원을 그리려면  
  
1.  끌어서는 `OvalShape` 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.  
  
2.  에 **속성** 창에는 `Size` 속성을 설정 `Height` 및 `Width` 를 같은 값입니다.  
  
3.  `BorderColor` 속성을 원하는 색으로 설정합니다.  
  
4.  `BorderStyle` 속성을 `Solid` 이외의 값으로 설정합니다.  
  
5.  `BorderWidth`를 픽셀 단위의 원하는 크기로 설정합니다.  
  
#### <a name="to-draw-a-circle-that-has-a-solid-fill"></a>단색 채우기가 적용된 원을 그리려면  
  
1.  끌어서는 `OvalShape` 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.  
  
2.  에 **속성** 창에는 `Size` 속성을 설정 `Height` 및 `Width` 를 같은 값입니다.  
  
3.  `BackColor` 속성을 원하는 색으로 설정합니다.  
  
4.  `BackStyle` 속성을 `Opaque`으로 설정합니다.  
  
#### <a name="to-draw-a-circle-that-has-a-patterned-fill"></a>무늬가 적용된 원을 그리려면  
  
1.  끌어서는 `OvalShape` 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.  
  
2.  에 **속성** 창에는 `Size` 속성을 설정 `Height` 및 `Width` 를 같은 값입니다.  
  
3.  `BackColor` 속성을 배경에 사용할 색으로 설정합니다.  
  
4.  `BackStyle` 속성을 `Opaque`으로 설정합니다.  
  
5.  `FillColor` 속성을 무늬에 사용할 색으로 설정합니다.  
  
6.  `FillStyle` 속성을 `Transparent` 또는 `Solid` 이외의 값으로 설정합니다.  
  
#### <a name="to-draw-a-circle-that-has-a-gradient-fill"></a>그라데이션 채우기가 적용된 원을 그리려면  
  
1.  끌어서는 `OvalShape` 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.  
  
2.  에 **속성** 창에는 `Size` 속성을 설정 `Height` 및 `Width` 를 같은 값입니다.  
  
3.  `FillColor` 속성을 시작 색으로 사용할 색으로 설정합니다.  
  
4.  `FillGradientColor` 속성을 종료 색으로 사용할 색으로 설정합니다.  
  
5.  `FillGradientStyle` 속성을 `None` 이외의 값으로 설정합니다.  
  
#### <a name="to-draw-a-circle-that-is-filled-with-an-image"></a>이미지로 채워진 원을 그리려면  
  
1.  끌어서는 `OvalShape` 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.  
  
2.  에 **속성** 창에는 `Size` 속성을 설정 `Height` 및 `Width` 를 같은 값입니다.  
  
3.  선택 된 `BackgroundImage` 속성을 클릭은 **줄임표** 단추 (...).  
  
4.  에 **리소스 선택** 대화 상자를 표시할 이미지를 선택 합니다. 이미지 리소스가 표시 되 면 클릭 **가져오기** 이미지의 위치를 찾습니다.  
  
5.  클릭 **확인** 여 이미지를 삽입 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>  
 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>  
 [Line 및 Shape 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [방법: LineShape 컨트롤로 선 그리기](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
