---
title: ToolStrip 컨트롤 아키텍처
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
ms.openlocfilehash: fd00fff6c745f5f7991c038dec305b5d45761656
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="toolstrip-control-architecture"></a>ToolStrip 컨트롤 아키텍처
<xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.ToolStripItem> 클래스 도구 모음, 상태 및 메뉴 항목을 표시 하기 위한 유연 하 고 확장 가능한 시스템을 제공 합니다. 이러한 클래스에 포함 된 모든는 <xref:System.Windows.Forms> "ToolStrip" 접두사는 네임 스페이스 및 이러한를 명명 된 일반적으로 (와 같은 <xref:System.Windows.Forms.ToolStripOverflow>) 또는 "Strip" 접미사와 함께 (같은 <xref:System.Windows.Forms.MenuStrip>).  
  
## <a name="toolstrip"></a>ToolStrip  
 다음 항목에서는 <xref:System.Windows.Forms.ToolStrip> 및 파생 된 컨트롤입니다.  
  
 <xref:System.Windows.Forms.ToolStrip> 에 대 한 추상 기본 클래스 <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, 및 <xref:System.Windows.Forms.ContextMenuStrip>합니다. 다음 개체 모델에서는 <xref:System.Windows.Forms.ToolStrip> 상속 계층 구조입니다.  
  
 ![ToolStrip 개체 모델](../../../../docs/framework/winforms/controls/media/toolstripobjectmodel.gif "ToolStripObjectModel")  
ToolStrip 개체 모델  
  
 모든 항목에 액세스할 수 있습니다는 <xref:System.Windows.Forms.ToolStrip> 통해는 <xref:System.Windows.Forms.ToolStrip.Items%2A> 컬렉션입니다. 모든 항목에 액세스할 수 있습니다는 <xref:System.Windows.Forms.ToolStripDropDownItem> 통해는 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> 컬렉션입니다. 파생 된 클래스에서 <xref:System.Windows.Forms.ToolStrip>를 사용할 수도 있습니다는 <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> 속성 현재 표시 된 항목만 액세스할 수 있습니다. 다음은 현재 오버플로 메뉴에 없는 항목입니다.  
  
 다음 항목은 둘 다와 함께 원활 하 게 작동 하도록 특별히 설계 <xref:System.Windows.Forms.ToolStripSystemRenderer> 및 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 모든 방향에서. 에 대 한 디자인 타임에 기본적으로 사용할 수 있는 <xref:System.Windows.Forms.ToolStrip> 제어:  
  
-   <xref:System.Windows.Forms.ToolStripButton>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="menustrip"></a>MenuStrip  
 <xref:System.Windows.Forms.MenuStrip> 대체 하는 최상위 컨테이너 인지 <xref:System.Windows.Forms.MainMenu>합니다. 또한 키 처리 및 여러 문서 MDI (인터페이스) 기능도 제공 합니다. 기능적으로 <xref:System.Windows.Forms.ToolStripDropDownItem> 및 <xref:System.Windows.Forms.ToolStripMenuItem> 과 함께 작동 <xref:System.Windows.Forms.MenuStrip>에서 파생 된 하지만, <xref:System.Windows.Forms.ToolStripItem>합니다.  
  
 다음 항목은 둘 다와 함께 원활 하 게 작동 하도록 특별히 설계 <xref:System.Windows.Forms.ToolStripSystemRenderer> 및 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 모든 방향에서. 에 대 한 디자인 타임에 기본적으로 사용할 수 있는 <xref:System.Windows.Forms.MenuStrip> 제어:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="statusstrip"></a>StatusStrip  
 <xref:System.Windows.Forms.StatusStrip> 대체는 <xref:System.Windows.Forms.StatusBar> 제어 합니다. 특수 기능 <xref:System.Windows.Forms.StatusStrip> 폼의 크기 조정 및 이동 그립에 대 한 지원이, 사용자 지정 테이블 레이아웃을 포함 및 `Spring` 있도록은 <xref:System.Windows.Forms.ToolStripStatusLabel> 사용 가능한 공간을 자동으로 채울 수 있습니다.  
  
 다음 항목은 둘 다와 함께 원활 하 게 작동 하도록 특별히 설계 <xref:System.Windows.Forms.ToolStripSystemRenderer> 및 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 모든 방향에서. 에 대 한 디자인 타임에 기본적으로 사용할 수 있는 <xref:System.Windows.Forms.StatusStrip> 제어:  
  
-   <xref:System.Windows.Forms.ToolStripStatusLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripProgressBar>  
  
### <a name="contextmenustrip"></a>ContextMenuStrip  
 <xref:System.Windows.Forms.ContextMenuStrip> 대체 <xref:System.Windows.Forms.ContextMenu>합니다. 연결할 수는 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤과 마우스 오른쪽으로 클릭 하 여 자동으로 표시 상황에 맞는 메뉴 (또는 바로 가기 메뉴). 표시할 수 있습니다는 <xref:System.Windows.Forms.ContextMenuStrip> 를 사용 하 여 프로그래밍 방식으로 <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> 메서드. <xref:System.Windows.Forms.ContextMenuStrip> 취소할 수 있는 지원 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 및 <xref:System.Windows.Forms.ToolStripDropDown.Closing> 동적 채우기 및 여러 번 클릭 시나리오를 처리 하는 이벤트입니다. <xref:System.Windows.Forms.ContextMenuStrip> 이미지, 상태를 확인 하는 메뉴 항목, 텍스트, 액세스 키, 바로 가기 및 계단식 메뉴를 지원합니다.  
  
 다음 항목은 둘 다와 함께 원활 하 게 작동 하도록 특별히 설계 <xref:System.Windows.Forms.ToolStripSystemRenderer> 및 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 모든 방향에서. 에 대 한 디자인 타임에 기본적으로 사용할 수 있는 <xref:System.Windows.Forms.ContextMenuStrip> 제어:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="toolstrip-generic-features"></a>ToolStrip 일반 기능  
 다음 항목에서는 기능 및 동작을 일반적인는 <xref:System.Windows.Forms.ToolStrip> 및 파생 된 컨트롤입니다.  
  
#### <a name="painting"></a>그리기  
 사용자 지정 그리기를 수행할 수 있는 <xref:System.Windows.Forms.ToolStrip> 여러 가지 방법으로 제어 합니다. 다른 Windows Forms 컨트롤에서와 마찬가지로 <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.ToolStripItem> 둘 다 재정의 가능한 `OnPaint` 메서드 및 `Paint` 이벤트입니다. 컨트롤의 클라이언트 영역을 기준으로 좌표 시스템은 일반적인 그리기 컨트롤의 왼쪽 위 모서리 즉, 0, 0입니다. `Paint` 이벤트 및 `OnPaint` 에 대 한 메서드는 <xref:System.Windows.Forms.ToolStripItem> 다른 컨트롤 그리기 이벤트 처럼 동작 합니다.  
  
 <xref:System.Windows.Forms.ToolStrip> 컨트롤 제공 항목과 통해 컨테이너의 렌더링에 대 한 보다 세부적인 액세스는 <xref:System.Windows.Forms.ToolStripRenderer> 배경, 항목 배경, 항목 이미지, 항목 화살표, 항목 텍스트를 그리기 위한 재정의 가능한 메서드를가지고 있는 클래스와의 테두리는 <xref:System.Windows.Forms.ToolStrip>. 이러한 방법에 대 한 이벤트 인수를 사용 하는 사각형, 색 및 필요에 따라 조정할 수 있는 텍스트 형식 등의 여러 속성을 노출 합니다.  
  
 몇 가지 항목을 그리는 방법을 조정 하려면 일반적으로 재정의 <xref:System.Windows.Forms.ToolStripRenderer>합니다.  
  
 새 항목을 작성 하 고 그리기의 모든 측면을 제어 하려면 무시 된 `OnPaint` 메서드. 내에서 `OnPaint`에서 메서드를 사용할 수는 <xref:System.Windows.Forms.ToolStripRenderer>합니다.  
  
 기본적으로는 <xref:System.Windows.Forms.ToolStrip> 이중 버퍼링을 활용 하기 위해 되는지는 <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> 설정 합니다.  
  
#### <a name="parenting"></a>부모/자식 관리  
 컨테이너 소유권 및 부모/자식 관리의 개념은에서 더 복잡 한 <xref:System.Windows.Forms.ToolStrip> 보다 다른 Windows Forms 컨테이너 컨트롤에서을 제어 합니다. 오버플로 여러 드롭 다운 항목을 공유 하는 등의 동적 시나리오를 지 원하는 데 필요한 즉 <xref:System.Windows.Forms.ToolStrip> 항목의 생성을 지원 하 고는 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤에서 합니다.  
  
 다음 목록에는 부모/자식 관리와 관련 된 멤버에 설명 하 고 용도 설명 합니다.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A> 드롭다운 목록 항목의 원본을 있는 항목에 액세스 합니다. 이 비슷합니다 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>, 컨트롤을 반환 하는 대신 반환 하지만 <xref:System.Windows.Forms.ToolStripItem>합니다.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A> 컨트롤의 원본인 결정의 <xref:System.Windows.Forms.ContextMenuStrip> 여러 컨트롤 동일한 공유 때 <xref:System.Windows.Forms.ContextMenuStrip>합니다.  
  
-   <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A> 에 대 한 읽기 전용 접근자는 <xref:System.Windows.Forms.ToolStripItem.Parent%2A> 속성입니다. 부모 소유자 점에서 다릅니다 부모 나타냅니다는 반환 된 현재 <xref:System.Windows.Forms.ToolStrip> 항목이 표시 되는 넘침 영역에 있을 수 있습니다.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Owner%2A> 반환 된 <xref:System.Windows.Forms.ToolStrip> 는 항목 컬렉션에 현재 포함 <xref:System.Windows.Forms.ToolStripItem>합니다. 이 참조 하는 가장 좋은 방법은 <xref:System.Windows.Forms.ToolStrip.ImageList%2A> 또는 기타 속성 최상위 <xref:System.Windows.Forms.ToolStrip> 오버플로 처리 하기 위한 특별 한 코드를 작성 하지 않고도 합니다.  
  
#### <a name="behavior-of-inherited-controls"></a>상속 된 컨트롤의 동작  
 다음과 같은 컨트롤이 상속에 사용 될 때마다 잠깁니다.  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.ToolStripPanel> 패널을 포함 하는 <xref:System.Windows.Forms.ToolStripContainer> 개별 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤입니다.  
  
 예를 들어, 이전 목록의 컨트롤 중 하나 이상을 사용 하 여 새 Windows Forms 응용 프로그램을 만듭니다. 에 하나 이상의 컨트롤의 액세스 한정자를 설정 `public` 또는 `protected`, 한 다음 프로젝트를 빌드합니다. 첫 번째 형태에서 상속 된 폼을 추가 하 고 상속된 된 컨트롤을 선택 합니다. 컨트롤이 표시 되 고 액세스 수정 자가 처럼 동작 잠긴 `private`합니다.  
  
#### <a name="toolstripcontainer-support-of-inheritance"></a>ToolStripContainer 상속 지원  
 <xref:System.Windows.Forms.ToolStripContainer> 컨트롤은 다음 예제와 비슷한 제한 된 상속된 시나리오를 지원 합니다.  
  
1.  새 Windows Forms 응용 프로그램을 만듭니다.  
  
2.  폼에 <xref:System.Windows.Forms.ToolStripContainer>를 추가합니다.  
  
3.  설정의 액세스 한정자는 <xref:System.Windows.Forms.ToolStripContainer> 를 `public` 또는 `protected`합니다.  
  
4.  조합을 추가 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, 및 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤을 <xref:System.Windows.Forms.ToolStripPanel> 영역에는 <xref:System.Windows.Forms.ToolStripContainer>합니다.  
  
5.  프로젝트를 빌드합니다.  
  
6.  첫 번째 형태에서 상속 되는 폼을 추가 합니다.  
  
7.  상속 된 선택 <xref:System.Windows.Forms.ToolStripContainer> 폼에 있습니다.  
  
#### <a name="inherited-behavior-of-child-controls"></a>자식 컨트롤의 상속 된 동작  
 이전 단계를 완료 한 후에 다음과 같은 상속 된 동작이 수행 됩니다.  
  
-   디자이너에서 상속된 된 아이콘과 함께 컨트롤이 나타납니다.  
  
-   <xref:System.Windows.Forms.ToolStripPanel> 컨트롤 수 없도록 잠기지; 선택 하거나 해당 콘텐츠를 다시 정렬할 수 없습니다.  
  
-   컨트롤을 추가할 수는 <xref:System.Windows.Forms.ToolStripContentPanel>, 컨트롤을 이동 하 고 자식 컨트롤의 있도록는 <xref:System.Windows.Forms.ToolStripContentPanel>합니다.  
  
-   폼을 빌드한 후 변경 내용을 유지 합니다.  
  
    > [!NOTE]
    >  모두에서 액세스 한정자를 제거 <xref:System.Windows.Forms.ToolStripPanel> 의 일부인 컨트롤에는 <xref:System.Windows.Forms.ToolStripContainer>합니다. 액세스 한정자는 <xref:System.Windows.Forms.ToolStripContainer> 전체 컨트롤을 제어 합니다.  
  
#### <a name="partial-trust"></a>부분 신뢰  
 제한 사항을 `ToolStrip`부분 신뢰 환경에서 s는 권한이 없는 사용자나 서비스에서 사용할 수 있는 개인 정보가 의도 하지 않은 항목을 방지 하도록 설계 되었습니다. 보호 조치는 다음과 같습니다.  
  
-   `ToolStripDropDown` 컨트롤에서는 <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> 에 항목을 표시 하는 <xref:System.Windows.Forms.ToolStripControlHost>합니다. 와 같은 내장 컨트롤이 모두에 적용이 <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox>, 및 <xref:System.Windows.Forms.ToolStripProgressBar> 제한은 사용자가 만든 제어 합니다. 이 요구 사항이 충족 되지 않으면 이러한 항목이 표시 되지 않습니다. 예외가 throw되지 않습니다.  
  
-   설정의 <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> 속성을 `false` 에 허용 되지 않습니다 및 취소할 수 있는 <xref:System.Windows.Forms.ToolStripDropDown.Closing> 이벤트 매개 변수는 무시 됩니다. 그러면 드롭다운 항목을 닫지 않으면 둘 이상의 키를 입력할 수 있습니다. 이 요구 사항이 충족 되지 않으면 이러한 항목이 표시 되지 않습니다. 예외가 throw되지 않습니다.  
  
-   이벤트를 처리 하는 많은 키 입력 이외의 부분 신뢰 상황에서에서 발생 하는 경우 발생 하지 것입니다 <xref:System.Security.Permissions.UIPermissionWindow.AllWindows>합니다.  
  
-   액세스 키가 처리 될 때 <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> 는 부여 되지 않습니다.  
  
#### <a name="usage"></a>사용법  
 다음과 같은 사용 패턴 관계가 <xref:System.Windows.Forms.ToolStrip> 레이아웃, 키보드 상호 작용 및 최종 사용자 동작:  
  
-   조인는 <xref:System.Windows.Forms.ToolStripPanel>  
  
     <xref:System.Windows.Forms.ToolStrip> 내 위치를 변경할 수는 <xref:System.Windows.Forms.ToolStripPanel> 및 across <xref:System.Windows.Forms.ToolStripPanel>s입니다. `Dock` 속성은 무시 됩니다 및 경우에는 <xref:System.Windows.Forms.ToolStrip.Stretch%2A> 속성은 `false`, 크기는 <xref:System.Windows.Forms.ToolStrip> 에 항목이 추가 되 면 증가 <xref:System.Windows.Forms.ToolStripPanel>합니다. 일반적으로 <xref:System.Windows.Forms.ToolStrip> 탭 순서에 참여 하지 않습니다.  
  
-   도킹됨  
  
     <xref:System.Windows.Forms.ToolStrip> 고정된 위치에 있는 컨테이너의 한 쪽에 배치의 전체 포인터로 고정 된 크기로 확장 합니다. 일반적으로 <xref:System.Windows.Forms.ToolStrip> 탭 순서에 참여 하지 않습니다.  
  
-   절대 위치로 지정  
  
     <xref:System.Windows.Forms.ToolStrip> 는 다른 컨트롤 처럼 점에서 따라 배치 되는 <xref:System.Windows.Forms.Control.Location%2A> 크기가 고정된 되어 속성과 탭 순서에 일반적으로 참여 합니다.  
  
#### <a name="keyboard-interaction"></a>키보드 상호 작용  
  
##### <a name="access-keys"></a>선택 키  
 와 함께 또는 다음 ALT 키, 액세스 키는 키보드를 사용 하 여 컨트롤을 활성화 하는 한 가지 방법은입니다. <xref:System.Windows.Forms.ToolStrip> 둘 다 명시적 및 암시적 선택 키를 지원합니다. 명시적 정의 앰퍼샌드 (&) 문자 앞에 사용 합니다. 문자 순서에 기반 하 여 일치 하는 항목을 찾으려고 시도 하는 알고리즘을 사용 하 여 암시적 정의 주어진 `Text` 속성입니다.  
  
##### <a name="shortcut-keys"></a>바로 가기 키  
 사용 되는 바로 가기 키를 <xref:System.Windows.Forms.MenuStrip> 조합해 서 사용은 <xref:System.Windows.Forms.Keys> 열거형 (주문별은 아님) 바로 가기 키를 정의 합니다. 사용할 수도 있습니다는 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> 속성을 "삭제" 대신 "Del"을 표시 하는 등 텍스트를 사용 하 여 바로 가기 키 표시  
  
##### <a name="navigation"></a>탐색  
 ALT 키를 활성화는 <xref:System.Windows.Forms.MenuStrip> 가리키는 <xref:System.Windows.Forms.Form.MainMenuStrip%2A>합니다. 여기에서 CTRL + TAB 간을 이동 <xref:System.Windows.Forms.ToolStrip> 컨트롤 내 `ToolStripPanel`s입니다. TAB 키와 숫자 키패드의 화살표 키에 있는 항목은 탐색할는 <xref:System.Windows.Forms.ToolStrip>합니다. 특별 한 알고리즘 오버플로 영역에서 탐색을 처리합니다. 스페이스바를 누르면 선택는 <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, 또는 <xref:System.Windows.Forms.ToolStripSplitButton>합니다.  
  
##### <a name="focus-and-validation"></a>포커스 및 유효성 검사  
 ALT 키를 사용 하면 활성화 될 때는 <xref:System.Windows.Forms.MenuStrip> 또는 <xref:System.Windows.Forms.ToolStrip> 도 현재 포커스가 있는 컨트롤에서 포커스를 제거 합니다. 내에서 호스팅되는 컨트롤 인지는 <xref:System.Windows.Forms.MenuStrip> 또는의 드롭다운 목록에서 <xref:System.Windows.Forms.MenuStrip>, 컨트롤 사용자가 TAB 키를 누를 때 포커스를 얻습니다. 일반적으로 <xref:System.Windows.Forms.Control.GotFocus>, <xref:System.Windows.Forms.Control.LostFocus>, <xref:System.Windows.Forms.Control.Enter>, 및 <xref:System.Windows.Forms.Control.Leave> 의 이벤트 <xref:System.Windows.Forms.MenuStrip> 키보드 활성화 될 경우 발생할 수 있습니다. 이러한 경우에 사용 된 <xref:System.Windows.Forms.MenuStrip.MenuActivate> 및 <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> 이벤트 대신 합니다.  
  
 기본적으로 <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> 은 `false`합니다. 호출 <xref:System.Windows.Forms.ContainerControl.Validate%2A> 명시적으로 폼에를 유효성 검사를 수행 합니다.  
  
#### <a name="layout"></a>레이아웃  
 제어 <xref:System.Windows.Forms.ToolStrip> 레이아웃의 멤버 중 하나를 선택 하 여 <xref:System.Windows.Forms.ToolStripLayoutStyle> 와 <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 속성입니다.  
  
##### <a name="stack-layouts"></a>스택 레이아웃  
 양쪽 끝에서 서로 옆에 있는 항목을 정렬 하는 것을 쌓는 <xref:System.Windows.Forms.ToolStrip>합니다. 다음 목록에는 스택 레이아웃을 설명 합니다.  
  
-   기본값은 <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow>입니다. 이 설정을 사용 하면는 <xref:System.Windows.Forms.ToolStrip> 레이아웃에 따라 자동으로 변경 하는 <xref:System.Windows.Forms.ToolStrip.Orientation%2A> 끌어서 도킹 시나리오를 처리 하는 속성입니다.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow> 렌더링 된 <xref:System.Windows.Forms.ToolStrip> 서로 옆에 있는 항목을 세로로 합니다.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow> 렌더링 된 <xref:System.Windows.Forms.ToolStrip> 서로 옆에 있는 항목을 가로로 합니다.  
  
##### <a name="other-features-of-stack-layouts"></a>스택 레이아웃의 다른 기능  
 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 끝을 결정는 <xref:System.Windows.Forms.ToolStrip> 항목이 정렬 됩니다.  
  
 항목에 적합 하지 않은 경우는 <xref:System.Windows.Forms.ToolStrip>, 오버플로 단추가 자동으로 나타납니다. <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 속성을 설정 하지 또는 필요에 따라 항상 항목 넘침 영역에 나타나는지 결정 합니다.  
  
 에 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 검사할 수 이벤트는 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 속성 항목의 주에 배치 되었는지 여부를 확인 하 <xref:System.Windows.Forms.ToolStrip>, 오버플로 <xref:System.Windows.Forms.ToolStrip>, 전혀 표시 되지 않을 경우 또는 합니다. 항목이 표시 되지 않으면 하는 일반적인 이유는 해당 항목의 주에 맞지 않고 <xref:System.Windows.Forms.ToolStrip> 및 해당 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 속성이로 설정 된 <xref:System.Windows.Forms.ToolStripItemOverflow.Never>합니다.  
  
 확인 한 <xref:System.Windows.Forms.ToolStrip> 에 삽입 하 여 이동 가능한는 <xref:System.Windows.Forms.ToolStripPanel> 설정과 해당 <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> 를 <xref:System.Windows.Forms.ToolStripGripStyle.Visible>합니다.  
  
##### <a name="other-layout-options"></a>다른 레이아웃 옵션  
 다른 레이아웃 옵션은 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 및 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>합니다.  
  
##### <a name="flow-layout"></a>선형 레이아웃  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 레이아웃에 대 한 기본값은 <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, 및 <xref:System.Windows.Forms.ToolStripOverflow>합니다. 비슷합니다는 <xref:System.Windows.Forms.FlowLayoutPanel>합니다. 기능 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 레이아웃은 다음과 같습니다.  
  
-   모든 기능을 <xref:System.Windows.Forms.FlowLayoutPanel> 에 의해 노출 되는 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> 속성입니다. 캐스팅 해야는 <xref:System.Windows.Forms.LayoutSettings> 클래스는 <xref:System.Windows.Forms.FlowLayoutSettings> 클래스입니다.  
  
-   사용할 수는 <xref:System.Windows.Forms.ToolStripItem.Dock%2A> 및 <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> 행 내에서 항목을 정렬 하려면 코드의 속성입니다.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성은 무시됩니다.  
  
-   에 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 검사할 수 이벤트는 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 속성 항목의 주에 배치 되었는지 여부를 확인 하 <xref:System.Windows.Forms.ToolStrip> 맞지 않는지 합니다.  
  
-   그립 렌더링 되지 않습니다 따라서 및는 <xref:System.Windows.Forms.ToolStrip> 에 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 레이아웃 스타일의는 <xref:System.Windows.Forms.ToolStripPanel> 이동할 수 없습니다.  
  
-   <xref:System.Windows.Forms.ToolStrip> 오버플로 단추 렌더링 되지 않습니다 및 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 는 무시 됩니다.  
  
##### <a name="table-layout"></a>표 레이아웃  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> 레이아웃에 대 한 기본값은 <xref:System.Windows.Forms.StatusStrip>합니다. 비슷합니다 <xref:System.Windows.Forms.TableLayoutPanel>합니다. 기능 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 레이아웃은 다음과 같습니다.  
  
-   모든 기능을 <xref:System.Windows.Forms.TableLayoutPanel> 에 의해 노출 되는 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> 속성입니다. 캐스팅 해야는 <xref:System.Windows.Forms.LayoutSettings> 클래스는 <xref:System.Windows.Forms.TableLayoutSettings> 클래스입니다.  
  
-   사용할 수는 <xref:System.Windows.Forms.ToolStripItem.Dock%2A> 및 <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> 표 셀 내의 항목에 코드의 속성입니다.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성은 무시됩니다.  
  
-   에 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 검사할 수 이벤트는 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 속성 항목의 주에 배치 되었는지 여부를 확인 하 <xref:System.Windows.Forms.ToolStrip> 맞지 않는지 합니다.  
  
-   그립 렌더링 되지 않습니다 따라서 및는 <xref:System.Windows.Forms.ToolStrip> 에 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> 레이아웃 스타일의는 <xref:System.Windows.Forms.ToolStripPanel> 이동할 수 없습니다.  
  
-   <xref:System.Windows.Forms.ToolStrip> 오버플로 단추 렌더링 되지 않습니다 및 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 는 무시 됩니다.  
  
## <a name="toolstripitem"></a>ToolStripItem  
 다음 항목에서는 <xref:System.Windows.Forms.ToolStripItem> 및 파생 된 컨트롤입니다.  
  
 <xref:System.Windows.Forms.ToolStripItem> 로 이동 하는 모든 항목에 대 한 추상 기본 클래스는 <xref:System.Windows.Forms.ToolStrip>합니다. 다음 개체 모델에서는 <xref:System.Windows.Forms.ToolStripItem> 상속 계층 구조입니다.  
  
 ![ToolStripItem 개체 모델](../../../../docs/framework/winforms/controls/media/toolstripitemobjectmodel.gif "ToolStripItemObjectModel")  
ToolStripItem 개체 모델  
  
 <xref:System.Windows.Forms.ToolStripItem> 클래스에서 직접 상속 되거나 <xref:System.Windows.Forms.ToolStripItem>, 이러한에서 간접적으로 상속 또는 <xref:System.Windows.Forms.ToolStripItem> 통해 <xref:System.Windows.Forms.ToolStripControlHost> 또는 <xref:System.Windows.Forms.ToolStripDropDownItem>합니다.  
  
 <xref:System.Windows.Forms.ToolStripItem> 컨트롤에 포함 되어야 합니다는 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, 또는 <xref:System.Windows.Forms.ContextMenuStrip> 폼에 직접 추가할 수 없습니다. 컨테이너의 다양 한 클래스는의 적절 한 하위 집합을 포함 하도록 설계 <xref:System.Windows.Forms.ToolStripItem> 컨트롤입니다.  
  
 다음 표에서 스톡 <xref:System.Windows.Forms.ToolStripItem> 컨트롤과를 잘 컨테이너입니다. 하지만 모든 <xref:System.Windows.Forms.ToolStrip> 하나에서 항목을 호스팅할 수 있습니다 <xref:System.Windows.Forms.ToolStrip>-컨테이너, 파생 된 이러한 항목은 다음 컨테이너에서 품질이 향상 하도록 설계 되었습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripDropDown> 디자이너 도구 상자에 나타나지 않습니다.  
  
|포함 된 항목|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|  
|--------------------|---------------|---------------|----------------------|-----------------|-----------------------|  
|<xref:System.Windows.Forms.ToolStripButton>|예|아니요|아니요|아니요|예|  
|<xref:System.Windows.Forms.ToolStripComboBox>|예|예|예|아니요|예|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|예|아니요|아니요|예|예|  
|<xref:System.Windows.Forms.ToolStripLabel>|예|아니요|아니요|예|예|  
|<xref:System.Windows.Forms.ToolStripSeparator>|예|예|예|아니요|예|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|예|아니요|아니요|예|예|  
|<xref:System.Windows.Forms.ToolStripTextBox>|예|예|예|아니요|예|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|아니요|예|예|아니요|아니요|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|아니요|아니요|아니요|예|아니요|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|예|아니요|아니요|예|아니요|  
|<xref:System.Windows.Forms.ToolStripControlHost>|예|예|아니요|예|예|  
  
### <a name="toolstripbutton"></a>ToolStripButton  
 <xref:System.Windows.Forms.ToolStripButton> 단추 항목이 <xref:System.Windows.Forms.ToolStrip>합니다. 다양 한 테두리 스타일으로 표시 하 고 표시 하 고 작동 상태를 활성화를 사용할 수 있습니다. 기본적으로 포커스를 가지도록 정의할 수 있습니다.  
  
### <a name="toolstriplabel"></a>ToolStripLabel  
 <xref:System.Windows.Forms.ToolStripLabel> 에 레이블 기능을 제공 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다. <xref:System.Windows.Forms.ToolStripLabel> 비슷합니다는 <xref:System.Windows.Forms.ToolStripButton> 기본적으로 포커스를 받지 않고 및 푸시 되거나 강조 표시 된로 렌더링 하지 않습니다.  
  
 <xref:System.Windows.Forms.ToolStripLabel> 호스팅된 항목으로 선택 키를 지원합니다.  
  
 사용 하 여는 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>, 및 <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> 속성에는 <xref:System.Windows.Forms.ToolStripLabel> 에서 링크 컨트롤을 지원 하기 위해는 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel  
 <xref:System.Windows.Forms.ToolStripStatusLabel> 버전이 <xref:System.Windows.Forms.ToolStripLabel> 에 사용할 수 있도록 설계 된 <xref:System.Windows.Forms.StatusStrip>합니다. 특수 기능에는 <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>, 및 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>합니다.  
  
### <a name="toolstripseparator"></a>ToolStripSeparator  
 <xref:System.Windows.Forms.ToolStripSeparator> 도구 모음이 나 메뉴 방향에 따라에 세로 또는 가로 줄을 추가 합니다. 메뉴에서와 같이 항목 간의 구분 또는 그룹을 제공합니다.  
  
 추가할 수는 <xref:System.Windows.Forms.ToolStripSeparator> 드롭 다운 목록에서 선택 하 여 디자인 타임에 있습니다. 그러나 하면 자동으로 만들 수는 <xref:System.Windows.Forms.ToolStripSeparator> 디자이너 템플릿 노드 또는 하이픈 (-)를 입력 하 여는 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 메서드.  
  
### <a name="toolstripcontrolhost"></a>ToolStripControlHost  
 <xref:System.Windows.Forms.ToolStripControlHost> 에 대 한 추상 기본 클래스 <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox>, 및 <xref:System.Windows.Forms.ToolStripProgressBar>합니다. <xref:System.Windows.Forms.ToolStripControlHost> 사용자 지정 컨트롤을 포함 하 여 두 가지 방법으로 다른 컨트롤을 호스트할 수 있습니다.  
  
-   생성 된 <xref:System.Windows.Forms.ToolStripControlHost> 에서 파생 된 클래스와 함께 <xref:System.Windows.Forms.Control>합니다. 호스팅된 컨트롤 및 속성에 완벽 하 게 액세스 하려면 캐스팅 해야 합니다는 <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> 속성을 실제 클래스로 나타냅니다.  
  
-   확장 <xref:System.Windows.Forms.ToolStripControlHost>, 상속 된 클래스의 기본 생성자에서 파생 되는 클래스를 전달 하 여 기본 클래스 생성자를 호출 하 고 <xref:System.Windows.Forms.Control>합니다. 이 옵션을 사용 하면 일반적인 컨트롤의 메서드 및 속성에 쉽게 액세스할 수를 래핑하는 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
### <a name="toolstripcombobox"></a>ToolStripComboBox  
 <xref:System.Windows.Forms.ToolStripComboBox> 이 <xref:System.Windows.Forms.ComboBox> 에서 호스팅에 대해 최적화는 <xref:System.Windows.Forms.ToolStrip>합니다. 호스팅된 컨트롤의 속성 및 이벤트의 하위 집합에서 노출 된 <xref:System.Windows.Forms.ToolStripComboBox> 수준, 하지만 기본 <xref:System.Windows.Forms.ComboBox> 컨트롤을 통해 모두 액세스할 수는 <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> 속성.  
  
### <a name="toolstriptextbox"></a>ToolStripTextBox  
 <xref:System.Windows.Forms.ToolStripTextBox> 이 <xref:System.Windows.Forms.TextBox> 에서 호스팅에 대해 최적화는 <xref:System.Windows.Forms.ToolStrip>합니다. 호스팅된 컨트롤의 속성 및 이벤트의 하위 집합에서 노출 된 <xref:System.Windows.Forms.ToolStripTextBox> 수준, 하지만 기본 <xref:System.Windows.Forms.TextBox> 컨트롤을 통해 모두 액세스할 수는 <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> 속성.  
  
### <a name="toolstripprogressbar"></a>ToolStripProgressBar  
 <xref:System.Windows.Forms.ToolStripProgressBar> 이 <xref:System.Windows.Forms.ProgressBar> 에서 호스팅에 대해 최적화는 <xref:System.Windows.Forms.ToolStrip>합니다. 호스팅된 컨트롤의 속성 및 이벤트의 하위 집합에서 노출 된 <xref:System.Windows.Forms.ToolStripProgressBar> 수준, 하지만 기본 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 통해 모두 액세스할 수는 <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> 속성.  
  
### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem  
 <xref:System.Windows.Forms.ToolStripDropDownItem> 에 대 한 추상 기본 클래스 <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton>, 및 <xref:System.Windows.Forms.ToolStripSplitButton>, 직접 항목 또는 드롭 다운 컨테이너의 호스트 추가 항목을 호스팅할 수 있습니다. 설정 하 여이 작업을 수행는 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> 속성을는 <xref:System.Windows.Forms.ToolStripDropDown> 설정는 <xref:System.Windows.Forms.ToolStrip.Items%2A> 의 속성은 <xref:System.Windows.Forms.ToolStripDropDown>합니다. 이러한 드롭다운 목록 항목을 통해 직접 액세스는 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> 속성입니다.  
  
### <a name="toolstripmenuitem"></a>ToolStripMenuItem  
 <xref:System.Windows.Forms.ToolStripMenuItem> 이 <xref:System.Windows.Forms.ToolStripDropDownItem> 함께 작동 하 <xref:System.Windows.Forms.ToolStripDropDownMenu> 및 <xref:System.Windows.Forms.ContextMenuStrip> 메뉴에 대 한 특별 한 강조 표시, 레이아웃 및 열 정렬을 처리 하기.  
  
### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton  
 <xref:System.Windows.Forms.ToolStripDropDownButton> 다음과 같은 <xref:System.Windows.Forms.ToolStripButton>, 하지만 사용자가 클릭 하면 드롭다운 영역을 표시 합니다. 설정 하 여 드롭다운 화살표를 표시 또는 숨기기는 <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> 속성입니다. <xref:System.Windows.Forms.ToolStripDropDownButton> 호스트는 <xref:System.Windows.Forms.ToolStripOverflowButton> 오버플로 하는 항목을 표시 하는 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
### <a name="toolstripsplitbutton"></a>ToolStripSplitButton  
 <xref:System.Windows.Forms.ToolStripSplitButton> 단추 및 드롭다운 단추 기능을 결합합니다.  
  
 사용 하 여는 <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> 동기화 하는 속성의 <xref:System.Windows.Forms.Control.Click> 단추에 표시 되는 항목으로 선택된 드롭다운 목록 항목의 이벤트입니다.  
  
### <a name="toolstripitem-generic-features"></a>ToolStripItem 일반 기능  
 <xref:System.Windows.Forms.ToolStripItem> 다음과 같은 제네릭 기능 및 옵션을 상속 하는 컨트롤을 제공 합니다.  
  
-   코어 이벤트  
  
-   이미지 처리  
  
-   맞춤  
  
-   텍스트와 이미지의 관계  
  
-   표시 스타일  
  
#### <a name="core-events"></a>코어 이벤트  
 <xref:System.Windows.Forms.ToolStripItem> 컨트롤 자신의 클릭, 마우스 및 그리기 이벤트를 수신 및 일부 키보드 전처리도 수행할 수 있습니다.  
  
#### <a name="image-handling"></a>이미지 처리  
 <xref:System.Windows.Forms.ToolStripItem.Image%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A>, 및 <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> 속성 이미지 처리의 다양 한 측면은 관련이 있습니다. 이미지를 사용 하 여 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 실행 시간 – 전용를 설정 하거나 이러한 속성을 직접 설정 하 여 <xref:System.Windows.Forms.ToolStrip.ImageList%2A> 속성입니다.  
  
 속성에 둘 다와의 상호 작용에 의해 결정 됩니다 이미지 크기 조정 <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.ToolStripItem>다음과 같이 합니다.  
  
-   <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A> 이미지의 조합으로 결정 된 대로 최종 이미지의 소수 자릿수 <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> 설정 및 컨테이너의 <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> 설정 합니다.  
  
    -   경우 <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> 은 `true` (기본값) 및 <xref:System.Windows.Forms.ToolStripItemImageScaling> 은 <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>, 이미지 크기는 조정 없습니다 및 <xref:System.Windows.Forms.ToolStrip> 크기는 가장 큰 항목 또는 지정 된 최소 크기의 합니다.  
  
    -   경우 <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> 은 `false` 및 <xref:System.Windows.Forms.ToolStripItemImageScaling> 은 <xref:System.Windows.Forms.ToolStripItemImageScaling.None>, 모두 이미지 또는 <xref:System.Windows.Forms.ToolStrip> 조정 합니다.  
  
#### <a name="alignment"></a>맞춤  
 값은 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성의 끝을 결정는 <xref:System.Windows.Forms.ToolStrip> 항목이 나타나는 합니다. <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성이 작동 하는 경우에만의 레이아웃 스타일의 <xref:System.Windows.Forms.ToolStrip> 스택 오버플로 값 중 하나로 설정 됩니다.  
  
 항목이에 배치 되는 <xref:System.Windows.Forms.ToolStrip> Items 컬렉션에 항목이 표시 된 순서에서입니다. 항목으로 배치 되는 위치를 프로그래밍 방식으로 변경 하려면 사용 하 여는 <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> 메서드를 컬렉션에 항목을 이동 합니다. 이 메서드는 항목을 이동 하지만 복제 하지 않습니다.  
  
#### <a name="text-and-image-relationship"></a>텍스트 및 이미지 관계  
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> 속성의 텍스트와 관련 하 여 이미지의 상대 위치를 정의 <xref:System.Windows.Forms.ToolStripItem>합니다. 이미지, 텍스트 또는 둘 다 없는 항목 특별 한 경우로 취급 됩니다 되도록는 <xref:System.Windows.Forms.ToolStripItem> 누락 된 요소 또는 요소를 빈 곳을 표시 하지 않습니다.  
  
#### <a name="display-style"></a>표시 스타일  
 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 원하는 부분만 표시 하는 동안 항목의 텍스트 및 이미지 속성의 값을 설정할 수 있습니다. 이 각기 다른 컨텍스트에서 동일한 항목을 표시할 때 표시 스타일을 변경 하려면 일반적으로 사용 됩니다.  
  
## <a name="accessory-classes"></a>액세서리 클래스  
 다른 다양 한 기능을 제공 하는 클래스는 다음과 같습니다.  
  
-   <xref:System.Windows.Forms.ToolStripManager> 지원 <xref:System.Windows.Forms.ToolStrip>-관련 병합, 설정 및 렌더러 옵션 등의 전체 응용 프로그램에 대 한 작업입니다.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer> 특정 스타일이 나 테마를 적용할 수 있습니다는 <xref:System.Windows.Forms.ToolStrip> 쉽게 합니다.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 펜과 브러시 대체 가능한 색상표에 따라 만듭니다 (<xref:System.Windows.Forms.ProfessionalColorTable>).  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> 시스템 색과 평면 비주얼 스타일을 적용 <xref:System.Windows.Forms.ToolStrip> 응용 프로그램입니다.  
  
-   <xref:System.Windows.Forms.ToolStripContainer> 유사한 <xref:System.Windows.Forms.SplitContainer>합니다. 네 개의 가장자리 패널을 사용 하 여 (인스턴스의 <xref:System.Windows.Forms.ToolStripPanel>) 및 한 개의 중앙 패널 (인스턴스의 <xref:System.Windows.Forms.ToolStripContentPanel>) 일반적인 배열을 만드는 데 합니다. 왼쪽 패널 제거할 수 있지만 숨길 수 있습니다. 제거 하거나 중앙 패널을 숨길 수 있습니다. 하나 이상의 정렬할 수 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, 또는 <xref:System.Windows.Forms.StatusStrip> 측면 패널에서 컨트롤 다른 컨트롤에 대 한 중앙 패널을 사용할 수 있습니다. <xref:System.Windows.Forms.ToolStripContentPanel> 또한 일관 된 모양을 위해 폼의 본문으로 렌더러 지원을 받는 방법을 제공 합니다. <xref:System.Windows.Forms.ToolStripContainer> 다중 문서 인터페이스 MDI ()를 지원 하지 않습니다.  
  
-   <xref:System.Windows.Forms.ToolStripPanel> 이동 및 정렬에 대 한 공간을 제공 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다. 따라서 선택 하는 경우에 하나의 패널을 사용할 수 및 <xref:System.Windows.Forms.ToolStripPanel> MDI 시나리오에서 잘 작동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)  
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [MenuStrip 컨트롤](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [StatusStrip 컨트롤](../../../../docs/framework/winforms/controls/statusstrip-control.md)  
 [ContextMenuStrip 컨트롤](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)  
 [BindingNavigator 컨트롤](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)
