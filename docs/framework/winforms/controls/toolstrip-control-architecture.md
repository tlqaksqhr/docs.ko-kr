---
title: "ToolStrip 컨트롤 아키텍처 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ToolStrip 컨트롤[Windows Forms], 아키텍처"
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
caps.latest.revision: 32
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# ToolStrip 컨트롤 아키텍처
<xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.ToolStripItem> 클래스는 도구 모음, 상태 및 메뉴 항목을 표시하기 위한 융통성 있고 확장 가능한 시스템을 제공합니다.  이러한 클래스는 모두 <xref:System.Windows.Forms> 네임스페이스에 포함되어 있으며 일반적으로 <xref:System.Windows.Forms.ToolStripOverflow>와 같이 "ToolStrip" 접두사나 <xref:System.Windows.Forms.MenuStrip>과 같이 "Strip" 접미사가 포함된 이름이 지정됩니다.  
  
## ToolStrip  
 다음 항목에서는 <xref:System.Windows.Forms.ToolStrip>과 이 클래스에서 파생되는 컨트롤에 대해 설명합니다.  
  
 <xref:System.Windows.Forms.ToolStrip>은 <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip>의 추상 기본 클래스입니다.  다음 개체 모델은 <xref:System.Windows.Forms.ToolStrip> 상속 계층 구조를 보여 줍니다.  
  
 ![ToolStrip 개체 모델](../../../../docs/framework/winforms/controls/media/toolstripobjectmodel.png "ToolStripObjectModel")  
ToolStrip 개체 모델  
  
 <xref:System.Windows.Forms.ToolStrip>의 모든 항목에는 <xref:System.Windows.Forms.ToolStrip.Items%2A> 컬렉션을 통해 액세스할 수 있습니다.  <xref:System.Windows.Forms.ToolStripDropDownItem>의 모든 항목에는 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> 컬렉션을 통해 액세스할 수 있습니다.  <xref:System.Windows.Forms.ToolStrip>에서 파생된 클래스의 경우 <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> 속성을 사용하여 현재 표시된 항목에만 액세스할 수도 있습니다.  이는 현재 오버플로 메뉴에 있지 않은 항목입니다.  
  
 다음 항목은 모든 방향에서 <xref:System.Windows.Forms.ToolStripSystemRenderer> 및 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 모두와 자연스럽게 작동하도록 특별히 디자인되었습니다.  기본적으로 디자인 타임에 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 사용할 수 있습니다.  
  
-   <xref:System.Windows.Forms.ToolStripButton>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### MenuStrip  
 <xref:System.Windows.Forms.MenuStrip>은 <xref:System.Windows.Forms.MainMenu>를 대체하는 최상위 컨테이너로,  키 처리 및 MDI\(다중 문서 인터페이스\) 기능을 제공합니다.  <xref:System.Windows.Forms.ToolStripDropDownItem>과 <xref:System.Windows.Forms.ToolStripMenuItem>은 <xref:System.Windows.Forms.ToolStripItem>에서 파생되었지만 기능적으로 <xref:System.Windows.Forms.MenuStrip>과 함께 작동합니다.  
  
 다음 항목은 모든 방향에서 <xref:System.Windows.Forms.ToolStripSystemRenderer> 및 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 모두와 자연스럽게 작동하도록 특별히 디자인되었습니다.  기본적으로 디자인 타임에 <xref:System.Windows.Forms.MenuStrip> 컨트롤에 사용할 수 있습니다.  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### StatusStrip  
 <xref:System.Windows.Forms.StatusStrip>은 <xref:System.Windows.Forms.StatusBar> 컨트롤을 대체합니다.  <xref:System.Windows.Forms.StatusStrip>에는 사용자 지정 테이블 레이아웃, 폼의 크기 조정\/이동 그립 지원 및 <xref:System.Windows.Forms.ToolStripStatusLabel>이 사용 가능한 공간을 자동으로 채우도록 하는 `Spring` 속성과 같은 특수 기능이 포함되어 있습니다.  
  
 다음 항목은 모든 방향에서 <xref:System.Windows.Forms.ToolStripSystemRenderer> 및 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 모두와 자연스럽게 작동하도록 특별히 디자인되었습니다.  기본적으로 디자인 타임에 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 사용할 수 있습니다.  
  
-   <xref:System.Windows.Forms.ToolStripStatusLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripProgressBar>  
  
### ContextMenuStrip  
 <xref:System.Windows.Forms.ContextMenuStrip>은 <xref:System.Windows.Forms.ContextMenu> 대신 사용됩니다.  <xref:System.Windows.Forms.ContextMenuStrip>을 컨트롤과 연결할 수 있으며 마우스 오른쪽 단추를 클릭하면 상황에 맞는 메뉴\(바로 가기 메뉴\)가 자동으로 표시됩니다.  <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> 메서드를 사용하여 <xref:System.Windows.Forms.ContextMenuStrip>을 프로그래밍 방식으로 표시할 수도 있습니다.  <xref:System.Windows.Forms.ContextMenuStrip>은 동적 채우기 및 여러 번 클릭 시나리오를 처리할 수 있도록 취소 가능한 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 및 <xref:System.Windows.Forms.ToolStripDropDown.Closing> 이벤트를 지원합니다.  또한 <xref:System.Windows.Forms.ContextMenuStrip>은 이미지, 메뉴 항목 선택 상태, 텍스트, 선택키, 바로 가기 및 계단식 메뉴를 지원합니다.  
  
 다음 항목은 모든 방향에서 <xref:System.Windows.Forms.ToolStripSystemRenderer> 및 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 모두와 자연스럽게 작동하도록 특별히 디자인되었습니다.  기본적으로 디자인 타임에 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤에 사용할 수 있습니다.  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### ToolStrip 일반 기능  
 다음 항목에서는 <xref:System.Windows.Forms.ToolStrip> 및 파생된 컨트롤에 일반적인 기능과 동작을 설명합니다.  
  
#### 그리기  
 여러 가지 방법으로 <xref:System.Windows.Forms.ToolStrip> 컨트롤에서 사용자 지정 그리기를 수행할 수 있습니다.  <xref:System.Windows.Forms.ToolStrip>과 <xref:System.Windows.Forms.ToolStripItem>에는 다른 Windows Forms 컨트롤과 마찬가지로 재정의할 수 있는 `OnPaint` 메서드와 `Paint` 이벤트가 있습니다.  일반적인 그리기와 마찬가지로 좌표계는 컨트롤의 클라이언트 영역을 기준으로 합니다. 즉, 컨트롤의 왼쪽 위 모퉁이에 대한 좌표가 0, 0입니다.  <xref:System.Windows.Forms.ToolStripItem>의 `Paint` 이벤트와 `OnPaint` 메서드는 다른 컨트롤 그리기 이벤트와 마찬가지로 동작합니다.  
  
 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 사용하면 <xref:System.Windows.Forms.ToolStrip>의 배경, 항목 배경, 항목 이미지, 항목 화살표, 항목 텍스트 및 테두리를 그리기 위한 재정의 가능한 메서드가 포함된 <xref:System.Windows.Forms.ToolStripRenderer> 클래스를 통해 항목 및 컨테이너의 세부 렌더링 기능에 액세스할 수도 있습니다.  이러한 메서드의 이벤트 인수는 원하는 대로 조정할 수 있는 사각형, 색, 텍스트 서식 등의 몇 가지 속성을 노출합니다.  
  
 항목을 그리는 방식의 몇 가지 요소만 조정하려면 일반적으로 <xref:System.Windows.Forms.ToolStripRenderer>를 재정의합니다.  
  
 새 항목을 작성하고 그리기의 모든 요소를 제어하려면 `OnPaint` 메서드를 재정의합니다.  `OnPaint` 내에서 <xref:System.Windows.Forms.ToolStripRenderer>의 메서드를 사용할 수 있습니다.  
  
 기본적으로 <xref:System.Windows.Forms.ToolStrip>은 <xref:System.Windows.Forms.ControlStyles> 설정을 사용하여 이중 버퍼링됩니다.  
  
#### 부모 지정  
 <xref:System.Windows.Forms.ToolStrip> 컨트롤에서는 컨테이너의 소유권 및 부모 지정이라는 개념은 다른 Windows Forms 컨테이너 컨트롤에서보다 복잡합니다.  이 개념은 오버플로, 여러 <xref:System.Windows.Forms.ToolStrip> 항목 간의 드롭다운 항목 공유와 같은 동적 시나리오와 컨트롤에서 <xref:System.Windows.Forms.ContextMenuStrip> 생성을 지원하는 데 필요합니다.  
  
 다음 목록에서는 부모 지정과 관련된 멤버와 해당 멤버의 용도에 대해 설명합니다.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A>은 드롭다운 항목의 소스 항목에 액세스합니다.  이는 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>과 비슷하지만 컨트롤을 반환하는 대신 <xref:System.Windows.Forms.ToolStripItem>을 반환한다는 점이 다릅니다.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>은 여러 컨트롤에서 동일한 <xref:System.Windows.Forms.ContextMenuStrip>을 공유할 경우 <xref:System.Windows.Forms.ContextMenuStrip>의 소스에 해당하는 컨트롤을 확인합니다.  
  
-   <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A>는 <xref:System.Windows.Forms.ToolStripItem.Parent%2A> 속성에 대한 읽기 전용 접근자입니다.  부모는 반환된 현재 <xref:System.Windows.Forms.ToolStrip>을 나타낸다는 점에서 소유자와 다릅니다. 이 컨트롤은 항목을 표시하며 오버플로 영역에 있을 수 있습니다.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Owner%2A>는 항목 컬렉션에 현재 <xref:System.Windows.Forms.ToolStripItem>이 들어 있는 <xref:System.Windows.Forms.ToolStrip>을 반환합니다.  오버프로를 처리하는 특수 코드를 작성하지 않고 최상위 <xref:System.Windows.Forms.ToolStrip>의 <xref:System.Windows.Forms.ToolStrip.ImageList%2A>나 다른 속성을 참조하는 데는 이 속성이 가장 유용합니다.  
  
#### 상속된 컨트롤의 동작  
 다음 컨트롤은 상속에 사용될 때마다 잠깁니다.  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.ToolStripContainer>의 패널과 개별 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤이 포함된 <xref:System.Windows.Forms.ToolStripPanel>  
  
 예를 들어, 위 목록에 있는 컨트롤을 하나 이상 사용하여 새 Windows Forms 응용 프로그램을 만듭니다.  하나 이상의 컨트롤에 대한 액세스 수정자를 `public`이나 `protected`로 설정하고 프로젝트를 빌드합니다.  그런 다음 첫 번째 폼에서 상속되는 폼을 추가하고 상속된 컨트롤을 선택합니다.  그러면 액세스 수정자가 `private`일 때와 같이 컨트롤이 잠긴 것으로 나타납니다.  
  
#### ToolStripContainer의 상속 지원  
 <xref:System.Windows.Forms.ToolStripContainer> 컨트롤은 다음 예제와 유사한 제한된 상속 시나리오를 지원합니다.  
  
1.  새 Windows Forms 응용 프로그램을 만듭니다.  
  
2.  이 폼에 <xref:System.Windows.Forms.ToolStripContainer>를 추가합니다.  
  
3.  <xref:System.Windows.Forms.ToolStripContainer>의 액세스 한정자를 `public` 또는 `protected`로 설정합니다.  
  
4.  <xref:System.Windows.Forms.ToolStripContainer>의 <xref:System.Windows.Forms.ToolStripPanel> 영역에 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤의 조합을 추가합니다.  
  
5.  프로젝트를 빌드합니다.  
  
6.  첫 번째 폼에서 상속되는 폼을 추가합니다.  
  
7.  폼의 상속된 <xref:System.Windows.Forms.ToolStripContainer>를 선택합니다.  
  
#### 자식 컨트롤의 상속된 동작  
 위의 단계를 완료하면 다음과 같이 상속된 동작이 발생합니다.  
  
-   디자이너에서 컨트롤이 상속된 아이콘과 함께 표시됩니다.  
  
-   <xref:System.Windows.Forms.ToolStripPanel> 컨트롤이 잠겨 있으므로 이 컨트롤의 내용을 선택하거나 다시 정렬할 수 없습니다.  
  
-   <xref:System.Windows.Forms.ToolStripContentPanel>에 컨트롤을 추가하거나 컨트롤을 이동하거나 <xref:System.Windows.Forms.ToolStripContentPanel>의 자식 컨트롤로 만들 수 있습니다.  
  
-   폼을 빌드한 후에도 변경 내용은 유지됩니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.ToolStripContainer>에 포함된 모든 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤에서 액세스 한정자를 제거하십시오.  <xref:System.Windows.Forms.ToolStripContainer>의 액세스 한정자는 전체 컨트롤을 제어합니다.  
  
#### 부분 신뢰  
 부분 신뢰 상태에서 `ToolStrip` 제한은 권한이 없는 사용자나 서비스가 사용할 수도 있는 개인 정보를 실수로 입력하는 것을 방지하기 위한 것입니다.  이를 보호하는 방법은 다음과 같습니다.  
  
-   `ToolStripDropDown` 컨트롤은 <xref:System.Security.Permissions.UIPermissionWindow>가 있어야 <xref:System.Windows.Forms.ToolStripControlHost>에 항목을 표시할 수 있습니다.  이 제한은 <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripProgressBar> 등의 내장 컨트롤과 사용자가 만든 컨트롤 모두에 적용됩니다.  이 요구 사항이 충족되지 않으면 이러한 항목이 표시되지 않습니다.  예외가 throw되지 않습니다.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> 속성을 `false`로 설정할 수 없으며 취소 가능한 <xref:System.Windows.Forms.ToolStripDropDown.Closing> 이벤트 매개 변수는 무시됩니다.  따라서 드롭다운 항목을 닫지 않으면 둘 이상의 키를 입력할 수 없습니다.  이 요구 사항이 충족되지 않으면 이러한 항목이 표시되지 않습니다.  예외가 throw되지 않습니다.  
  
-   많은 키 입력 처리 이벤트가 <xref:System.Security.Permissions.UIPermissionWindow> 이외의 부분 신뢰 컨텍스트에서는 발생하지 않습니다.  
  
-   <xref:System.Security.Permissions.UIPermissionWindow>가 부여되지 않은 경우 선택키가 처리되지 않습니다.  
  
#### 용도  
 다음 사용 패턴은 <xref:System.Windows.Forms.ToolStrip> 레이아웃, 키보드 상호 작용 및 최종 사용자 동작과 관계가 있습니다.  
  
-   <xref:System.Windows.Forms.ToolStripPanel>에 결합  
  
     <xref:System.Windows.Forms.ToolStripPanel> 내와 여러 <xref:System.Windows.Forms.ToolStripPanel>에서 <xref:System.Windows.Forms.ToolStrip>의 위치를 변경할 수 있습니다.  `Dock` 속성이 무시되고 <xref:System.Windows.Forms.ToolStrip.Stretch%2A> 속성이 `false`인 경우 <xref:System.Windows.Forms.ToolStripPanel>에 항목이 추가됨에 따라 <xref:System.Windows.Forms.ToolStrip>의 크기가 증가합니다.  일반적으로 <xref:System.Windows.Forms.ToolStrip>은 탭 순서에 포함되지 않습니다.  
  
-   도킹  
  
     <xref:System.Windows.Forms.ToolStrip>은 컨테이너 한 쪽의 고정 위치에 배치되며 크기는 해당 컨트롤이 도킹된 전체 가장자리 크기에 맞게 늘어납니다.  일반적으로 <xref:System.Windows.Forms.ToolStrip>은 탭 순서에 포함되지 않습니다.  
  
-   절대 위치  
  
     <xref:System.Windows.Forms.ToolStrip>은 <xref:System.Windows.Forms.Control.Location%2A> 속성에 따라 배치되고 고정 크기이며 일반적으로 탭 순서에 포함된다는 점에서 다른 컨트롤과 비슷합니다.  
  
#### 키보드 상호 작용  
  
##### 선택키  
 키보드를 사용하여 컨트롤을 활성화하는 한 가지 방법으로 선택키를 Alt 키와 함께 또는 Alt 키 다음에 사용할 수 있습니다.  <xref:System.Windows.Forms.ToolStrip>은 명시적 선택키와 암시적 선택키를 모두 지원합니다.  명시적 정의에서는 문자 앞에 앰퍼샌드\(&\) 문자를 사용합니다.  암시적 정의에서는 지정된 `Text` 속성의 문자 순서에 따라 일치하는 항목을 찾는 알고리즘을 사용합니다.  
  
##### 바로 가기 키  
 <xref:System.Windows.Forms.MenuStrip>에서 사용되는 바로 가기 키를 정의하는 데는 <xref:System.Windows.Forms.Keys> 열거형\(순서 관계없음\)의 조합이 사용됩니다.  <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> 속성을 사용하여 "Delete" 대신 "Del"을 표시하는 등 텍스트만 포함된 바로 가기 키를 표시할 수도 있습니다.  
  
##### 탐색  
 Alt 키는 <xref:System.Windows.Forms.Form.MainMenuStrip%2A>이 가리키는 <xref:System.Windows.Forms.MenuStrip>을 활성화합니다.  여기에서 Ctrl\+Tab을 누르면 `ToolStripPanel`에 있는 <xref:System.Windows.Forms.ToolStrip> 컨트롤 사이를 탐색할 수 있습니다.  Tab 키와 숫자 키패드의 아래쪽 화살표를 누르면 <xref:System.Windows.Forms.ToolStrip>에 있는 항목 사이를 탐색할 수 있습니다.  특수한 알고리즘이 오버플로 영역의 탐색을 처리합니다.  스페이스바는 <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton> 또는 <xref:System.Windows.Forms.ToolStripSplitButton>을 선택합니다.  
  
##### 포커스 및 유효성 검사  
 <xref:System.Windows.Forms.MenuStrip>이나 <xref:System.Windows.Forms.ToolStrip>은 Alt 키에 의해 활성화되어도 현재 포커스가 있는 컨트롤에서 포커스를 가져오지 않고 제거하지도 않습니다.  <xref:System.Windows.Forms.MenuStrip> 내에서 호스팅되는 컨트롤이나 <xref:System.Windows.Forms.MenuStrip>의 드롭다운이 있는 경우 사용자가 Tab 키를 누르면 해당 컨트롤이 포커스를 얻게 됩니다.  일반적으로 <xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.Control.GotFocus>, <xref:System.Windows.Forms.Control.LostFocus>, <xref:System.Windows.Forms.Control.Enter> 및 <xref:System.Windows.Forms.Control.Leave> 이벤트는 키보드에 의해 해당 이베트가 활성화되어도 발생하지 않습니다.  이러한 경우 <xref:System.Windows.Forms.MenuStrip.MenuActivate> 및 <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> 이벤트를 대신 사용합니다.  
  
 <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A>의 기본값은 `false`입니다.  따라서 유효성 검사를 수행하려면 폼에서 <xref:System.Windows.Forms.ContainerControl.Validate%2A>를 명시적으로 호출해야 합니다.  
  
#### Layout  
 <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 속성이 있는 <xref:System.Windows.Forms.ToolStripLayoutStyle>의 멤버 중 하나를 선택하여 <xref:System.Windows.Forms.ToolStrip> 레이아웃을 제어할 수 있습니다.  
  
##### 스택 레이아웃  
 스택은 <xref:System.Windows.Forms.ToolStrip>의 양 끝에 항목을 나란히 정렬하는 것입니다.  다음 목록에서는 스택 레이아웃을 설명합니다.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle>가 기본값입니다.  이 설정을 사용하면 끌기 및 도킹 시나리오 처리를 위해 <xref:System.Windows.Forms.ToolStrip>의 레이아웃이 <xref:System.Windows.Forms.ToolStrip.Orientation%2A> 속성에 따라 자동으로 변경됩니다.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle>는 <xref:System.Windows.Forms.ToolStrip> 항목을 세로로 나란히 렌더링합니다.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle>는 <xref:System.Windows.Forms.ToolStrip> 항목을 가로로 나란히 렌더링합니다.  
  
##### 스택 레이아웃의 기타 기능  
 항목이 맞춰지는 <xref:System.Windows.Forms.ToolStrip>의 끝은 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>에 의해 결정됩니다.  
  
 항목이 <xref:System.Windows.Forms.ToolStrip>에 맞지 않으면 오버플로 단추가 자동으로 나타납니다.  <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 속성 설정에 따라 오버플로 영역에 항목이 항상 표시되는지, 필요한 경우에만 표시되는지, 아니면 아예 표시되지 않는지 결정됩니다.  
  
 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 이벤트에서 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 속성을 검사하여 항목이 주 <xref:System.Windows.Forms.ToolStrip>이나 오버플로 <xref:System.Windows.Forms.ToolStrip>에 배치되었는지, 아니면 아예 표시되지 않는지 확인할 수 있습니다.  일반적으로 항목이 주 <xref:System.Windows.Forms.ToolStrip>에 맞지 않고 해당 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 속성이 <xref:System.Windows.Forms.ToolStripItemOverflow>로 설정된 경우 항목이 표시되지 않습니다.  
  
 <xref:System.Windows.Forms.ToolStrip>을 <xref:System.Windows.Forms.ToolStripPanel>에 배치하고 해당 <xref:System.Windows.Forms.ToolStrip.GripStyle%2A>을 <xref:System.Windows.Forms.ToolStripGripStyle>로 설정하여 이동 가능하게 만듭니다.  
  
##### 기타 레이아웃 옵션  
 기타 레이아웃 옵션에는 <xref:System.Windows.Forms.ToolStripLayoutStyle> 및 <xref:System.Windows.Forms.ToolStripLayoutStyle>이 있습니다.  
  
##### 선형 레이아웃  
 <xref:System.Windows.Forms.ToolStripLayoutStyle> 레이아웃은 <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> 및 <xref:System.Windows.Forms.ToolStripOverflow>의 기본값이며  <xref:System.Windows.Forms.FlowLayoutPanel>과 유사합니다.  <xref:System.Windows.Forms.ToolStripLayoutStyle> 레이아웃의 기능은 다음과 같습니다.  
  
-   <xref:System.Windows.Forms.FlowLayoutPanel>의 모든 기능은 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> 속성에 의해 노출됩니다.  <xref:System.Windows.Forms.LayoutSettings> 클래스를 <xref:System.Windows.Forms.FlowLayoutSettings> 클래스로 캐스팅해야 합니다.  
  
-   코드에 <xref:System.Windows.Forms.ToolStripItem.Dock%2A> 속성과 <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> 속성을 사용하여 행 안에서 항목을 맞출 수 있습니다.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성은 무시됩니다.  
  
-   <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 이벤트에서 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 속성을 검사하여 항목이 주 <xref:System.Windows.Forms.ToolStrip>에 배치되었는지, 아니면 항목이 맞지 않는지 확인할 수 있습니다.  
  
-   그립은 렌더링되지 않으므로 <xref:System.Windows.Forms.ToolStripPanel>에서 <xref:System.Windows.Forms.ToolStripLayoutStyle> 레이아웃 스타일의 <xref:System.Windows.Forms.ToolStrip>을 이동할 수 없습니다.  
  
-   <xref:System.Windows.Forms.ToolStrip> 오버플로 단추는 렌더링되지 않으며 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>는 무시됩니다.  
  
##### 표 레이아웃  
 <xref:System.Windows.Forms.ToolStripLayoutStyle> 레이아웃은 <xref:System.Windows.Forms.StatusStrip>의 기본값이며  <xref:System.Windows.Forms.TableLayoutPanel>과 유사합니다.  <xref:System.Windows.Forms.ToolStripLayoutStyle> 레이아웃의 기능은 다음과 같습니다.  
  
-   <xref:System.Windows.Forms.TableLayoutPanel>의 모든 기능은 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> 속성에 의해 노출됩니다.  <xref:System.Windows.Forms.LayoutSettings> 클래스를 <xref:System.Windows.Forms.TableLayoutSettings> 클래스로 캐스팅해야 합니다.  
  
-   코드에 <xref:System.Windows.Forms.ToolStripItem.Dock%2A> 속성과 <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> 속성을 사용하여 표 셀 안에서 항목을 맞출 수 있습니다.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성은 무시됩니다.  
  
-   <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 이벤트에서 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 속성을 검사하여 항목이 주 <xref:System.Windows.Forms.ToolStrip>에 배치되었는지, 아니면 항목이 맞지 않는지 확인할 수 있습니다.  
  
-   그립은 렌더링되지 않으므로 <xref:System.Windows.Forms.ToolStripPanel>에서 <xref:System.Windows.Forms.ToolStripLayoutStyle> 레이아웃 스타일 상태인 <xref:System.Windows.Forms.ToolStrip>은 이동할 수 없습니다.  
  
-   <xref:System.Windows.Forms.ToolStrip> 오버플로 단추는 렌더링되지 않으며 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>는 무시됩니다.  
  
## ToolStripItem  
 다음 항목에서는 <xref:System.Windows.Forms.ToolStripItem>과 이 클래스에서 파생되는 컨트롤에 대해 설명합니다.  
  
 <xref:System.Windows.Forms.ToolStripItem>은 <xref:System.Windows.Forms.ToolStrip>에 포함되는 모든 항목에 대한 추상 기본 클래스입니다.  다음 개체 모델은 <xref:System.Windows.Forms.ToolStripItem> 상속 계층 구조를 보여 줍니다.  
  
 ![ToolStripItem 개체 모델](../../../../docs/framework/winforms/controls/media/toolstripitemobjectmodel.png "ToolStripItemObjectModel")  
ToolStripItem 개체 모델  
  
 <xref:System.Windows.Forms.ToolStripItem> 클래스는 <xref:System.Windows.Forms.ToolStripItem>에서 직접 상속되거나 <xref:System.Windows.Forms.ToolStripControlHost> 또는 <xref:System.Windows.Forms.ToolStripDropDownItem>을 통해 <xref:System.Windows.Forms.ToolStripItem>에서 간접적으로 상속됩니다.  
  
 <xref:System.Windows.Forms.ToolStripItem> 컨트롤은 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip> 또는 <xref:System.Windows.Forms.ContextMenuStrip>에 포함되어야 하며 폼에 직접 추가할 수 없습니다.  다양한 컨테이너 클래스가 <xref:System.Windows.Forms.ToolStripItem> 컨트롤의 적절한 하위 집합을 포함하도록 디자인되었습니다.  
  
 다음 표에서는 스톡 <xref:System.Windows.Forms.ToolStripItem> 컨트롤의 목록과 해당 컨트롤이 가장 잘 나타나는 컨테이너를 보여 줍니다.  모든 <xref:System.Windows.Forms.ToolStrip> 항목을 모든 <xref:System.Windows.Forms.ToolStrip> 파생 컨테이너에서 호스팅할 수 있지만 이 항목은 다음 컨테이너에서 가장 잘 나타나도록 디자인되었습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripDropDown>은 디자이너 도구 상자에 표시되지 않습니다.  
  
|포함된 항목|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|  
|------------|---------------|---------------|----------------------|-----------------|-----------------------|  
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
  
### ToolStripButton  
 <xref:System.Windows.Forms.ToolStripButton>은 <xref:System.Windows.Forms.ToolStrip>의 단추 항목입니다.  다양한 테두리 스타일로 단추 항목을 표시하고 이를 사용하여 작업 상태를 나타내거나 활성화할 수 있습니다.  기본적으로 포커스를 받도록 단추 항목을 정의할 수도 있습니다.  
  
### ToolStripLabel  
 <xref:System.Windows.Forms.ToolStripLabel>은 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 레이블 기능을 제공합니다.  <xref:System.Windows.Forms.ToolStripLabel>은 기본적으로 포커스를 받지 않고 누름 또는 선택 상태로 렌더링되지 않는다는 점에서 <xref:System.Windows.Forms.ToolStripButton>과 비슷합니다.  
  
 호스팅된 항목인 <xref:System.Windows.Forms.ToolStripLabel>은 선택키를 지원합니다.  
  
 <xref:System.Windows.Forms.ToolStrip>에서 링크 컨트롤을 지원하려면 <xref:System.Windows.Forms.ToolStripLabel>에 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 및 <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> 속성을 사용합니다.  
  
### ToolStripStatusLabel  
 <xref:System.Windows.Forms.ToolStripStatusLabel>은 <xref:System.Windows.Forms.ToolStripLabel>을 <xref:System.Windows.Forms.StatusStrip>에 사용하기 알맞게 변경한 것입니다.  이 컨트롤에는 <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A> 및 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>과 같은 특수 기능이 있습니다.  
  
### ToolStripSeparator  
 <xref:System.Windows.Forms.ToolStripSeparator>는 방향에 따라 도구 모음 또는 메뉴에 가로줄이나 세로줄을 추가합니다.  이 컨트롤은 메뉴에서와 같이 항목을 그룹화하거나 각 항목을 구분해 줍니다.  
  
 디자인 타임에 드롭다운 목록에서 <xref:System.Windows.Forms.ToolStripSeparator>를 선택하여 이 컨트롤을 추가할 수 있습니다.  그러나 디자이너 템플릿 노드나 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 메서드에서 하이픈\(\-\)을 입력하여 <xref:System.Windows.Forms.ToolStripSeparator>를 자동으로 만들 수도 있습니다.  
  
### ToolStripControlHost  
 <xref:System.Windows.Forms.ToolStripControlHost>은 <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox> 및 <xref:System.Windows.Forms.ToolStripProgressBar>의 추상 기본 클래스입니다.  <xref:System.Windows.Forms.ToolStripControlHost>에서는 사용자 지정 컨트롤을 비롯한 다른 컨트롤을 다음과 같은 두 가지 방법으로 호스팅할 수 있습니다.  
  
-   <xref:System.Windows.Forms.Control>에서 파생되는 클래스로 <xref:System.Windows.Forms.ToolStripControlHost>를 만듭니다.  호스팅된 컨트롤과 속성에 모두 액세스하려면 <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> 속성을 이 속성이 나타내는 실제 클래스로 다시 캐스팅해야 합니다.  
  
-   <xref:System.Windows.Forms.ToolStripControlHost>를 확장하고 상속된 클래스의 기본 생성자에서 <xref:System.Windows.Forms.Control>의 파생 클래스를 전달하여 기본 클래스 생성자를 호출합니다.  이 옵션을 사용하면 <xref:System.Windows.Forms.ToolStrip>에서 쉽게 액세스할 수 있도록 공용 컨트롤 메서드와 속성을 래핑할 수 있습니다.  
  
### ToolStripComboBox  
 <xref:System.Windows.Forms.ToolStripComboBox>는 <xref:System.Windows.Forms.ComboBox>를 <xref:System.Windows.Forms.ToolStrip>에서 호스팅하기 적합하게 수정한 것입니다.  호스팅된 컨트롤의 속성 및 이벤트 중 일부는 <xref:System.Windows.Forms.ToolStripComboBox> 수준에서 노출되지만 내부 <xref:System.Windows.Forms.ComboBox> 컨트롤은 <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> 속성을 통해 완전하게 액세스할 수 있습니다.  
  
### ToolStripTextBox  
 <xref:System.Windows.Forms.ToolStripTextBox>는 <xref:System.Windows.Forms.TextBox>를 <xref:System.Windows.Forms.ToolStrip>에서 호스팅하기 적합하게 수정한 것입니다.  호스팅된 컨트롤의 속성 및 이벤트 중 일부는 <xref:System.Windows.Forms.ToolStripTextBox> 수준에서 노출되지만 내부 <xref:System.Windows.Forms.TextBox> 컨트롤은 <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> 속성을 통해 완전하게 액세스할 수 있습니다.  
  
### ToolStripProgressBar  
 <xref:System.Windows.Forms.ToolStripProgressBar>는 <xref:System.Windows.Forms.ProgressBar>를 <xref:System.Windows.Forms.ToolStrip>에서 호스팅하기 적합하게 수정한 것입니다.  호스팅된 컨트롤의 속성 및 이벤트 중 일부는 <xref:System.Windows.Forms.ToolStripProgressBar> 수준에서 노출되지만 내부 <xref:System.Windows.Forms.ProgressBar> 컨트롤은 <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> 속성을 통해 완전하게 액세스할 수 있습니다.  
  
### ToolStripDropDownItem  
 <xref:System.Windows.Forms.ToolStripDropDownItem>은 <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton> 및 <xref:System.Windows.Forms.ToolStripSplitButton>의 추상 기본 클래스로서, 드롭다운 컨테이너에서 직접 항목을 호스팅하거나 추가 항목을 호스팅할 수 있습니다.  드롭다운 컨테이너에 추가 항목을 호스팅하는 작업은 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> 속성을 <xref:System.Windows.Forms.ToolStripDropDown>으로 설정하고 <xref:System.Windows.Forms.ToolStripDropDown>의 <xref:System.Windows.Forms.ToolStrip.Items%2A> 속성을 설정하여 수행할 수 있습니다.  이러한 드롭다운 항목은 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> 속성을 통해 직접 액세스할 수 있습니다.  
  
### ToolStripMenuItem  
 <xref:System.Windows.Forms.ToolStripMenuItem>은 메뉴의 특수 강조 표시, 레이아웃 및 열 배열을 처리하기 위해 <xref:System.Windows.Forms.ToolStripDropDownMenu> 및 <xref:System.Windows.Forms.ContextMenuStrip>과 함께 작동하는 <xref:System.Windows.Forms.ToolStripDropDownItem>입니다.  
  
### ToolStripDropDownButton  
 <xref:System.Windows.Forms.ToolStripDropDownButton>은 <xref:System.Windows.Forms.ToolStripButton>과 비슷하지만 사용자가 클릭하면 드롭다운 영역이 표시됩니다.  <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> 속성을 설정하여 드롭다운 화살표를 숨기거나 표시할 수 있습니다.  <xref:System.Windows.Forms.ToolStripDropDownButton>은 <xref:System.Windows.Forms.ToolStrip>에 표시되지 못한 항목을 표시하는 <xref:System.Windows.Forms.ToolStripOverflowButton>을 호스팅합니다.  
  
### ToolStripSplitButton  
 <xref:System.Windows.Forms.ToolStripSplitButton>은 단추 기능과 드롭다운 단추 기능을 결합한 것입니다.  
  
 선택한 드롭다운 항목의 <xref:System.Windows.Forms.Control.Click> 이벤트와 단추에 표시된 항목을 동기화하려면 <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> 속성을 사용합니다.  
  
### ToolStripItem 일반 기능  
 <xref:System.Windows.Forms.ToolStripItem>은 다음과 같은 일반 기능과 컨트롤 상속을 위한 옵션을 제공합니다.  
  
-   핵심 이벤트  
  
-   이미지 처리  
  
-   맞춤  
  
-   텍스트와 이미지의 관계  
  
-   표시 스타일  
  
#### 핵심 이벤트  
 <xref:System.Windows.Forms.ToolStripItem> 컨트롤은 해당 컨트롤의 클릭, 마우스 및 그리기 이벤트를 받으며 일부 키보드 전처리도 수행할 수 있습니다.  
  
#### 이미지 처리  
 <xref:System.Windows.Forms.ToolStripItem.Image%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A> 및 <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> 속성은 다양한 이미지 처리 특성과 관련이 있습니다.  이러한 속성을 직접 설정하거나 <xref:System.Windows.Forms.ToolStrip.ImageList%2A> 속성만 런타임에서 설정하여 <xref:System.Windows.Forms.ToolStrip> 컨트롤에서 이미지를 사용합니다.  
  
 이미지 크기 조정은 다음과 같이 <xref:System.Windows.Forms.ToolStrip>과 <xref:System.Windows.Forms.ToolStripItem>에서 속성이 상호 작용하여 결정됩니다.  
  
-   <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A>는 이미지의 <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> 설정과 컨테이너의 <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> 설정을 조합하여 조정된 최종 이미지의 크기입니다.  
  
    -   <xref:System.Windows.Forms.ToolStrip.AutoSize%2A>가 `true`\(기본값\)이고 <xref:System.Windows.Forms.ToolStripItemImageScaling>이 <xref:System.Windows.Forms.ToolStripItemImageScaling>인 경우 이미지 배율 조정은 발생하지 않으며 <xref:System.Windows.Forms.ToolStrip> 크기는 가장 큰 항목의 크기나 미리 지정된 최소 크기와 같게 됩니다.  
  
    -   <xref:System.Windows.Forms.ToolStrip.AutoSize%2A>가 `false`이고 <xref:System.Windows.Forms.ToolStripItemImageScaling>이 <xref:System.Windows.Forms.ToolStripItemImageScaling>인 경우 이미지가 표시되지 않고 <xref:System.Windows.Forms.ToolStrip> 배율오 조정되지 않습니다.  
  
#### 맞춤  
 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성의 값은 항목이 <xref:System.Windows.Forms.ToolStrip>의 어느 쪽 끝에 나타날지를 결정합니다.  <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성은 <xref:System.Windows.Forms.ToolStrip>의 레이아웃 스타일이 스택 오버플로 값 중 하나로 설정된 경우에만 작동합니다.  
  
 항목은 항목 컬렉션에 나타나는 순서대로 <xref:System.Windows.Forms.ToolStrip>에 배치됩니다.  항목이 배치되는 위치를 프로그래밍 방식으로 변경하려면 <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> 메서드를 사용하여 컬렉션의 항목을 이동합니다.  이 메서드는 항목을 복제하는 것이 아니라 이동합니다.  
  
#### 텍스트와 이미지의 관계  
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> 속성은 <xref:System.Windows.Forms.ToolStripItem>의 텍스트를 기준으로 이미지의 상대 위치를 정의합니다.  이미지, 텍스트 또는 둘 모두가 없는 항목의 경우 <xref:System.Windows.Forms.ToolStripItem>에서 누락된 요소에 대해 빈 영역이 표시되지 않도록 특수하게 처리됩니다.  
  
#### 표시 스타일  
 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>을 사용하면 항목의 텍스트 및 이미지 속성 값을 설정할 수 있을 뿐 아니라 원하는 항목만 표시할 수도 있습니다.  이 클래스는 일반적으로 동일한 항목을 각기 다른 컨텍스트에 표시할 때 표시 스타일을 변경하는 데 사용됩니다.  
  
## 부속 클래스  
 그 밖의 다양한 기능을 제공하는 클래스는 다음과 같습니다.  
  
-   <xref:System.Windows.Forms.ToolStripManager>는 전체 응용 프로그램에 대해 병합, 설정 및 렌더링 옵션과 같은 <xref:System.Windows.Forms.ToolStrip> 관련 작업을 지원합니다.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>는 <xref:System.Windows.Forms.ToolStrip>에 특정 스타일이나 테마를 손쉽게 적용할 수 있도록 합니다.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer>는 대체할 수 있는 색상표\(<xref:System.Windows.Forms.ProfessionalColorTable>\)를 기준으로 펜과 브러시를 만듭니다.  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer>는 <xref:System.Windows.Forms.ToolStrip> 응용 프로그램에 시스템 색과 평면 비주얼 스타일을 적용합니다.  
  
-   <xref:System.Windows.Forms.ToolStripContainer>는 <xref:System.Windows.Forms.SplitContainer>와 비슷합니다.  이 클래스에서는 네 개의 가장자리 패널\(<xref:System.Windows.Forms.ToolStripPanel>의 인스턴스\)과 한 개의 중앙 패널\(<xref:System.Windows.Forms.ToolStripContentPanel>의 인스턴스\)을 사용하여 일반적인 배열을 만듭니다.  가장자리 패널은 제거할 수 없지만 숨길 수는 있습니다.  중앙 패널을 제거할 수도 없고 숨길 수도 없습니다.  가장자리 패널에는 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> 또는 <xref:System.Windows.Forms.StatusStrip> 컨트롤을 하나 이상 배열할 수 있으며 다른 컨트롤에 대한 중앙 패널을 사용할 수 있습니다.  또한 <xref:System.Windows.Forms.ToolStripContentPanel>을 사용하면 폼 본문에 렌더러를 사용하여 일관된 모양을 유지할 수 있습니다.  <xref:System.Windows.Forms.ToolStripContainer>는 MDI\(다중 문서 인터페이스\)를 지원하지 않습니다.  
  
-   <xref:System.Windows.Forms.ToolStripPanel>은 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 이동 및 배열하기 위한 공간을 제공합니다.  필요한 경우 한 패널만 사용할 수 있습니다. <xref:System.Windows.Forms.ToolStripPanel>은 MDI 시나리오에서 제대로 작동합니다.  
  
## 참고 항목  
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)   
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)   
 [MenuStrip 컨트롤](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)   
 [StatusStrip 컨트롤](../../../../docs/framework/winforms/controls/statusstrip-control.md)   
 [ContextMenuStrip 컨트롤](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)   
 [BindingNavigator 컨트롤](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)