---
title: '연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: f8e8122f82bc6a8c4fab17b8b73c07d08bab4d26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a>연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬
폼의 정확한 컨트롤 배치는 많은 응용 프로그램에서 우선 순위가 높습니다. Windows Forms 디자이너가이를 위해 여러 레이아웃 도구를 제공 합니다. 가장 중요 한 중 하나는 <xref:System.Windows.Forms.Design.Behavior.SnapLine> 기능입니다.  
  
 맞춤선은 정확 하 게 정렬 위치를 다른 제어 기능과 함께 컨트롤을 보여 줍니다. 또한 보여 있습니다 여백의 Windows 사용자 인터페이스 지침에 지정 된 대로 컨트롤 사이의 권장된 거리입니다. 자세한 내용은 참조 [사용자 인터페이스 디자인 및 개발](http://go.microsoft.com/FWLink/?LinkId=83878)합니다.  
  
 맞춤선 쉽게 보다를 사용자 컨트롤을 맞출 전문적인 모양 및 동작 (모양 및 느낌).  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   Windows Forms 프로젝트 만들기  
  
-   간격 및 맞춤선을 사용 하 여 컨트롤 정렬  
  
-   에 폼과 컨테이너 여백  
  
-   그룹화 된 컨트롤에 맞춤  
  
-   맞춤선을 사용 하 여 크기로 윤곽선 지정 하 여 컨트롤을 추가 하려면  
  
-   도구 상자에서 컨트롤을 끌어 올 때 맞춤선을 사용 하 여  
  
-   맞춤선을 사용 하 여 컨트롤 크기 조정  
  
-   컨트롤의 텍스트에 레이블 맞춤  
  
-   맞춤선을 사용 하 여 키보드 탐색  
  
-   맞춤선 및 레이아웃 패널  
  
-   맞춤선을 사용 하지 않도록 설정  
  
 완료 되 면 맞춤선 기능에 의해 수행 하는 레이아웃 역할을 이해를 해야 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1.  "SnaplineExample" 이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다. 자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.  
  
2.  폼 디자이너에서 폼을 선택 합니다.  
  
## <a name="spacing-and-aligning-controls-using-snaplines"></a>간격 및 맞춤선을 사용 하 여 컨트롤 정렬  
 맞춤선 폼에서 컨트롤 정렬 하는 정확 하 고 직관적인 방법을 제공 합니다. 선택한 컨트롤을 다른 컨트롤 또는 컨트롤 집합에 맞출 위치 근처 이동할 때 나타납니다. 선택 항목은 "맞춤선" 제안된 된 위치에 다른 컨트롤을 지 나 이동 하면 합니다.  
  
#### <a name="to-arrange-controls-using-snaplines"></a>맞춤선을 사용 하 여 컨트롤을 정렬 하려면  
  
1.  끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
2.  이동 된 <xref:System.Windows.Forms.Button> 컨트롤을 폼의 오른쪽 아래 모퉁이로 합니다. 참고로 표시 되는 맞춤선의 <xref:System.Windows.Forms.Button> 아래쪽 및 오른쪽 테두리 폼의 컨트롤에 도달 합니다. 이러한 맞춤선 폼 컨트롤의 테두리 사이의 권장된 거리를 표시 합니다.  
  
3.  이동 된 <xref:System.Windows.Forms.Button> 컨트롤 주위의 테두리 폼 및 맞춤선 나타나는 위치를 확인 합니다. 작업을 완료 하는 경우 이동 된 <xref:System.Windows.Forms.Button> 가운데 폼의 컨트롤입니다.  
  
4.  다른 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
5.  두 번째 이동 <xref:System.Windows.Forms.Button> 거의 첫 번째 수준 될 때까지 제어 합니다. 맞춤선이 두 단추의 텍스트 기준선에 표시 되 고 컨트롤이 이동 하는 컨트롤이 다른 컨트롤과 수준의 위치에 맞춰집니다.  
  
6.  두 번째 이동 <xref:System.Windows.Forms.Button> 첫 번째 바로 위에 놓을 때까지 제어 합니다. 컨트롤 사용자는 다른 컨트롤과 정렬 되는 위치에 이동 맞춰집니다 있고 두 단추의 왼쪽 및 오른쪽 가장자리를 따라 표시 되는 맞춤선을 note 합니다.  
  
7.  중 하나를 선택는 <xref:System.Windows.Forms.Button> 제어 하 고 거의 닿는 될 때까지 다른 가깝게 이동 합니다. 사이 나타나는 맞춤선 참고 합니다. 이 간격은 컨트롤 테두리 사이의 권장된 거리입니다. 또한 참고는 컨트롤이 이동 하는이 위치에 맞춰집니다.  
  
8.  두 개 <xref:System.Windows.Forms.Panel> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
9. 이동 중 하나는 <xref:System.Windows.Forms.Panel> 거의 첫 번째 수준 될 때까지 제어 합니다. 두 컨트롤의 위쪽 및 아래쪽 가장자리를 따라 표시 되 고 컨트롤이 다른 컨트롤과 수준의 위치로 이동 하는 컨트롤 맞춰집니다 되는 맞춤선을 note 합니다.  
  
## <a name="aligning-to-form-and-container-margins"></a>에 폼과 컨테이너 여백  
 맞춤선을 사용 하면 일관 된 방식으로 컨트롤을 폼 및 컨테이너 여백을 맞출 수 있습니다.  
  
#### <a name="to-align-controls-to-form-and-container-margins"></a>폼 및 컨테이너 여백에 컨트롤을 맞추려면  
  
1.  중 하나를 선택는 <xref:System.Windows.Forms.Button> 제어 하 고 맞춤선 나타날 때까지 폼의 오른쪽 테두리에 가깝게 이동 합니다. 오른쪽 테두리에서 계산 된 맞춤선의 거리는 컨트롤의 합계인 <xref:System.Windows.Forms.Control.Margin%2A> 속성과 양식의 <xref:System.Windows.Forms.Control.Padding%2A> 속성 값입니다.  
  
> [!NOTE]
>  하는 경우 폼의 <xref:System.Windows.Forms.Control.Padding%2A> 0,0,0,0 속성, Windows Forms 디자이너는 숨겨진 폼 제공 <xref:System.Windows.Forms.Control.Padding%2A> 9,9,9,9의 값입니다. 이 동작을 재정의 하려면 0,0,0,0 이외의 값을 할당 합니다.  
  
1.  값을 변경는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 확장은 <xref:System.Windows.Forms.Control.Margin%2A> 항목에는 **속성** 창과 설정은 <xref:System.Windows.Forms.Padding.All%2A> 속성을 0입니다. 자세한 내용은 참조 [연습: 레이아웃으로 Windows Forms 컨트롤 Padding, Margins 및 AutoSize 속성](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)합니다.  
  
2.  이동 된 <xref:System.Windows.Forms.Button> 맞춤선이 나타날 때까지 폼의 오른쪽 테두리에 가깝게 제어 합니다. 이 간격은 폼의 값에서 제공 됩니다 <xref:System.Windows.Forms.Control.Padding%2A> 속성입니다.  
  
3.  끌어서는 <xref:System.Windows.Forms.GroupBox> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
4.  값을 변경는 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 확장은 <xref:System.Windows.Forms.Control.Padding%2A> 항목에는 **속성** 창과 설정은 <xref:System.Windows.Forms.Padding.All%2A> 속성을 10입니다.  
  
5.  끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 에 <xref:System.Windows.Forms.GroupBox> 제어 합니다.  
  
6.  이동 된 <xref:System.Windows.Forms.Button> 컨트롤의 오른쪽 테두리에 가깝게는 <xref:System.Windows.Forms.GroupBox> 맞춤선이 나타날 때까지 제어 합니다. 이동의 <xref:System.Windows.Forms.Button> 컨트롤 내에서 <xref:System.Windows.Forms.GroupBox> 제어 및 맞춤선 나타나는 위치를 확인 합니다.  
  
## <a name="aligning-to-grouped-controls"></a>그룹화 된 컨트롤에 맞춤  
 맞춤선을 사용 하 여 그룹화 된 컨트롤을 맞출 수 컨트롤 내에서 뿐만 <xref:System.Windows.Forms.GroupBox> 제어 합니다.  
  
#### <a name="to-align-to-grouped-controls"></a>그룹화 된 컨트롤을 맞추려면  
  
1.  두 개의 폼에 컨트롤을 선택 합니다. 선택 영역을 이동 하 고 선택 항목 및 다른 컨트롤 사이 표시 되는 맞춤선을 기록해 둡니다.  
  
2.  끌어서는 <xref:System.Windows.Forms.GroupBox> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
3.  끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 에 <xref:System.Windows.Forms.GroupBox> 제어 합니다.  
  
4.  중 하나를 선택는 <xref:System.Windows.Forms.Button> 컨트롤과 주위로 이동는 <xref:System.Windows.Forms.GroupBox> 제어 합니다. 참고의 가장자리에 표시 되는 맞춤선의 <xref:System.Windows.Forms.GroupBox> 제어 합니다. 또한 맞춤선의 가장자리에 표시 되는 <xref:System.Windows.Forms.Button> 컨트롤에 포함 되는 <xref:System.Windows.Forms.GroupBox> 제어 합니다. 컨테이너 컨트롤의 자식 컨트롤에는 또한 맞춤선을 지원 합니다.  
  
## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a>맞춤선을 사용 하 여 크기로 윤곽선 지정 하 여 컨트롤을 추가 하려면  
 맞춤선 정렬 때 처음 배치 하는 폼에서 제어 합니다.  
  
#### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a>크기로 윤곽선 지정 하 여 컨트롤을 배치 하려면 맞춤선을 사용 하려면  
  
1.  **도구 상자**에서 <xref:System.Windows.Forms.Button> 컨트롤 아이콘을 클릭합니다. 폼으로 끌어다 놓지 마세요.  
  
2.  폼의 디자인 화면 위로 마우스 포인터를 이동 합니다. 포인터가 <xref:System.Windows.Forms.Button> 컨트롤 아이콘이 연결된 십자형으로 바뀝니다. 또한 맞춤선 맞춤된 위치를 제안에 게 표시 되는 <xref:System.Windows.Forms.Button> 제어 합니다.  
  
3.  마우스 단추를 길게 클릭합니다.  
  
4.  폼에서 마우스 포인터를 끕니다. 참고 개요 그려짐을, 위치 및 컨트롤의 크기를 나타내는입니다.  
  
5.  폼에 다른 컨트롤과 맞춰질 때까지 포인터를 끕니다. 맞춤을 나타내는 맞춤선 나타나는 참고 합니다.  
  
6.  마우스 단추를 놓습니다. 컨트롤의 윤곽선으로 표시 되는 크기와 위치에 생성 됩니다.  
  
## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a>도구 상자에서 컨트롤을 끌어 올 때 맞춤선을 사용 하 여  
 맞춤선 정렬 컨트롤을 끌어 올 때에서 **도구 상자** 폼으로 합니다.  
  
#### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a>도구 상자에서 컨트롤을 끌어 올 때 맞춤선을 사용 하려면  
  
1.  끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 에서 폼으로 하지만 마우스 단추를 해제 하지 않습니다.  
  
2.  폼의 디자인 화면 위로 마우스 포인터를 이동 합니다. 포인터가 변경 되는 위치를 나타내는 새 <xref:System.Windows.Forms.Button> 컨트롤 생성 됩니다.  
  
3.  폼에서 마우스 포인터를 끕니다. 맞춤선에 대 한 맞춤된 위치를 제안에 게 표시 되는 <xref:System.Windows.Forms.Button> 제어 합니다. 다른 컨트롤에 정렬 되는 위치를 찾습니다.  
  
4.  마우스 단추를 놓습니다. 컨트롤이 맞춤선 나타내는 위치에 만들어집니다.  
  
## <a name="resizing-controls-using-snaplines"></a>맞춤선을 사용 하 여 컨트롤 크기 조정  
 맞춤선 하는 데 도움이 크기를 조정할 때 컨트롤을 정렬 합니다.  
  
#### <a name="to-resize-a-control-using-snaplines"></a>맞춤선을 사용 하는 컨트롤의 크기를 조정 하려면  
  
1.  끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
2.  크기 조정의 <xref:System.Windows.Forms.Button> 모퉁이 끌어서 크기 조정 핸들 중 하나를 선택 하 여 제어 합니다. 자세한 내용은 참조 [하는 방법: Windows Forms에서 컨트롤의 크기를 조정](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)합니다.  
  
3.  중 하나가 때까지 크기 조정 핸들을 끌어는 <xref:System.Windows.Forms.Button> 컨트롤의 테두리는 다른 컨트롤과 정렬 됩니다. 맞춤선 나타나는 참고 합니다. 또한 메모를 크기 조정 핸들 맞춤선으로 지정 된 위치에 맞춰집니다.  
  
4.  크기 조정 된 <xref:System.Windows.Forms.Button> 방향을 제어 하 고 크기 조정 핸들을 다른 컨트롤에 맞춥니다. Note 맞춤선 맞춤을 나타내는 다양 한 방향에 표시 되는 방식입니다.  
  
## <a name="aligning-a-label-to-a-controls-text"></a>컨트롤의 텍스트에 레이블 맞춤  
 일부 컨트롤은 다른 컨트롤에 표시 된 텍스트 정렬을 위한 맞춤선을 제공 합니다.  
  
#### <a name="to-align-a-label-to-a-controls-text"></a>컨트롤의 텍스트에 레이블을 맞추려면  
  
1.  끌어서는 <xref:System.Windows.Forms.TextBox> 에서 제어는 **도구 상자** 폼으로 합니다. 삭제할 경우는 <xref:System.Windows.Forms.TextBox> 컨트롤을 폼으로, 스마트 태그 문자 모양을 클릭 하 고, 선택는 **텍스트 textBox1를 설정할** 옵션입니다. 자세한 내용은 참조 [연습: 수행 일반적인 태스크를 사용 하 여 스마트 태그를 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)합니다.  
  
2.  끌어서는 <xref:System.Windows.Forms.Label> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
3.  <xref:System.Windows.Forms.Label> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 변경합니다. 참고가 컨트롤의 테두리 표시 텍스트에 맞게 조정 됩니다.  
  
4.  이동의 <xref:System.Windows.Forms.Label> 컨트롤의 왼쪽에는 <xref:System.Windows.Forms.TextBox> 의 아래쪽 가장자리에 맞춥니다 이므로 컨트롤는 <xref:System.Windows.Forms.TextBox> 제어 합니다. 두 컨트롤의 아래쪽 가장자리를 따라 나타나는 맞춤선을 note 합니다.  
  
5.  이동의 <xref:System.Windows.Forms.Label> 제어 될 때까지 상향 약간는 <xref:System.Windows.Forms.Label> 텍스트 및 <xref:System.Windows.Forms.TextBox> 텍스트를 정렬 합니다. 두 컨트롤의 텍스트 필드 맞춰진 경우를 나타내는 표시 하는 다른 스타일된 맞춤선을 note 합니다.  
  
## <a name="using-snaplines-with-keyboard-navigation"></a>맞춤선을 사용 하 여 키보드 탐색  
 맞춤선 정렬 키보드의 화살표 키를 사용 하 여 정렬할 때 제어 합니다.  
  
#### <a name="to-use-snaplines-with-keyboard-navigation"></a>키보드 탐색 맞춤선을 사용 하려면  
  
1.  끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼으로 합니다. 폼의 왼쪽 위 모퉁이에 배치 합니다.  
  
2.  CTRL + 아래쪽 화살표를 누릅니다. 첫 번째 사용 가능한 가로 맞춤 위치로 컨트롤을 폼 아래로 이동 하는 참고 합니다.  
  
3.  컨트롤이 폼의 맨 아래에 도달할 때까지 CTRL + 아래쪽 화살표를 누릅니다. Note 양식을 아래로 이동할 때 컨트롤의 위치입니다.  
  
4.  CTRL + 오른쪽 화살표를 누릅니다. 컨트롤의 첫 번째 세로 맞춤을 사용할 수 있는 위치로 폼으로 이동 하는 참고 합니다.  
  
5.  컨트롤이 폼의 측면에 도달할 때까지 CTRL + 오른쪽 화살표를 누릅니다. 폼에서 이동할 때 컨트롤의 위치를 note 합니다.  
  
6.  화살표 키의 조합으로 컨트롤을 폼 주위로 이동 합니다. 컨트롤이 차지 하는 위치를 확인 하 고 맞춤선을 함께 사용 하 합니다.  
  
7.  크기를 조정 하려면 SHIFT + 화살표 키를 눌러는 <xref:System.Windows.Forms.Button> 하나의 픽셀 단위로 제어 합니다.  
  
8.  크기를 조정 하려면 CTRL + SHIFT + 모든 화살표 키를 눌러는 <xref:System.Windows.Forms.Button> 맞춤선 단위로 제어 합니다.  
  
## <a name="snaplines-and-layout-panels"></a>맞춤선 및 레이아웃 패널  
 맞춤선은 레이아웃 패널 내에서 사용할 수 없습니다.  
  
#### <a name="to-selectively-disable-snaplines"></a>맞춤선을 선택적으로 해제 하려면  
  
1.  끌어서는 <xref:System.Windows.Forms.TableLayoutPanel> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
2.  <xref:System.Windows.Forms.Button> 도구 상자 **에서**컨트롤 아이콘을 두 번 클릭합니다. 참고 새 단추 컨트롤에 표시 되는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 첫 번째 셀입니다.  
  
3.  두 번 클릭 하 고 <xref:System.Windows.Forms.Button> 컨트롤 아이콘은 **도구 상자** 두 번 더 합니다. 이 방법에서 빈 셀이 하나는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.  
  
4.  끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 의 빈 셀에는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다. 참고 맞춤선이 나타나지 않습니다.  
  
5.  끌어서는 <xref:System.Windows.Forms.Button> 의 제어는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 하 고 주위로 이동는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다. 맞춤선이 다시 나타납니다 유의 합니다.  
  
## <a name="disabling-snaplines"></a>맞춤선을 사용 하지 않도록 설정  
 맞춤선은 기본적으로 켜 집니다. 맞춤선을 선택적으로 해제할 수 있습니다 또는 디자인 환경에서 비활성화할 수 있습니다.  
  
#### <a name="to-selectively-disable-snaplines"></a>맞춤선을 선택적으로 해제 하려면  
  
-   ALT 키를 누르고 주위 폼 컨트롤을 이동 하는 동안 합니다.  
  
     Note 맞춤선이 나타나지 않고 및 가능한 맞춤 위치에 컨트롤 맞춤 되지 않습니다.  
  
#### <a name="to-disable-snaplines-in-the-design-environment"></a>디자인 환경에서 맞춤선을 사용 하지 않도록 설정 하려면  
  
1.  **도구** 메뉴를 열고는 **옵션** 대화 상자. Windows Forms 디자이너 대화 상자를 엽니다. 자세한 내용은 참조 [Windows Forms 디자이너, 옵션 대화 상자, 일반](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)합니다.  
  
2.  선택 된 **일반** 노드. 에 **레이아웃 모드** 섹션, 선택을 변경 **맞춤선** 를 **SnapToGrid**합니다.  
  
3.  설정을 적용 하려면 확인을 클릭 합니다.  
  
4.  폼에 컨트롤을 선택 하 고 다른 컨트롤 이동 합니다. 맞춤선 나타나지 않는 참고 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 맞춤선에 폼 컨트롤을 정렬 하는 직관적인 방법을 제공 합니다. 다음과 같은 사항을 더 살펴보는 것이 좋습니다.  
  
-   중첩 시도 <xref:System.Windows.Forms.GroupBox> 컨트롤 내에 다른 <xref:System.Windows.Forms.GroupBox> 제어 합니다. 위치는 <xref:System.Windows.Forms.Button> 자식 내에서 컨트롤 <xref:System.Windows.Forms.GroupBox> 컨트롤과 부모 내의 다른 <xref:System.Windows.Forms.GroupBox> 제어 합니다. 이동 된 <xref:System.Windows.Forms.Button> 컨트롤을 맞춤선 컨테이너 경계를 교차 하는 방법을 참조 하세요.  
  
-   열을 만들 <xref:System.Windows.Forms.TextBox> 컨트롤 및 해당 열 <xref:System.Windows.Forms.Label> 컨트롤입니다. 값으로 설정 된 <xref:System.Windows.Forms.Label> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 `true`합니다. 맞춤선을 사용 하 여 이동 된 <xref:System.Windows.Forms.Label> 컨트롤의 표시 된 텍스트의 텍스트를 맞춥니다는 <xref:System.Windows.Forms.TextBox> 컨트롤입니다.  
  
 Windows 사용자 인터페이스 디자인에 대 한 내용은 책을 참조 하십시오. *Microsoft Windows User Experience, Official Guidelines 사용자 인터페이스 개발자 및 디자이너에 대 한* Redmond, WA: Microsoft Press, 1999 합니다. (USBN: 0-7356-0566-1).  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Design.Behavior.SnapLine>  
 [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)  
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
