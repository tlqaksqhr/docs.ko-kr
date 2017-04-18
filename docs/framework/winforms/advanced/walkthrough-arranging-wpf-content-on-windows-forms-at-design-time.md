---
title: "연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "상호 운용성[WPF]"
  - "Windows Forms, WPF 콘텐츠 고정 및 도킹"
  - "Windows Forms, 디자인 타임에 WPF 콘텐츠 정렬"
  - "WPF 콘텐츠[Windows Forms], 디자인 타임에 정렬"
  - "WPF 콘텐츠, Windows Forms에서 호스팅"
  - "WPF 사용자 정의 컨트롤[Windows Forms], 레이아웃 패널에 호스팅"
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬
이 연습에서는 기준 위치 지정 및 맞춤선과 같은 Windows Forms 레이아웃 기능을 사용하여 WPF\(Windows Presentation Foundation\) 컨트롤을 정렬하는 방법을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   프로젝트를 만듭니다.  
  
-   WPF 컨트롤을 만듭니다.  
  
-   레이아웃 패널에서 WPF 컨트롤을 호스트합니다.  
  
-   맞춤선을 사용하여 WPF 컨트롤을 맞춥니다.  
  
-   WPF 컨트롤을 고정 및 도킹합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## 프로젝트 만들기  
 첫 번째 단계에서는 Windows Forms 프로젝트를 만듭니다.  
  
> [!NOTE]
>  WPF 콘텐츠를 호스트하는 경우 C\# 및 Visual Basic 프로젝트만 지원됩니다.  
  
#### 프로젝트를 만들려면  
  
-   Visual Basic 또는 Visual C\#에서 `ArrangeElementHost`라는 새 Windows Forms 응용 프로그램 프로젝트를 만듭니다.  
  
## WPF 컨트롤 만들기  
 프로젝트에 WPF 컨트롤을 추가한 후 폼에 정렬할 수 있습니다.  
  
#### WPF 컨트롤을 만들려면  
  
1.  프로젝트에 새 WPF <xref:System.Windows.Controls.UserControl>을 추가합니다.  컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.  자세한 내용은 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)를 참조하세요.  
  
2.  디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.  자세한 내용은 [방법: 디자인 화면의 요소 선택 및 이동](http://msdn.microsoft.com/ko-kr/54cb70b6-b35b-46e4-a0cc-65189399c474)을 참조하세요.  
  
3.  **속성** 창에서 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성의 값을 `200`으로 설정합니다.  
  
4.  <xref:System.Windows.Controls.Control.Background%2A> 속성 값을 `Blue`로 설정합니다.  
  
5.  프로젝트를 빌드합니다.  
  
## 레이아웃 패널에서 WPF 컨트롤 호스트  
 다른 Windows Forms 컨트롤을 사용하는 것과 동일한 방식으로 레이아웃 패널에서 WPF 컨트롤을 사용할 수 있습니다.  
  
#### 레이아웃 패널에서 WPF 컨트롤을 호스트하려면  
  
1.  Windows Forms 디자이너에서 `Form1`을 엽니다.  
  
2.  **도구 상자**에서 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 폼으로 끌어 옵니다.  
  
3.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 스마트 태그 패널에서 **마지막 행 제거**를 선택합니다.  
  
4.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 더 큰 너비와 높이로 조정합니다.  
  
5.  **도구 상자**에서 `UserControl1`을 두 번 클릭하여 <xref:System.Windows.Forms.TableLayoutPanel>의 첫 번째 셀에 `UserControl1`의 인스턴스를 만듭니다.  
  
     `UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.  
  
6.  **도구 상자**에서 `UserControl1`을 두 번 클릭하여 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 두 번째 셀에 다른 인스턴스를 만듭니다.  
  
7.  **문서 개요** 창에서 `tableLayoutPanel1`을 선택합니다.  자세한 내용은 [Document Outline Window](http://msdn.microsoft.com/ko-kr/9054f2bc-f6f8-4242-9fe0-be71089b12f8)을 참조하세요.  
  
8.  **속성** 창에서 <xref:System.Windows.Forms.Control.Padding%2A> 속성의 값을 `10, 10, 10, 10`으로 설정합니다.  
  
     두 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 모두 새 레이아웃에 맞게 크기가 조정됩니다.  
  
## 맞춤선을 사용하여 WPF 컨트롤 맞춤  
 맞춤선을 사용하여 폼에서 컨트롤을 쉽게 맞출 수 있습니다.  맞춤선을 사용하여 WPF 컨트롤도 맞출 수 있습니다.  자세한 내용은 [연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)을 참조하세요.  
  
#### 맞춤선을 사용하여 WPF 컨트롤을 맞추려면  
  
1.  **도구 상자**에서 `UserControl1`의 인스턴스를 폼으로 끌어 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 아래 공간에 배치합니다.  
  
     `UserControl1` 인스턴스가 `elementHost3`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.  
  
2.  맞춤선을 사용하여 `elementHost3`의 왼쪽 가장자리를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 왼쪽 가장자리에 맞춥니다.  
  
3.  맞춤선을 사용하여 `elementHost3`의 크기를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤과 동일한 너비로 조정합니다.  
  
4.  가운데 맞춤선이 컨트롤 사이에 나타날 때까지 `elementHost3`을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 쪽으로 이동합니다.  
  
5.  **속성** 창에서 Margin 속성의 값을 `20, 20, 20, 20`으로 설정합니다.  
  
6.  가운데 맞춤선이 다시 나타날 때까지 `elementHost3`을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에서 멀리 이동합니다.  이제 가운데 맞춤선이 여백 20을 나타냅니다.  
  
7.  왼쪽 가장자리가 `elementHost1`의 왼쪽 가장자리와 맞춰질 때까지 `elementHost3`을 오른쪽으로 이동합니다.  
  
8.  오른쪽 가장자리가 `elementHost2`의 오른쪽 가장자리와 맞춰질 때까지 `elementHost3`의 너비를 변경합니다.  
  
## WPF 컨트롤 고정 및 도킹  
 폼에 호스트된 WPF 컨트롤은 다른 Windows Forms 컨트롤과 동일한 고정 및 도킹 동작을 갖습니다.  
  
#### WPF 컨트롤을 고정 및 도킹하려면  
  
1.  `elementHost1`를 선택합니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 **Top, Bottom, Left, Right**로 설정합니다.  
  
3.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 더 큰 크기로 조정합니다.  
  
     `elementHost1` 컨트롤의 크기가 조정되어 셀을 채웁니다.  
  
4.  `elementHost2`를 선택합니다.  
  
5.  **속성** 창에서 <xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle>로 설정합니다.  
  
     `elementHost2` 컨트롤의 크기가 조정되어 셀을 채웁니다.  
  
6.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 선택합니다.  
  
7.  <xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle>로 설정합니다.  
  
8.  `elementHost3`를 선택합니다.  
  
9. <xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle>로 설정합니다.  
  
     `elementHost3` 컨트롤의 크기가 조정되어 폼의 나머지 공간을 채웁니다.  
  
10. 폼의 크기를 조정합니다.  
  
     <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 3개의 크기가 모두 적절하게 조정됩니다.  
  
     자세한 내용은 [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [방법: 디자인 타임에 컨트롤을 폼의 가장자리에 맞춤](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)   
 [연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [WPF 컨트롤 사용](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)