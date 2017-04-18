---
title: "연습: 혼합 응용 프로그램에서 데이터 바인딩 | Microsoft Docs"
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
  - "데이터 바인딩[WPF 상호 운용성]"
  - "혼합 응용 프로그램[WPF 상호 운용성]"
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
caps.latest.revision: 39
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 36
---
# 연습: 혼합 응용 프로그램에서 데이터 바인딩
데이터 소스를 컨트롤에 바인딩하는 작업은 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 중에 무엇을 사용 중이건 사용자가 내부 데이터에 액세스할 수 있도록 하기 위해 필수적입니다.  이 연습은 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 모두 포함하는 혼합 응용 프로그램에서 데이터 바인딩을 사용하는 방법을 보여 줍니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   프로젝트 만들기  
  
-   데이터 템플릿 정의  
  
-   폼 레이아웃 지정  
  
-   데이터 바인딩 지정  
  
-   상호 운용을 사용하여 데이터 표시  
  
-   프로젝트에 데이터 소스 추가  
  
-   데이터 소스에 바인딩  
  
 이 연습에서 설명하는 작업의 전체 코드 목록은 [Data Binding in Hybrid Applications 샘플](http://go.microsoft.com/fwlink/?LinkID=159983)을 참조하십시오.  
  
 연습을 마치면 혼합 응용 프로그램에서의 데이터 바인딩 기능을 이해할 수 있게 됩니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   Microsoft SQL Server를 실행하는 Northwind 샘플 데이터베이스에 대한 액세스 권한  
  
## 프로젝트 만들기  
  
#### 프로젝트를 만들고 설정하려면  
  
1.  `WPFWithWFAndDatabinding`이라는 WPF 응용 프로그램 프로젝트를 만듭니다.  
  
2.  솔루션 탐색기에서 다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]에서 MainWindow.xaml을 엽니다.  
  
4.  <xref:System.Windows.Window> 요소에서 다음 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 네임스페이스 매핑을 추가합니다.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <xref:System.Windows.FrameworkElement.Name%2A> 속성을 할당하여 기본 <xref:System.Windows.Controls.Grid> 요소 `mainGrid`를 명명합니다.  
  
     [!code-xml[WPFWithWFAndDatabinding#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## 데이터 템플릿 정의  
 고객의 마스터 목록은 <xref:System.Windows.Controls.ListBox> 컨트롤에 표시됩니다.  다음 코드 예제는 <xref:System.Windows.Controls.ListBox> 컨트롤의 시각적 트리를 제어하는 `ListItemsTemplate`이라는 <xref:System.Windows.DataTemplate> 개체를 정의합니다.  이 <xref:System.Windows.DataTemplate>은 <xref:System.Windows.Controls.ListBox> 컨트롤의 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 속성에 할당됩니다.  
  
#### 데이터 템플릿을 정의하려면  
  
-   다음 XAML를 <xref:System.Windows.Controls.Grid> 요소의 선언에 복사합니다.  
  
     [!code-xml[WPFWithWFAndDatabinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## 폼 레이아웃 지정  
 폼 레이아웃은 행과 열이 각각 세 개있는 표로 정의됩니다.  <xref:System.Windows.Controls.Label> 컨트롤은 Customers 테이블에 있는 각 열을 식별하기 위해 제공됩니다.  
  
#### 표 레이아웃을 설정하려면  
  
-   다음 XAML를 <xref:System.Windows.Controls.Grid> 요소의 선언에 복사합니다.  
  
     [!code-xml[WPFWithWFAndDatabinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### 레이블 컨트롤을 설정하려면  
  
-   다음 XAML를 <xref:System.Windows.Controls.Grid> 요소의 선언에 복사합니다.  
  
     [!code-xml[WPFWithWFAndDatabinding#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## 데이터 바인딩 지정  
 고객의 마스터 목록은 <xref:System.Windows.Controls.ListBox> 컨트롤에 표시됩니다.  첨부된 `ListItemsTemplate`은 <xref:System.Windows.Controls.TextBlock> 컨트롤을 데이터베이스의 `ContactName` 필드에 바인딩합니다.  
  
 각 고객 레코드의 상세 정보는 여러 <xref:System.Windows.Controls.TextBox> 컨트롤에 표시됩니다.  
  
#### 데이터 바인딩을 지정하려면  
  
-   다음 XAML를 <xref:System.Windows.Controls.Grid> 요소의 선언에 복사합니다.  
  
     <xref:System.Windows.Data.Binding> 클래스가 <xref:System.Windows.Controls.TextBox> 컨트롤을 데이터베이스의 적절한 필드에 바인딩합니다.  
  
     [!code-xml[WPFWithWFAndDatabinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## 상호 운용을 사용하여 데이터 표시  
 선택한 고객에 해당하는 주문은 `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView?displayProperty=fullName> 컨트롤에 표시됩니다.  `dataGridView1` 컨트롤은 코드 숨김 파일에서 데이터 소스에 바인딩되어 있습니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤은 이 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 부모입니다.  
  
#### DataGridView 컨트롤에 데이터를 표시하려면  
  
-   다음 XAML를 <xref:System.Windows.Controls.Grid> 요소의 선언에 복사합니다.  
  
     [!code-xml[WPFWithWFAndDatabinding#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## 프로젝트에 데이터 소스 추가  
 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서는 프로젝트에 데이터 소스를 쉽게 추가할 수 있습니다.  이 절차는 강력한 형식의 데이터 집합을 프로젝트에 추가합니다.  선택된 각 테이블에 대한 테이블 어댑터와 같은 기타 여러 지원 클래스도 추가됩니다.  
  
#### 데이터 소스를 추가하려면  
  
1.  **데이터** 메뉴에서 **새 데이터 소스 추가**를 선택합니다.  
  
2.  **데이터 소스 구성 마법사**에서 데이터 집합을 사용하여 Northwind 데이터베이스에 대한 연결을 만듭니다.  자세한 내용은 [방법: 데이터베이스의 데이터에 연결](../Topic/How%20to:%20Connect%20to%20Data%20in%20a%20Database.md)을 참조하십시오.  
  
3.  **데이터 소스 구성 마법사**에서 해당 메시지가 나타나면 연결 문자열을 `NorthwindConnectionString`으로 저장합니다.  
  
4.  데이터베이스 개체를 선택하라는 메시지가 표시되면 `Customers` 및 `Orders` 테이블을 선택하고 생성된 데이터 집합의 이름을 `NorthwindDataSet`으로 지정합니다.  
  
## 데이터 소스에 바인딩  
 <xref:System.Windows.Forms.BindingSource?displayProperty=fullName> 구성 요소는 응용 프로그램의 데이터 소스에 일관된 인터페이스를 제공합니다.  데이터 소스에 바인딩하는 작업은 코드 숨김 파일에서 구현됩니다.  
  
#### 데이터 소스에 바인딩하려면  
  
1.  MainWindow.xaml.vb 또는 MainWindow.xaml.cs라고 명명된 코드 숨김 파일을 엽니다.  
  
2.  다음 코드를 `MainWindow` 클래스 정의에 복사합니다.  
  
     이 코드는 <xref:System.Windows.Forms.BindingSource> 구성 요소와 데이터베이스에 연결하는 관련 도우미 클래스를 선언합니다.  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]  
  
3.  다음 코드를 생성자에 복사합니다.  
  
     이 코드는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 만들고 초기화합니다.  
  
     [!code-csharp[WPFWithWFAndDatabinding#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]  
  
4.  MainWindow.xaml을 엽니다.  
  
5.  디자인 뷰 또는 XAML 뷰에서 <xref:System.Windows.Window> 요소를 선택합니다.  
  
6.  속성 창에서 **이벤트** 탭을 클릭합니다.  
  
7.  <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 두 번 클릭합니다.  
  
8.  다음 코드를 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기에 복사합니다.  
  
     이 코드는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 데이터 컨텍스트로 할당하고 `Customers` 및 `Orders` 어댑터 개체를 채웁니다.  
  
     [!code-csharp[WPFWithWFAndDatabinding#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]  
  
9. 다음 코드를 `MainWindow` 클래스 정의에 복사합니다.  
  
     이 메서드는 <xref:System.Windows.Data.CollectionView.CurrentChanged> 이벤트를 처리하고 데이터 바인딩의 현재 항목을 업데이트합니다.  
  
     [!code-csharp[WPFWithWFAndDatabinding#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Data Binding in Hybrid Applications 샘플](http://go.microsoft.com/fwlink/?LinkID=159983)   
 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)