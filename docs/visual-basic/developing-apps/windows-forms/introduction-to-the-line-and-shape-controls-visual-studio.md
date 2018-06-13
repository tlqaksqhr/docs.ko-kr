---
title: Line 및 Shape 컨트롤 소개(Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- Line control [Visual Basic], overview
- Shape control [Visual Basic], overview
- lines, drawing
- shapes, drawing
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
ms.openlocfilehash: 3ad740f7dd15194830959a5493970b4ba54ce142
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590740"
---
# <a name="introduction-to-the-line-and-shape-controls-visual-studio"></a>Line 및 Shape 컨트롤 소개(Visual Studio)
Visual Basic Power Packs Line 및 Shape 컨트롤은 폼과 컨테이너에서 선 및 모양 그리기 수 있도록 하는 세 가지 그래픽 컨트롤의 집합입니다. <xref:Microsoft.VisualBasic.PowerPacks.LineShape> 컨트롤 가로, 세로, 및 대각선를 그리는 데 사용 됩니다. <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 컨트롤을 원 및 타원, 사용 및 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 컨트롤 사각형 및 정사각형을 그리는 데 사용 됩니다.  
  
## <a name="line-and-shape-controls"></a>Line 및 Shape 컨트롤  
 Line 및 Shape 컨트롤을 캡슐화 하는에 포함 된 그래픽 방법은 <xref:System.Drawing> 네임 스페이스입니다. 그러면 그래픽 개체, 펜 및 브러시를 만들 필요 없이 한 번에 선 및 모양 그리기 수 있습니다. 그라데이션 채우기와 같은 복잡 한 그래픽 기술은 일부 속성을 설정 하 여 수행할 수 있습니다.  
  
 그래픽 메서드를 사용 하 여 선과 도형 그리기 수도 있지만 Line 및 Shape 컨트롤을 사용 하 여 여러 가지 이점이 있습니다.  
  
-   런타임 시 그래픽 메서드를 호출할 수 있습니다. Line 및 Shape 컨트롤 디자인 타임에 폼에 추가할 수 있습니다. 이 통해 모양을 확인 하 고 정확 하 게; 배치할 수 있습니다. 또한 런타임 시 추가할 수도 있습니다.  
  
-   Line 및 Shape 컨트롤은 선택할 수 있는 런타임 시 이벤트와 같은 제공 <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> 및 <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>합니다. 그래픽 메서드의 출력 선택 가능한 되지 않으며 이벤트를 제공 하지 않습니다.  
  
-   Line 및 Shape 컨트롤 제공 <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A> 및 <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A> 디자인 타임 및 런타임 시 z 순서를 제어할 수 있도록 하는 방법입니다. 런타임 시 실행 순서를 변경한 경우에 그래픽 방법의 z 순서를 제어할 수 있습니다.  
  
-   Line 및 Shape 컨트롤은 창 없는 컨트롤입니다. 창 핸들이 하며 따라서 적은 시스템 리소스를 사용 합니다.  
  
### <a name="object-model"></a>개체 모델  
 Line 및 Shape 컨트롤 기본에서 파생 <xref:Microsoft.VisualBasic.PowerPacks.Shape> 자신의 공유 속성, 메서드 및 이벤트를 정의 하는 클래스입니다.  
  
 다음 그림은 Line 및 Shape 개체 계층 구조를 보여 줍니다.  
  
 ![Line 및 Shape 개체 계층 구조의 다이어그램](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Line 및 Shape 개체 계층 구조  
  
 파생 된 <xref:Microsoft.VisualBasic.PowerPacks.LineShape> 클래스 속성, 메서드 및 동일한 줄으로 고유한 이벤트를 포함 합니다. 파생 된 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> 클래스는 기본 클래스에 대 한 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 및 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; 속성, 메서드 및 이벤트 모든 셰이프에 공통적인 것을 포함 합니다. 또한에서 파생 시켜 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> 직접 만들 `Shape` 컨트롤입니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 및 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 클래스 원, 타원, 사각형 및 모퉁이가 둥근 사각형을 그리는 데 사용할 수 있습니다.  
  
 선 또는 모양 컨트롤이 폼 이나 컨테이너, 면 보이지 않는에 추가 되는 면 <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> 개체가 만들어집니다. <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> 각 컨테이너 컨트롤 내의 셰이프에 대 한 캔버스의 역할, 각 <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> 는 해당 <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection> Line 및 Shape 컨트롤을 반복할 수 있습니다. 끌어서 놓는 방법 또는 잘라내기 / 붙여넣기를 사용 하 여 다른 한 컨테이너의 셰이프를 이동할 수 있습니다. 마지막 셰이프는 컨테이너에서 제거 되 고 <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> 도 제거 됩니다.  
  
> [!NOTE]
>  일부 컨테이너 컨트롤 Line 및 Shape 컨트롤을 지원합니다. 선 또는 모양 컨트롤에서 호스트할 수 없습니다는 <xref:System.Windows.Forms.TableLayoutPanel> 또는 <xref:System.Windows.Forms.FlowLayoutPanel>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks>  
 [방법: LineShape 컨트롤로 선 그리기](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [방법: OvalShape 및 RectangleShape 컨트롤을 사용하여 도형 그리기](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [방법: 도형 간 탭 이동 사용](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)
