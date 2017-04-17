---
title: "연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], TableLayoutPanel을 사용하여 정렬"
  - "TableLayoutPanel 컨트롤[Windows Forms], 연습"
  - "Windows Forms 컨트롤, 정렬"
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 28
---
# 연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬
일부 응용 프로그램에서는 폼의 크기가 변경되거나 내용의 크기가 변경되면 그에 맞게 레이아웃이 적절하게 자동 정렬되는 폼이 필요합니다.  동적 레이아웃이 필요하며 코드에서 <xref:System.Windows.Forms.Control.Layout> 이벤트를 명시적으로 처리하지 않으려는 경우에는 레이아웃 패널을 사용해 보십시오.  
  
 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤 및 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 간단하게 폼에 컨트롤을 정렬하는 방법을 제공합니다.  두 컨트롤 모두 자식 컨트롤의 상대적 위치를 자동으로 제어하도록 구성할 수 있는 기능을 제공하고 런타임 시 동적 레이아웃 기능을 제공하므로 부모 폼의 크기가 변경되면 자식 컨트롤의 크기를 조정하고 위치를 변경할 수 있습니다.  레이아웃 패널을 레이아웃 패널 내에 중첩하여 복잡한 사용자 인터페이스를 만들 수 있습니다.  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>은 해당 내용을 가로 또는 세로 방향으로 정렬합니다.  내용을 한 행에서 다음 행으로 또는 한 열에서 다음 열로 줄 바꿈할 수 있습니다.  또는 내용을 줄 바꿈하지 않고 클리핑할 수 있습니다.  자세한 내용은 [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)을 참조하십시오.  
  
 <xref:System.Windows.Forms.TableLayoutPanel>은 해당 내용을 표에 정렬하며 HTML \<table\> 요소와 비슷한 기능을 제공합니다.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하면 개별 컨트롤의 위치를 정확하게 지정하지 않아도 모눈 레이아웃에 컨트롤을 배치할 수 있습니다.  해당 셀은 행 및 열에 정렬되며 셀의 크기가 다를 수 있습니다.  셀을 행 및 열에 병합할 수 있습니다.  셀에는 폼에 포함할 수 있는 모든 것을 포함할 수 있으며 다른 측면에서 컨테이너로 동작할 수 있습니다.  
  
 또한 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 런타임 시 비례적 크기 조정 기능을 제공하므로 폼 크기가 바뀌면 레이아웃이 변경될 수 있습니다.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 이러한 기능을 제공하므로 데이터 입력 폼 및 지역화된 응용 프로그램에 가장 적합합니다.  자세한 내용은 [Walkthrough: Creating a Resizable Windows Form for Data Entry](http://msdn.microsoft.com/ko-kr/e193b4fc-912a-4917-b036-b76c7a6f58ab) 및 [Walkthrough: Creating a Localizable Windows Form](http://msdn.microsoft.com/ko-kr/c5240b6e-aaca-4286-9bae-778a416edb9c)을 참조하십시오.  
  
 일반적으로 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 전체 레이아웃에 대한 컨테이너로 사용하지 마십시오.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하여 레이아웃 부분에 비례적 크기 조정 기능을 제공할 수 있습니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   Windows Forms 프로젝트 만들기  
  
-   행 및 열에 컨트롤 정렬  
  
-   행 및 열 속성 설정  
  
-   컨트롤로 행 및 열 확장  
  
-   오버플로 자동 처리  
  
-   도구 상자의 컨트롤을 두 번 클릭하여 삽입  
  
-   해당 윤곽선을 그려서 컨트롤 삽입  
  
-   다른 부모에 기존 컨트롤 다시 할당  
  
 작업이 끝나면 이러한 중요한 레이아웃 기능이 수행하는 역할을 이해할 수 있게 됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### 프로젝트를 만들려면  
  
1.  "TableLayoutPanelExample"이라고 하는 Windows 응용 프로그램 프로젝트를 만듭니다.  자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)을 참조하십시오.  
  
2.  **Windows** **Forms 디자이너**에서 폼을 선택합니다.  
  
## 행 및 열에 컨트롤 정렬  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하면 컨트롤을 행 및 열에 쉽게 정렬할 수 있습니다.  
  
#### TableLayoutPanel을 사용하여 행 및 열에 컨트롤을 정렬하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 폼으로 끌어 옵니다.  기본적으로 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에는 네 개의 셀이 있습니다.  
  
2.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤로 끌어서 셀 중 하나에 놓습니다.  <xref:System.Windows.Forms.Button> 컨트롤은 선택한 셀 내에 만들어집니다.  
  
3.  **도구 상자**에 있는 <xref:System.Windows.Forms.Button> 컨트롤을 세 개 더 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤로 끌면 나머지 세 개의 셀에 단추가 하나씩 포함됩니다.  
  
4.  두 열 사이의 세로 크기 조정 핸들을 선택하여 왼쪽으로 이동합니다.  첫 번째 열에 있는 <xref:System.Windows.Forms.Button> 컨트롤의 너비가 작게 조정되지만 두 번째 열에 있는 <xref:System.Windows.Forms.Button> 컨트롤의 크기는 바뀌지 않습니다.  
  
5.  두 열 사이의 세로 크기 조정 핸들을 선택하여 오른쪽으로 이동합니다.  첫 번째 열에 있는 <xref:System.Windows.Forms.Button> 컨트롤의 크기가 원래 크기로 돌아가지만 두 번째 열에 있는 <xref:System.Windows.Forms.Button> 컨트롤은 오른쪽으로 이동됩니다.  
  
6.  세로 크기 조정 핸들을 위 또는 아래로 이동하여 패널의 컨트롤에 미치는 영향을 확인합니다.  
  
## 도킹 및 고정 기능을 사용하여 셀 내에서 컨트롤 위치 지정  
 <xref:System.Windows.Forms.TableLayoutPanel>에서의 자식 컨트롤의 고정 동작은 다른 컨테이너 컨트롤에서의 고정 동작과 다릅니다.  자식 컨트롤의 도킹 동작은 다른 컨테이너 컨트롤에서의 도킹 동작과 같습니다.  
  
#### 셀 내에서 컨트롤 위치 지정  
  
1.  첫 번째 <xref:System.Windows.Forms.Button> 컨트롤을 선택합니다.  <xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle>로 변경합니다.  <xref:System.Windows.Forms.Button> 컨트롤이 해당 셀에 맞게 확장됩니다.  
  
2.  나머지 <xref:System.Windows.Forms.Button> 컨트롤 중 하나를 선택합니다.  <xref:System.Windows.Forms.Control.Anchor%2A> 속성의 값을 <xref:System.Windows.Forms.AnchorStyles>로 변경합니다.  컨트롤의 오른쪽 테두리가 셀의 오른쪽 테두리에 가깝게 이동됩니다.  테두리 사이의 간격은 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성과 패널의 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 합한 것입니다.  
  
3.  <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 <xref:System.Windows.Forms.AnchorStyles> 및 <xref:System.Windows.Forms.AnchorStyles>로 변경합니다.  <xref:System.Windows.Forms.Control.Margin%2A> 및 <xref:System.Windows.Forms.Control.Padding%2A> 값을 고려하여 컨트롤 크기가 셀 너비로 조정됩니다.  
  
4.  <xref:System.Windows.Forms.AnchorStyles> 및 <xref:System.Windows.Forms.AnchorStyles> 스타일에 대해 2단계와 3단계를 반복합니다.  
  
## 행 및 열 속성 설정  
 <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> 및 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 컬렉션을 사용하여 행 및 열의 개별 속성을 설정할 수 있습니다.  
  
#### 행 및 열 속성을 설정하려면  
  
1.  **Windows Forms 디자이너**에서 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 선택합니다.  
  
2.  **속성** 창에서 **Columns** 항목 옆에 있는 줄임표\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) 단추를 클릭하여 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 컬렉션을 엽니다.  
  
3.  첫 번째 열을 선택하고 해당 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성 값을 <xref:System.Windows.Forms.SizeType>로 변경합니다.  **확인**을 클릭하여 변경 내용을 적용합니다.  첫 번째 열의 너비가 <xref:System.Windows.Forms.Button> 컨트롤에 맞게 줄어드는지 확인합니다.  또한 열 너비를 조정할 수 없는지 확인합니다.  
  
4.  **속성** 창에서 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 컬렉션을 열고 첫 번째 열을 선택합니다.  <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성의 값을 <xref:System.Windows.Forms.SizeType>로 변경합니다.  **확인**을 클릭하여 변경 내용을 적용합니다.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 너비를 크게 변경하면 첫 번째 열의 너비가 확장됩니다.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 너비를 작게 변경하면 첫 번재 열의 단추가 셀에 맞게 조정됩니다.  또한 열 너비를 조정할 수 있습니다.  
  
5.  **속성** 창에서 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 컬렉션을 열고 나열된 열을 모두 선택합니다.  모든 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성의 값을 <xref:System.Windows.Forms.SizeType>로 설정합니다.  **확인**을 클릭하여 변경 내용을 적용합니다.  <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> 컬렉션에서도 이를 반복합니다.  
  
6.  모퉁이 크기 조정 핸들 중 하나를 선택하고 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 너비와 높이를 모두 조정합니다.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 크기가 변경되면 행 및 열 크기가 변경됩니다.  또한 가로 및 세로 크기 조정 핸들로 행 및 열 크기를 조정할 수 있습니다.  
  
## 컨트롤로 행 및 열 확장  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 여러 개의 새로운 속성을 디자인 타임에 컨트롤에 추가합니다.  이러한 속성 중 두 가지가 `RowSpan` 및 `ColumnSpan`입니다.  이러한 속성을 사용하여 컨트롤로 두 개 이상의 행이나 열을 확장할 수 있습니다.  
  
#### 컨트롤로 행 및 열을 확장하려면  
  
1.  첫 번째 행과 첫 번째 열에서 <xref:System.Windows.Forms.Button> 컨트롤을 선택합니다.  
  
2.  **속성** 창에서 `ColumnSpan` 속성의 값을 2로 변경합니다.  <xref:System.Windows.Forms.Button> 컨트롤은 첫 번째 열과 두 번째 열을 채웁니다.  또한 이러한 변경 사항을 적용할 수 있게 행이 추가됩니다.  
  
3.  `RowSpan` 속성에 대해 2단계를 반복합니다.  
  
## 도구 상자의 컨트롤을 두 번 클릭하여 삽입  
 **도구 상자**의 컨트롤을 두 번 클릭하여 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 채울 수 있습니다.  
  
#### 도구 상자의 컨트롤을 두 번 클릭하여 삽입하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  **도구 상자**에서 <xref:System.Windows.Forms.Button> 컨트롤 아이콘을 두 번 클릭합니다.  새 단추 컨트롤이 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 첫 번째 셀에 나타납니다.  
  
3.  **도구 상자**에서 여러 개의 컨트롤을 두 번 클릭합니다.  새 컨트롤이 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 빈 셀에 연속적으로 나타납니다.  또한 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 열려 있는 셀이 없는 경우 새 컨트롤을 적용할 수 있게 확장됩니다.  
  
## 오버플로 자동 처리  
 컨트롤을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 삽입할 때 새 컨트롤을 위한 빈 셀이 부족할 수 있습니다.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 셀 수를 늘려서 이러한 문제를 자동으로 처리합니다.  
  
#### 오버플로 자동 처리를 확인하려면  
  
1.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 빈 셀이 있는 경우 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤이 가득 찰 때까지 새 <xref:System.Windows.Forms.Button> 컨트롤을 계속 삽입합니다.  
  
2.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤이 가득 차면 **도구 상자**의 <xref:System.Windows.Forms.Button> 아이콘을 두 번 클릭하여 다른 <xref:System.Windows.Forms.Button> 컨트롤을 삽입합니다.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤이 새 컨트롤을 적용할 수 있게 새 셀을 만듭니다.  컨트롤을 몇 개 더 삽입하고 크기 조정 동작을 확인합니다.  
  
3.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> 속성 값을 <xref:System.Windows.Forms.TableLayoutPanelGrowStyle>로 변경합니다.  **도구 상자**의 <xref:System.Windows.Forms.Button> 아이콘을 두 번 클릭하여 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤이 가득 찰 때까지 <xref:System.Windows.Forms.Button> 컨트롤을 삽입합니다.  다시 **도구 상자**의 <xref:System.Windows.Forms.Button> 아이콘을 두 번 클릭합니다.  **Windows Forms 디자이너**에서 추가 행 및 열을 만들 수 없음을 알리는 오류 메시지가 표시됩니다.  
  
## 해당 윤곽선을 그려서 컨트롤 삽입  
 컨트롤을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 삽입하고 셀에 윤곽선을 그려서 크기를 지정할 수 있습니다.  
  
#### 해당 윤곽선을 그려서 컨트롤을 삽입하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  **도구 상자**에서 <xref:System.Windows.Forms.Button> 컨트롤 아이콘을 클릭합니다.  이 때 컨트롤을 폼으로 끌어 오지 마십시오.  
  
3.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 위에 마우스 포인터를 놓습니다.  포인터가 <xref:System.Windows.Forms.Button> 컨트롤 아이콘이 연결된 십자형으로 변경됩니다.  
  
4.  마우스 단추를 클릭한 채로 있습니다.  
  
5.  마우스 포인터를 끌어서 <xref:System.Windows.Forms.Button> 컨트롤의 윤곽선을 그립니다.  원하는 크기가 되면 마우스 단추를 놓습니다.  <xref:System.Windows.Forms.Button> 컨트롤이 컨트롤의 윤곽선을 그린 셀에 만들어집니다.  
  
## 셀 내에서 여러 컨트롤이 허용되지 않는 경우  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 셀마다 하나의 자식 컨트롤만 포함할 수 있습니다.  
  
#### 셀 내의 여러 컨트롤이 허용되지 않음을 보여 주려면  
  
-   **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤로 끌어서 사용된 셀 중 하나에 놓습니다.  이 때 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하여 <xref:System.Windows.Forms.Button> 컨트롤을 사용된 셀로 끌 수 없음을 알 수 있습니다.  
  
## 컨트롤 바꾸기  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하면 두 개의 다른 셀을 사용하는 컨트롤을 바꿀 수 있습니다.  
  
#### 컨트롤을 바꾸려면  
  
-   사용된 셀의 <xref:System.Windows.Forms.Button> 컨트롤 중 하나를 끌어서 사용된 다른 셀에 놓습니다.  두 개의 컨트롤이 한 셀에서 다른 셀로 이동됩니다.  
  
## 다음 단계  
 레이아웃 패널과 컨트롤을 조합하여 복잡한 레이아웃을 만들 수 있습니다.  다음과 같은 제안을 따르는 것이 좋습니다.  
  
-   <xref:System.Windows.Forms.Button> 컨트롤 중 하나의 크기를 크게 조정하고 레이아웃에 미치는 영향을 확인합니다.  
  
-   선택한 여러 컨트롤을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 붙여넣고 컨트롤이 어떻게 삽입되는지 확인합니다.  
  
-   레이아웃 패널에 다른 레이아웃 패널이 포함될 수 있습니다.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 기존 컨트롤로 끌어 놓아 보십시오.  
  
-   <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 부모 폼에 도킹합니다.  폼 크기를 조정하고 레이아웃에 미치는 영향을 확인합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Microsoft Windows User Experience, 사용자 인터페이스 개발자 및 디자이너를 위한 공식적인 지침서. Redmond, WA: Microsoft Press, 1999. \(USBN: 0\-7356\-0566\-1\)](http://www.microsoft.com/mspress/southpacific/books/book11588.htm)   
 [Walkthrough: Creating a Resizable Windows Form for Data Entry](http://msdn.microsoft.com/ko-kr/e193b4fc-912a-4917-b036-b76c7a6f58ab)   
 [Walkthrough: Creating a Localizable Windows Form](http://msdn.microsoft.com/ko-kr/c5240b6e-aaca-4286-9bae-778a416edb9c)   
 [TableLayoutPanel 컨트롤에 대한 유용한 정보](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)   
 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [방법: Windows Forms에 컨트롤 도킹](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)   
 [방법: Windows Forms에서 컨트롤 고정](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)   
 [연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)