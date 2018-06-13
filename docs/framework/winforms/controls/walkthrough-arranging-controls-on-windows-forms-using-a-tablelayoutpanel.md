---
title: '연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: 6b98495fb967b7f3b5885f940c348b5cba33cb18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541822"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬
일부 응용 프로그램에는 폼 크기가 조정되거나 내용의 크기가 변경될 때 적절하게 정렬되는 레이아웃을 가진 폼이 필요합니다. 동적 레이아웃이 필요하며 코드에서 명시적으로 <xref:System.Windows.Forms.Control.Layout> 이벤트를 처리하지 않으려는 경우 레이아웃 패널을 사용하는 것이 좋습니다.  
  
 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤 및 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 폼에서 컨트롤을 정렬하는 직관적인 방법을 제공합니다. 둘 다 포함된 자식 컨트롤의 상대 위치를 제어하는 구성 가능한 자동 기능을 제공하며, 둘 다 런타임에 동적 레이아웃 기능을 제공하므로 부모 폼의 크기가 변경될 때 자식 컨트롤의 크기를 조정하고 위치를 변경할 수 있습니다. 레이아웃 패널을 레이아웃 패널 내에 중첩하여 정교한 사용자 인터페이스를 구현할 수 있습니다.  
  
 <xref:System.Windows.Forms.FlowLayoutPanel> 은 특정 흐름 방향(수평 또는 수직)으로 내용을 정렬합니다. 컨트롤 내용을 한 행에서 다음 행으로 또는 한 열에서 다음 열로 줄 바꿈할 수 있습니다. 또는 컨트롤 내용이 줄 바꿈되는 대신 잘릴 수 있습니다. 자세한 내용은 참조 [연습: Windows Forms 사용 하 여 FlowLayoutPanel에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)합니다.  
  
 <xref:System.Windows.Forms.TableLayoutPanel> html 유사한 기능을 제공 하는 눈금으로 내용을 정렬 \<테이블 > 요소입니다. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 정확 하 게 각 개별 컨트롤의 위치를 지정할 필요 없이 사용 하면 모눈 레이아웃에 컨트롤을 배치할 수 있습니다. 해당 셀은 행과 열로 정렬되며 크기가 서로 다를 수 있습니다. 행 및 열에서 셀을 병합할 수 있습니다. 셀 폼을 포함 하 고 컨테이너로 다른 측면에서 작동 하는 모든 항목을 포함할 수 있습니다.  
  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 레이아웃 폼의 크기가 조정 원활 하 게 변경할 수 런타임 시 가변 크기 조정 기능도 제공 합니다. 이렇게 하면는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 등의 데이터 입력 폼 및 지역화 된 응용 프로그램에 적합 합니다. 자세한 내용은 참조 [연습: 데이터 항목에 대 한 크기 조정 가능한 Windows Form 만들기](http://msdn.microsoft.com/library/e193b4fc-912a-4917-b036-b76c7a6f58ab) 및 [연습: 지역화 가능한 Windows Form 만들기](http://msdn.microsoft.com/library/c5240b6e-aaca-4286-9bae-778a416edb9c)합니다.  
  
 사용 하지 해야 일반적으로 <xref:System.Windows.Forms.TableLayoutPanel> 전체 레이아웃에 대 한 컨테이너로 제어 합니다. 사용 하 여 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 레이아웃의 부분에 비례하여 크기 조정 기능을 제공 합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   Windows Forms 프로젝트 만들기  
  
-   행과 열에 컨트롤 정렬  
  
-   설정 행 및 열 속성  
  
-   행 및 열 컨트롤 확장  
  
-   자동 오버플로 처리  
  
-   도구 상자에서 두 번 클릭하여 컨트롤 삽입  
  
-   윤곽선을 그려 컨트롤 삽입  
  
-   다른 부모에 기존 컨트롤 다시 할당  
  
 작업을 완료하면 이러한 중요한 레이아웃 기능이 수행하는 역할을 이해하게 됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1.  "TableLayoutPanelExample" 이라는 Windows 응용 프로그램 프로젝트를 만듭니다. 자세한 내용은 참조 [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 합니다.  
  
2.  폼을 선택는 **Windows** **Forms 디자이너**합니다.  
  
## <a name="arranging-controls-in-rows-and-columns"></a>행과 열에 컨트롤 정렬  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용 하면 쉽게 행과 열으로 컨트롤을 정렬할 수 있습니다.  
  
#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>행 및 열 TableLayoutPanel을 사용 하 여 컨트롤을 정렬 하려면  
  
1.  끌어서는 <xref:System.Windows.Forms.TableLayoutPanel> 에서 제어는 **도구 상자** 폼으로 합니다. 이때 기본적으로는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 네 개의 셀입니다.  
  
2.  끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 에 <xref:System.Windows.Forms.TableLayoutPanel> 제어 셀 중 하나에 놓습니다. <xref:System.Windows.Forms.Button> 컨트롤이 선택한 셀 내에서 만들어집니다.  
  
3.  세 개의 추가 끌어 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 에 <xref:System.Windows.Forms.TableLayoutPanel> 각 셀에 단추가 포함 되어를 제어 합니다.  
  
4.  두 열 사이의 세로 크기 조정 핸들을 선택 하 고 왼쪽으로 이동 합니다. <xref:System.Windows.Forms.Button> 첫 번째 열에는 컨트롤의 크기 중 더 작은 너비 크기가 조정 되는 <xref:System.Windows.Forms.Button> 컨트롤 두 번째 열에는 변경 되지 않습니다.  
  
5.  두 열 사이의 세로 크기 조정 핸들을 선택 하 고 오른쪽으로 이동 합니다. <xref:System.Windows.Forms.Button> 를 원래 크기로, 첫 번째 열에 컨트롤을 반환 하는 동안는 <xref:System.Windows.Forms.Button> 오른쪽으로 두 번째 열에 컨트롤을 이동 합니다.  
  
6.  패널의 컨트롤에 미치는 영향을 위아래로 가로 크기 조정 핸들을 이동 합니다.  
  
## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>도킹 및 고정 기능을 사용 하 여 셀 내에서 컨트롤을 위치 지정  
 자식 컨트롤의 고정 동작은 <xref:System.Windows.Forms.TableLayoutPanel> 다른 컨테이너 컨트롤의 동작과에서 다릅니다. 자식 컨트롤의 도킹 동작 다른 컨테이너 컨트롤와 같습니다.  
  
#### <a name="positioning-controls-within-cells"></a>셀 내에서 컨트롤을 위치 지정  
  
1.  첫 번째 선택 <xref:System.Windows.Forms.Button> 제어 합니다. <xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle.Fill>로 변경합니다. <xref:System.Windows.Forms.Button> 컨트롤은 해당 셀에 맞게 확장 됩니다.  
  
2.  다른 중 하나를 선택 <xref:System.Windows.Forms.Button> 컨트롤입니다. <xref:System.Windows.Forms.Control.Anchor%2A> 속성의 값을 <xref:System.Windows.Forms.AnchorStyles.Right>로 변경합니다. Note 오른쪽 테두리가 셀의 오른쪽 테두리 가까이 되도록 이동 됩니다. 테두리 사이의 거리는의 합계는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성과 패널의 <xref:System.Windows.Forms.Control.Padding%2A> 속성입니다.  
  
3.  값을 변경는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 <xref:System.Windows.Forms.AnchorStyles.Right> 및 <xref:System.Windows.Forms.AnchorStyles.Left>합니다. 컨트롤의 셀의 너비와의 참고는 <xref:System.Windows.Forms.Control.Margin%2A> 및 <xref:System.Windows.Forms.Control.Padding%2A> 고려 하는 값입니다.  
  
4.  2와 3 단계를 반복 하는 <xref:System.Windows.Forms.AnchorStyles.Top> 및 <xref:System.Windows.Forms.AnchorStyles.Bottom> 스타일입니다.  
  
## <a name="setting-row-and-column-properties"></a>설정 행 및 열 속성  
 사용 하 여 행과 열의 개별 속성을 설정할 수는 <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> 및 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 컬렉션입니다.  
  
#### <a name="to-set-row-and-column-properties"></a>행 및 열 속성을 설정 하려면  
  
1.  선택 된 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 **Windows Forms 디자이너**합니다.  
  
2.  에 **속성** 창을 열어는 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 줄임표를 클릭 하 여 컬렉션 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 단추 옆에 **열** 항목입니다.  
  
3.  첫 번째 열을 선택 하 고 값을 변경 해당 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성을 <xref:System.Windows.Forms.SizeType.AutoSize>합니다. 클릭 **확인** 하 여 변경 내용을 적용 합니다. 주의 첫 번째 열의 너비에 맞게 축소 되는 <xref:System.Windows.Forms.Button> 제어 합니다. 열 너비 크기를 조정할 수 없는 참고 항목  
  
4.  에 **속성** 창을 열어는 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 컬렉션과 첫 번째 열을 선택 합니다. <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성의 값을 <xref:System.Windows.Forms.SizeType.Percent>로 변경합니다. 클릭 **확인** 하 여 변경 내용을 적용 합니다. 크기 조정 된 <xref:System.Windows.Forms.TableLayoutPanel> 더 큰 너비를 제어 하 고 확장 되는 첫 번째 열의 너비를 확인 합니다. 크기 조정 된 <xref:System.Windows.Forms.TableLayoutPanel> 너비를 제어 하 고 첫 번째 열에 있는 단추 셀에 맞게 크기가 조정 됩니다. 열의 너비를 조정할 수 있는지 참고도 합니다.  
  
5.  에 **속성** 창을 열어는 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 컬렉션과 나열된 된 모든 열을 선택 합니다. 값을 설정할 모든 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성을 <xref:System.Windows.Forms.SizeType.Percent>합니다. 클릭 **확인** 하 여 변경 내용을 적용 합니다. 으로 반복 된 <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> 컬렉션입니다.  
  
6.  모퉁이 크기 조정 핸들 중 하나를 선택 하 고 너비와 높이의 크기를 조정는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다. 행과 열으로 크기가 조정 되는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 크기를 변경 합니다. 또한 행과 열은 가로 크기를 조정할 수 및 크기 조정 핸들이 세로 note 합니다.  
  
## <a name="spanning-rows-and-columns-with-a-control"></a>행 및 열 컨트롤 확장  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 디자인 타임에 컨트롤에 몇 가지 새 속성을 추가 합니다. 이러한 속성 중 두 가지는 `RowSpan` 및 `ColumnSpan`합니다. 제어 범위 세 개 이상의 행 또는 열을 확인 하려면 이러한 속성을 사용할 수 있습니다.  
  
#### <a name="to-span-rows-and-columns-with-a-control"></a>행과 열 컨트롤과 확장 하려면  
  
1.  선택 된 <xref:System.Windows.Forms.Button> 첫 번째 행과 첫째 열에서 제어 합니다.  
  
2.  에 **속성** 의 값을 변경 하는 windows에서는 `ColumnSpan` 속성을 **2**합니다. <xref:System.Windows.Forms.Button> 컨트롤에서 첫 번째 열과 두 번째 열을 채웁니다. 또한 이러한 변경에 따라에 행을 더 추가 된 것 보다 note 합니다.  
  
3.  에 대 한 2 단계를 반복는 `RowSpan` 속성입니다.  
  
## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>도구 상자에서 두 번 클릭하여 컨트롤 삽입  
 채울 수 있습니다 프로그램 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에서 컨트롤을 두 번 클릭 하 고 **도구 상자**합니다.  
  
#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>도구 상자에서 두 번 클릭하여 컨트롤을 삽입하려면  
  
1.  끌어서는 <xref:System.Windows.Forms.TableLayoutPanel> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
2.  <xref:System.Windows.Forms.Button> 도구 상자 **에서**컨트롤 아이콘을 두 번 클릭합니다. 참고 새 단추 컨트롤에 표시 되는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 첫 번째 셀입니다.  
  
3.  **도구 상자**에서 컨트롤을 몇 개 더 두 번 클릭합니다. 새 컨트롤에 연속 해 서 표시는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 빈된 셀입니다. 또한는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 사용할 수 있는 열린 셀이 없는 경우 새 컨트롤에 맞게 확장 됩니다.  
  
## <a name="automatic-handling-of-overflows"></a>자동 오버플로 처리  
 에 컨트롤을 삽입 하는 경우는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 부족 해질 수 있습니다 빈 셀에 새 컨트롤에 대 한 합니다. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤이이 상황을 처리 자동으로 셀의 수를 늘려 합니다.  
  
#### <a name="to-observe-automatic-handling-of-overflows"></a>오버플로 자동 처리를 관찰 하기  
  
1.  에 빈 셀이 없으면는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 하 고, 새로 삽입을 계속 <xref:System.Windows.Forms.Button> 될 때까지 제어는 <xref:System.Windows.Forms.TableLayoutPanel> 가득 찬 합니다.  
  
2.  한 번는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤이 이면 전체를 두 번 클릭는 <xref:System.Windows.Forms.Button> 아이콘은 **도구 상자** 다른 삽입할 <xref:System.Windows.Forms.Button> 제어 합니다. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 새 컨트롤에 맞게 셀을 새로 만듭니다. 몇 가지 더 많은 컨트롤을 삽입 하 고 크기 조정 동작을 관찰 합니다.  
  
3.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> 속성 값을 <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>로 변경합니다. 두 번 클릭는 <xref:System.Windows.Forms.Button> 아이콘은 **도구 상자** 삽입할 <xref:System.Windows.Forms.Button> 될 때까지 제어는 <xref:System.Windows.Forms.TableLayoutPanel> 가득 찬 합니다. 두 번 클릭은 <xref:System.Windows.Forms.Button> 아이콘에는 **도구 상자** 다시 합니다. 오류 메시지가 나타납니다는 **Windows Forms 디자이너** 알리는 추가 행과 열을 만들 수 없습니다.  
  
## <a name="inserting-a-control-by-drawing-its-outline"></a>윤곽선을 그려 컨트롤 삽입  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 컨트롤을 삽입하고 셀에서 해당 윤곽선을 그려 크기를 지정합니다.  
  
#### <a name="to-insert-a-control-by-drawing-its-outline"></a>윤곽선을 그려 컨트롤을 삽입하려면  
  
1.  끌어서는 <xref:System.Windows.Forms.TableLayoutPanel> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
2.  **도구 상자**에서 <xref:System.Windows.Forms.Button> 컨트롤 아이콘을 클릭합니다. 폼으로 끌어다 놓지 마세요.  
  
3.  마우스 포인터를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 위로 이동합니다. 포인터가 <xref:System.Windows.Forms.Button> 컨트롤 아이콘이 연결된 십자형으로 바뀝니다.  
  
4.  마우스 단추를 길게 클릭합니다.  
  
5.  마우스 포인터를 끌어 <xref:System.Windows.Forms.Button> 컨트롤의 윤곽선을 그립니다. 원하는 크기가 되면 마우스 단추를 놓습니다. <xref:System.Windows.Forms.Button> 컨트롤이 컨트롤의 윤곽선을 그린 셀에 만들어집니다.  
  
## <a name="multiple-controls-within-cells-are-not-permitted"></a>셀 내에서 여러 컨트롤은 허용 되지 않습니다.  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 셀 마다 하나의 자식 컨트롤을 포함할 수 있습니다.  
  
#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>셀 내에서 여러 개의 컨트롤 허용 되지 않는 보여 주기 위해  
  
-   끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 에 <xref:System.Windows.Forms.TableLayoutPanel> 제어 하 고 사용 된 셀 중 하나에 놓습니다. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 삭제할 수 없습니다는 <xref:System.Windows.Forms.Button> 셀으로 끌 제어 합니다.  
  
## <a name="swapping-controls"></a>교환 컨트롤  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용 하면 두 개의 다른 셀 컨트롤을 교환할 수 있습니다.  
  
#### <a name="to-swap-controls"></a>컨트롤을 바꾸려면  
  
-   중 하나를 끌어는 <xref:System.Windows.Forms.Button> 점유 셀 및 놓습니다 이미 사용 중인된 다른 셀에서 컨트롤입니다. 참고에 다른 두 개의 한 셀에서 이동 됩니다.  
  
## <a name="next-steps"></a>다음 단계  
 레이아웃 패널 및 컨트롤의 조합을 사용하여 복잡한 레이아웃을 얻을 수 있습니다. 다음과 같은 사항을 더 살펴보는 것이 좋습니다.  
  
-   크기 조정 중 하나를 시도 <xref:System.Windows.Forms.Button> 컨트롤을 더 큰 크기 및 레이아웃에 미치는 영향을 확인 합니다.  
  
-   에 여러 컨트롤의 선택 영역을 붙여는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 하 고 어떻게 컨트롤은 삽입 되는지 확인 합니다.  
  
-   레이아웃 패널에 다른 레이아웃 패널을 포함할 수 있습니다. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 기존 컨트롤에 끌어다 놓습니다.  
  
-   <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 부모 폼에 도킹합니다. 폼의 크기를 조정하고 레이아웃에 미치는 영향을 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Microsoft Windows 사용자 환경, 사용자 인터페이스 개발자 및 디자이너를 위한 공식 지침. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)](http://www.microsoft.com/mspress/southpacific/books/book11588.htm)  
 [연습: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기](http://msdn.microsoft.com/library/e193b4fc-912a-4917-b036-b76c7a6f58ab)  
 [연습: 지역화 가능한 Windows Form 만들기](http://msdn.microsoft.com/library/c5240b6e-aaca-4286-9bae-778a416edb9c)  
 [TableLayoutPanel 컨트롤에 대한 모범 사례](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)  
 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [방법: Windows Forms에서 컨트롤 고정](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [방법: Windows Forms에서 컨트롤 고정](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)  
 [연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
