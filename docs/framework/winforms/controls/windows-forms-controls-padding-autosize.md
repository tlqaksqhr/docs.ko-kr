---
title: "연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Margin.Bottom"
  - "Margin.Left"
  - "Margin.Top"
  - "Margin.All"
  - "Margin.Right"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "AutoSize 속성, 연습"
  - "레이아웃[Windows Forms], 여백 및 안쪽 여백"
  - "Margin 속성[Windows Forms], 연습"
  - "Padding 속성[Windows Forms], 연습"
  - "연습[Windows Forms], 레이아웃"
  - "Windows Forms, 레이아웃"
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 28
---
# 연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃
많은 응용 프로그램에 있어 폼에 컨트롤을 정확하게 배치하는 작업은 매우 중요합니다.  **Windows Forms 디자이너**에서는 이러한 작업을 위한 여러 가지 레이아웃 도구를 제공합니다.  가장 중요한 세 가지 속성은 <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A> 및 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성이며, 이들 속성은 모든 Windows Forms 컨트롤에 있습니다.  
  
 <xref:System.Windows.Forms.Control.Margin%2A> 속성은 컨트롤 테두리에서 지정된 거리에 다른 컨트롤이 위치하도록 컨트롤 주위의 공간을 정의합니다.  
  
 <xref:System.Windows.Forms.Control.Padding%2A> 속성은 컨트롤 테두리에서 지정된 거리에 컨트롤 내용\(예: 해당 <xref:System.Windows.Forms.Control.Text%2A> 속성 값\)이 위치하도록 컨트롤 내부 공간을 정의합니다.  
  
 다음 그림에서는 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 및 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 보여 줍니다.  
  
 ![Windows Forms 컨트롤의 여백 및 안쪽 여백](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS\_WinFormPadMargin")  
  
 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 설정하면 컨트롤은 컨트롤의 내용에 맞게 자체적으로 크기를 자동 조정합니다.  이 경우 해당 컨트롤의 원래 <xref:System.Windows.Forms.Control.Size%2A> 속성 값보다 작게 크기가 조정되지는 않으며 해당 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성 값을 고려합니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   Windows Forms 프로젝트 만들기  
  
-   컨트롤에 여백 설정  
  
-   컨트롤에 안쪽 여백 설정  
  
-   컨트롤 크기 자동 조정  
  
 작업이 끝나면 이러한 중요한 레이아웃 기능이 수행하는 역할을 이해할 수 있게 됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음과 같은 요건이 필요합니다.  
  
-   Visual Studio가 설치된 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 만들고 실행할 수 있는 권한  
  
## 프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### 프로젝트를 만들려면  
  
1.  `LayoutExample`이라는 **Windows 응용 프로그램** 프로젝트를 만듭니다.  자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)을 참조하십시오.  
  
2.  **Windows Forms 디자이너**에서 폼을 선택합니다.  
  
## 컨트롤에 여백 설정  
 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 사용하여 컨트롤 간의 기본 거리를 설정할 수 있습니다.  컨트롤을 다른 컨트롤 가까이 이동할 때 두 컨트롤의 여백에 나타나는 맞춤선을 볼 수 있습니다.  또한 이동하는 컨트롤이 여백에서 정의된 거리에 맞춰집니다.  
  
#### Margin 속성을 사용하여 폼의 컨트롤을 정렬하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  <xref:System.Windows.Forms.Button> 컨트롤 중 하나를 선택하고 다른 컨트롤에 거의 닿을 때까지 가깝게 이동합니다.  
  
     이러한 컨트롤 사이에 나타나는 맞춤선을 확인합니다.  이 거리는 두 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 값을 합한 것입니다.  이동 중인 컨트롤이 이 거리에 맞춰집니다.  자세한 내용은 [연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)을 참조하십시오.  
  
3.  **속성** 창에서 <xref:System.Windows.Forms.Control.Margin%2A> 항목을 확장하고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 20으로 설정하여 컨트롤 중 하나의 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 변경합니다.  
  
4.  <xref:System.Windows.Forms.Button> 컨트롤 중 하나를 선택하고 다른 컨트롤 가까이 이동합니다.  
  
     여백 값의 합을 정의하는 맞춤선이 더 길기 때문에 컨트롤이 다른 컨트롤에서 더 먼 거리에 맞춰집니다.  
  
5.  **속성** 창에서 <xref:System.Windows.Forms.Control.Margin%2A> 항목을 확장하고 <xref:System.Windows.Forms.Padding.Top%2A> 속성을 5로 설정하여 선택한 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 변경합니다.  
  
6.  선택한 컨트롤을 다른 컨트롤의 아래쪽으로 이동합니다. 그러면 맞춤선이 더 짧아진 것을 확인할 수 있습니다.  선택한 컨트롤을 다른 컨트롤의 왼쪽으로 이동합니다. 그러면 맞춤선은 4단계에서 확인했던 값을 그대로 유지합니다.  
  
7.  <xref:System.Windows.Forms.Control.Margin%2A> 속성의 <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>을 각각 다른 값으로 설정하거나 이들 모두 <xref:System.Windows.Forms.Padding.All%2A> 속성 값과 동일한 값으로 설정할 수 있습니다.  
  
## 컨트롤에 안쪽 여백 설정  
 응용 프로그램에 필요한 정확한 레이아웃 작업을 수행하기 위해 컨트롤에 자식 컨트롤을 포함하는 경우가 있습니다.  자식 컨트롤의 테두리가 부모 컨트롤의 테두리에 가깝게 위치하도록 지정하려면 부모 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 자식 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성과 함께 사용합니다.  또한 <xref:System.Windows.Forms.Control.Padding%2A> 속성은 컨트롤 내용\(예: <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성\)이 해당 테두리에 가깝게 배치되도록 제어하는 데 사용됩니다.  
  
#### 안쪽 여백을 사용하여 폼의 컨트롤을 정렬하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 변경합니다.  
  
3.  **속성** 창에서 <xref:System.Windows.Forms.Control.Padding%2A> 항목을 확장하고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 5로 설정하여 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 변경합니다.  
  
     컨트롤이 확장되어 새 안쪽 여백에 공간이 생깁니다.  
  
4.  **도구 상자**의 <xref:System.Windows.Forms.GroupBox> 컨트롤을 폼으로 끌어 옵니다.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.GroupBox> 컨트롤로 끌어 옵니다.  <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.GroupBox> 컨트롤의 오른쪽 아래 모퉁이에 맞도록 이동합니다.  
  
     <xref:System.Windows.Forms.Button> 컨트롤이 <xref:System.Windows.Forms.GroupBox> 컨트롤의 아래쪽 테두리와 및 오른쪽 테두리에 가까워질 때 나타나는 맞춤선을 확인합니다.  이러한 맞춤선은 <xref:System.Windows.Forms.Button>의 <xref:System.Windows.Forms.Control.Margin%2A> 속성에 해당합니다.  
  
5.  **속성** 창에서 <xref:System.Windows.Forms.Control.Padding%2A> 항목을 확장하고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 20으로 설정하여 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 변경합니다.  
  
6.  <xref:System.Windows.Forms.GroupBox> 컨트롤에서 <xref:System.Windows.Forms.Button> 컨트롤을 선택하여 <xref:System.Windows.Forms.GroupBox>의 가운데로 이동합니다.  
  
     <xref:System.Windows.Forms.GroupBox> 컨트롤 테두리에서 보다 먼 거리에 맞춤선이 나타납니다.  이 거리는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성과 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 합한 것입니다.  
  
## 컨트롤 크기 자동 조정  
 일부 응용 프로그램에서는 런타임에서의 컨트롤 크기가 디자인 타임에서의 크기와 같지 않습니다.  <xref:System.Windows.Forms.Button> 컨트롤의 텍스트는 데이터베이스에서 가져올 수 있지만 그 길이를 미리 알 수 없습니다.  
  
 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성이 `true`로 설정되면 컨트롤은 해당 내용에 맞게 자체적으로 크기를 조정합니다.  자세한 내용은 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)를 참조하십시오.  
  
#### AutoSize 속성을 사용하여 폼의 컨트롤을 정렬하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 변경합니다.  
  
3.  <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 "이 단추는 해당 Text 속성에 대해 긴 문자열을 가집니다."로 변경합니다.  
  
     변경 내용을 커밋하면 <xref:System.Windows.Forms.Button> 컨트롤은 새 텍스트에 맞도록 자체적으로 크기를 조정합니다.  
  
4.  **도구 상자**의 다른 <xref:System.Windows.Forms.Button> 컨트롤을 폼으로 끌어 옵니다.  
  
5.  <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 "이 단추는 해당 Text 속성에 대해 긴 문자열을 가집니다."로 변경합니다.  
  
     변경 내용을 커밋하면 <xref:System.Windows.Forms.Button> 컨트롤은 자체적으로 크기를 조정하지 않으며 텍스트는 컨트롤의 오른쪽 가장자리에서 잘립니다.  
  
6.  **속성** 창에서 <xref:System.Windows.Forms.Control.Padding%2A> 항목을 확장하고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 5로 설정하여 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 변경합니다.  
  
     이 컨트롤의 안쪽에 있는 텍스트는 네 가장자리 모두에서 잘립니다.  
  
7.  <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 `true`로 설정합니다.  
  
     <xref:System.Windows.Forms.Button> 컨트롤은 자체적으로 크기를 조정하여 모든 문자열을 포함합니다.  또한 <xref:System.Windows.Forms.Button> 컨트롤이 네 방향 모두에서 확장되므로 안쪽 여백이 텍스트 주변에 추가됩니다.  
  
8.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 폼으로 끌어 옵니다.  폼의 오른쪽 아래 모퉁이 가까이에 이 컨트롤을 배치합니다.  
  
9. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 변경합니다.  
  
10. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 <xref:System.Windows.Forms.AnchorStyles>, <xref:System.Windows.Forms.AnchorStyles>으로 설정합니다.  
  
11. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 "이 단추는 해당 Text 속성에 대해 긴 문자열을 가집니다."로 변경합니다.  
  
     변경 내용을 커밋하면 <xref:System.Windows.Forms.Button> 컨트롤은 왼쪽으로 크기를 조정합니다.  일반적으로 자동 크기 조정은 해당 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 설정의 반대 방향으로 컨트롤의 크기를 늘립니다.  
  
## AutoSize 및 AutoSizeMode 속성  
 일부 컨트롤에서는 `AutoSizeMode` 속성을 지원하므로 컨트롤의 자동 크기 조정 동작을 보다 세밀하게 제어할 수 있습니다.  
  
#### AutoSizeMode 속성을 사용하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.Panel> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 설정합니다.  
  
3.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.Panel> 컨트롤로 끌어 옵니다.  
  
4.  <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.Panel> 컨트롤의 오른쪽 아래 모퉁이 가까이에 배치합니다.  
  
5.  <xref:System.Windows.Forms.Panel> 컨트롤을 선택하고 오른쪽 아래에 있는 크기 조정 핸들을 선택합니다.  <xref:System.Windows.Forms.Panel> 컨트롤의 크기를 크게 또는 작게 조정합니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.Panel> 컨트롤의 크기를 자유롭게 조정할 수 있지만 <xref:System.Windows.Forms.Button> 컨트롤의 오른쪽 아래 모퉁이의 위치보다 작게 크기를 조정할 수는 없습니다.  이 동작은 `AutoSizeMode` 속성의 기본값인 <xref:System.Windows.Forms.AutoSizeMode>에서 지정합니다.  
  
6.  <xref:System.Windows.Forms.Panel> 컨트롤의 `AutoSizeMode` 속성 값을 <xref:System.Windows.Forms.AutoSizeMode>로 설정합니다.  
  
     <xref:System.Windows.Forms.Panel> 컨트롤이 <xref:System.Windows.Forms.Button> 컨트롤을 포함하도록 자체적으로 크기를 조정합니다.  사용자가 <xref:System.Windows.Forms.Panel> 컨트롤의 크기를 조정할 수는 없습니다.  
  
7.  <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.Panel> 컨트롤의 왼쪽 아래 모퉁이로 끌어 옵니다.  
  
     <xref:System.Windows.Forms.Panel> 컨트롤의 크기가 <xref:System.Windows.Forms.Button> 컨트롤의 새 위치에 맞도록 조정됩니다.  
  
## 다음 단계  
 이 외에도 Windows Forms 응용 프로그램의 컨트롤을 정렬할 수 있는 레이아웃 기능에는 여러 가지가 있으며  이러한 기능을 다음과 같이 조합하여 사용할 수 있습니다.  
  
-   <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하여 폼을 작성합니다.  자세한 내용은 [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)을 참조하십시오.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성 값 및 해당 자식 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성 값을 변경합니다.  
  
-   <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤을 사용하여 위의 작업을 동일하게 수행합니다.  자세한 내용은 [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)을 참조하십시오.  
  
-   <xref:System.Windows.Forms.Panel> 컨트롤의 자식 컨트롤을 도킹해 봅니다.  <xref:System.Windows.Forms.Control.Padding%2A> 속성은 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> 속성을 보다 일반적으로 구현한 것이므로 <xref:System.Windows.Forms.Panel> 컨트롤에 자식 컨트롤을 배치하고 자식 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>로 설정하여 이러한 작업을 수행할 수 있습니다.  <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 여러 값으로 설정한 다음 그 결과를 확인합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Control.AutoSize%2A>   
 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>   
 <xref:System.Windows.Forms.Control.Margin%2A>   
 <xref:System.Windows.Forms.Control.Padding%2A>   
 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)