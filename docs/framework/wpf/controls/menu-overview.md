---
title: "Menu 개요 | Microsoft Docs"
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
  - "Menu 컨트롤"
  - "메뉴 컨트롤"
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Menu 개요
<xref:System.Windows.Controls.Menu> 클래스를 사용 하면 명령 및 계층적 순서로 이벤트 처리기와 관련 된 요소를 구성할 수 있습니다. 각 <xref:System.Windows.Controls.Menu> 의 컬렉션을 포함 하는 요소 <xref:System.Windows.Controls.MenuItem> 요소입니다.  
  
   
  
<a name="menu_control"></a>   
## <a name="menu-control"></a>Menu 컨트롤  
 <xref:System.Windows.Controls.Menu> 컨트롤에는 명령이 나 응용 프로그램에 대 한 옵션을 지정 하는 항목의 목록을 표시 합니다. 클릭 하면 일반적으로 <xref:System.Windows.Controls.MenuItem> 명령을 실행 하는 응용 프로그램 또는 하위 메뉴를 엽니다.  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>메뉴 만들기  
 다음 예제에서는 한 <xref:System.Windows.Controls.Menu> 텍스트를 조작 하는 <xref:System.Windows.Controls.TextBox>합니다. <xref:System.Windows.Controls.Menu> 포함 <xref:System.Windows.Controls.MenuItem> 사용 하는 개체는 <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, 및 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 속성 및 <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, 및 <xref:System.Windows.Controls.MenuItem.Click> 이벤트입니다.  
  
 [!code-xml[MenuItemCommandsAndEvents#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>바로 가기 키와 MenuItems  
 바로 가기 키를 호출 하는 키보드로 입력할 수 있는 문자 조합을 <xref:System.Windows.Controls.Menu> 명령입니다. 예를 들어 바로 가기를 **복사** 는 CTRL + C입니다. 두 가지 속성 바로 가기 키 및 메뉴 항목을 사용 하 여-<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> 또는 <xref:System.Windows.Controls.MenuItem.Command%2A>합니다.  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 다음 예제를 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> 키보드 바로 가기 텍스트를 할당 하는 속성 <xref:System.Windows.Controls.MenuItem> 컨트롤입니다. 이 바로 가기 메뉴 항목에만 배치합니다.  사용 하는 명령은 연결 하지는 않습니다는 <xref:System.Windows.Controls.MenuItem>합니다. 응용 프로그램 동작을 수행 하는 사용자 입력을 처리 해야 합니다.  
  
 [!code-xml[MenuEvent#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>명령  
 다음 예제를 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.MenuItem.Command%2A> 연결할 속성의 **열려** 및 **저장** 함께 명령의 <xref:System.Windows.Controls.MenuItem> 컨트롤입니다. Command 속성은 명령 연결 뿐만 아니라는 <xref:System.Windows.Controls.MenuItem>, 바로 가기로 사용 하 여 입력된 제스처 텍스트를 제공 합니다.  
  
 [!code-xml[MenuEvent#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <xref:System.Windows.Controls.MenuItem> 클래스에는 <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 은 명령이 발생 하는 요소를 지정 하는 속성입니다. 경우 <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 키보드 포커스가 있는 요소는 명령을 받은 설정 하지 않으면. 명령에 대 한 자세한 내용은 참조 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)합니다.  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>메뉴의 스타일 지정  
 컨트롤의 스타일을 변경할 수 있습니다 크게 모양 및 동작의 <xref:System.Windows.Controls.Menu> 사용자 지정 컨트롤을 작성 하지 않고도 컨트롤입니다. 시각적 속성을 설정 하는 것 외에도 적용할 수 있습니다는 <xref:System.Windows.Style> 컨트롤의 개별 부분에 속성을 통해 해당 컨트롤의 부분 동작을 변경 또는 추가 부분을 추가 또는 컨트롤의 레이아웃을 변경 합니다. 다음 예에서는 여러 가지 방법으로 추가할 수를 보여 줍니다.는 <xref:System.Windows.Style> 에 <xref:System.Windows.Controls.Menu> 제어 합니다.  
  
 첫 번째 코드 예제에서는 정의 <xref:System.Windows.Style> 라는 `Simple` 스타일에서 현재 시스템 설정을 사용 하는 방법을 보여 주는 합니다. 색을 할당 하는 코드는 `MenuHighlightBrush` 메뉴의 배경색으로 및 `MenuTextBrush` 메뉴의 전경색으로 합니다. 브러시를 할당 하는 리소스 키를 사용 하는 것을 확인 합니다.  
  
 [!code-xml[MenuStylesSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 다음 샘플에서는 <xref:System.Windows.Trigger> 의 모양을 변경할 수 있도록 하는 요소는 <xref:System.Windows.Controls.MenuItem> 에서 발생 하는 이벤트에 대 한 응답에서은 <xref:System.Windows.Controls.Menu>합니다. 위로 마우스를 이동 하면는 <xref:System.Windows.Controls.Menu>, 전경색 및 메뉴 항목의 글꼴 특성을 변경 합니다.  
  
 [!code-xml[MenuStylesSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>참고 항목  
 [WPF 컨트롤 갤러리 샘플](http://go.microsoft.com/fwlink/?LinkID=160053)