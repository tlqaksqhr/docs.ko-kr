---
title: "연습: ElementHost 컨트롤을 사용하여 속성 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ElementHost 컨트롤, 속성 매핑"
  - "속성 매핑"
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 연습: ElementHost 컨트롤을 사용하여 속성 매핑
이 연습에서는 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> 속성을 사용하여 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 속성을 호스팅되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소의 해당 속성에 매핑하는 방법을 보여 줍니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   프로젝트 만들기  
  
-   새 속성 매핑 정의  
  
-   기본 속성 매핑 제거  
  
-   기본 속성 매핑 확장  
  
 이 연습에서 설명하는 작업의 전체 코드 목록은 [Mapping Properties Using the ElementHost Control 샘플](http://go.microsoft.com/fwlink/?LinkID=160018)을 참조하십시오.  
  
 작업을 마치면 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 속성을 호스팅되는 요소의 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성에 매핑할 수 있습니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## 프로젝트 만들기  
  
#### 프로젝트를 만들려면  
  
1.  `PropertyMappingWithElementHost`라는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램 프로젝트를 만듭니다.  자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
2.  솔루션 탐색기에서 참조를 다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리에 추가합니다.  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
3.  다음 코드를 `Form1` 코드 파일의 맨 위에 복사합니다.  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  Windows Forms 디자이너에서 `Form1`을 엽니다.  폼을 두 번 클릭하여 <xref:System.Windows.Forms.Form.Load> 이벤트에 대한 이벤트 처리기를 추가합니다.  
  
5.  Windows Forms 디자이너로 돌아가서 폼의 <xref:System.Windows.Forms.Control.Resize> 이벤트에 대한 이벤트 처리기를 추가합니다.  자세한 내용은 [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/ko-kr/8461e9b8-14e8-406f-936e-3726732b23d2)를 참조하십시오.  
  
6.  `Form1` 클래스에서 <xref:System.Windows.Forms.Integration.ElementHost> 필드를 선언합니다.  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## 새 속성 매핑 정의  
 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤은 여러 가지 기본 속성 매핑을 제공합니다.  <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>에서 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 메서드를 호출하여 새 속성 매핑을 추가합니다.  
  
#### 새 속성 매핑을 정의하려면  
  
1.  다음 코드를 `Form1` 클래스의 정의에 복사합니다.  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     `AddMarginMapping` 메서드는 <xref:System.Windows.Forms.Control.Margin%2A> 속성에 대해 새 매핑을 추가합니다.  
  
     `OnMarginChange` 메서드는 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> 속성으로 변환합니다.  
  
2.  다음 코드를 `Form1` 클래스의 정의에 복사합니다.  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     `AddRegionMapping` 메서드는 <xref:System.Windows.Forms.Control.Region%2A> 속성에 대해 새 매핑을 추가합니다.  
  
     `OnRegionChange` 메서드는 <xref:System.Windows.Forms.Control.Region%2A> 속성을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> 속성으로 변환합니다.  
  
     `Form1_Resize` 메서드는 폼의 <xref:System.Windows.Forms.Control.Resize> 이벤트를 처리하고 클리핑 영역의 크기를 조정하여 호스팅되는 요소에 맞춥니다.  
  
## 기본 속성 매핑 제거  
 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>에서 <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> 메서드를 호출하여 기본 속성 매핑을 제거합니다.  
  
#### 기본 속성 매핑을 제거하려면  
  
-   다음 코드를 `Form1` 클래스의 정의에 복사합니다.  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     `RemoveCursorMapping` 메서드는 <xref:System.Windows.Forms.Control.Cursor%2A> 속성에 대한 기본 매핑을 삭제합니다.  
  
## 기본 속성 매핑 확장  
 기본 속성 매핑을 사용하고 고유한 매핑을 사용하여 확장할 수 있습니다.  
  
#### 기본 속성 매핑을 확장하려면  
  
-   다음 코드를 `Form1` 클래스의 정의에 복사합니다.  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     `ExtendBackColorMapping` 메서드는 사용자 지정 속성 변환기를 기존 <xref:System.Windows.Forms.Control.BackColor%2A> 속성 매핑에 추가합니다.  
  
     `OnBackColorChange` 메서드는 특정 이미지를 호스팅되는 컨트롤의 <xref:System.Windows.Controls.Control.Background%2A> 속성에 할당합니다.  기본 속성 매핑이 적용된 후 `OnBackColorChange` 메서드가 호출됩니다.  
  
## 속성 매핑 초기화  
  
#### 속성 매핑을 초기화하려면  
  
1.  다음 코드를 `Form1` 클래스의 정의에 복사합니다.  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     `Form1_Load` 메서드는 <xref:System.Windows.Forms.Form.Load> 이벤트를 처리하고 다음 초기화를 수행합니다.  
  
    -   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> 요소를 만듭니다.  
  
    -   연습의 앞 부분에서 정의한 메서드를 호출하여 속성 매핑을 설정합니다.  
  
    -   초기 값을 매핑된 속성에 할당합니다.  
  
2.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Windows Forms 및 WPF 속성 매핑](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)   
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)