---
title: "연습: WindowsFormsHost 요소를 사용하여 속성 매핑 | Microsoft Docs"
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
  - "속성 매핑"
  - "WindowsFormsHost 요소 속성 매핑"
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# 연습: WindowsFormsHost 요소를 사용하여 속성 매핑
이 연습에서는 사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 매핑할 속성을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 해당 속성에 호스팅 속성 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 제어 합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   프로젝트를 만듭니다.  
  
-   응용 프로그램 레이아웃을 정의 합니다.  
  
-   새 속성 매핑을 정의합니다.  
  
-   기본 속성 매핑을 제거 합니다.  
  
-   기본 속성 매핑을 대체 합니다.  
  
-   기본 속성 매핑을 확장 합니다.  
  
 이 연습에서 설명 하는 작업의 전체 코드 목록을 보려면 [WindowsFormsHost 요소 샘플을 사용 하 여 속성 매핑](http://go.microsoft.com/fwlink/?LinkID=160019)합니다.  
  
 매핑할 수 작업을 완료 하는 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 해당 속성에 호스팅 속성 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 제어 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
  
#### <a name="to-create-and-set-up-the-project"></a>만들고 프로젝트를 설정 합니다.  
  
1.  WPF 응용 프로그램 프로젝트를 라는 `PropertyMappingWithWfhSample`합니다.  
  
2.  솔루션 탐색기에서 WindowsFormsIntegration.dll 라는 WindowsFormsIntegration 어셈블리에 대 한 참조를 추가 합니다.  
  
3.  솔루션 탐색기에서 System.Drawing 및 System.Windows.Forms 어셈블리에 대 한 참조를 추가 합니다.  
  
## <a name="defining-the-application-layout"></a>응용 프로그램 레이아웃 정의  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램의 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 호스트 하는 요소는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 제어 합니다.  
  
#### <a name="to-define-the-application-layout"></a>응용 프로그램 레이아웃을 정의 하려면  
  
1.  열에서 Window1.xaml는 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]합니다.  
  
2.  기존 코드를 다음 코드로 바꿉니다.  
  
     [!code-xml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]  
  
3.  Window1. xaml.cs 코드 편집기에서 엽니다.  
  
4.  파일 맨 위에 있는 다음 네임 스페이스를 가져옵니다.  
  
     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]  
  
## <a name="defining-a-new-property-mapping"></a>새 속성 매핑을 정의합니다.  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 여러 가지 기본을 속성 매핑을 제공 합니다. 호출 하 여 새 속성 매핑을 추가 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 메서드는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>합니다.  
  
#### <a name="to-define-a-new-property-mapping"></a>새 속성 매핑을 정의 하려면  
  
-   에 대 한 정의에 다음 코드를 복사는 `Window1` 클래스입니다.  
  
     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]  
  
     `AddClipMapping` 에 대 한 새 매핑을 추가 하는 메서드는 <xref:System.Windows.UIElement.Clip%2A> 속성입니다.  
  
     `OnClipChange` 메서드 변환 하는 <xref:System.Windows.UIElement.Clip%2A> 속성을는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> 속성입니다.  
  
     `Window1_SizeChanged` 메서드 처리 창의 <xref:System.Windows.FrameworkElement.SizeChanged> 이벤트 고 응용 프로그램 창에 맞게 클리핑 영역 크기를 지정 합니다.  
  
## <a name="removing-a-default-property-mapping"></a>기본 속성 매핑을 제거합니다.  
 호출 하 여 기본 속성 매핑을 제거는 <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> 메서드는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>합니다.  
  
#### <a name="to-remove-a-default-property-mapping"></a>기본 속성 매핑을 제거 하려면  
  
-   에 대 한 정의에 다음 코드를 복사는 `Window1` 클래스입니다.  
  
     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]  
  
     `RemoveCursorMapping` 메서드에 대 한 기본 매핑을 삭제 하는 <xref:System.Windows.FrameworkElement.Cursor%2A> 속성입니다.  
  
## <a name="replacing-a-default-property-mapping"></a>기본 속성 매핑을 교체  
 기본 매핑 및 호출을 제거 하 여 기본 속성 매핑을 바꾸기는 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 메서드를는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>합니다.  
  
#### <a name="to-replace-a-default-property-mapping"></a>기본 속성 매핑을 바꾸려면  
  
-   에 대 한 정의에 다음 코드를 복사는 `Window1` 클래스입니다.  
  
     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]  
  
     `ReplaceFlowDirectionMapping` 메서드 대체에 대 한 기본 매핑을 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성입니다.  
  
     `OnFlowDirectionChange` 메서드 변환 하는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성을는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> 속성입니다.  
  
     `cb_CheckedChanged` 메서드 핸들로 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 이벤트에는 <xref:System.Windows.Forms.CheckBox> 제어 합니다. 할당 된 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성의 값에 따라는 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성  
  
## <a name="extending-a-default-property-mapping"></a>확장 기본 속성 매핑  
 기본 속성 매핑을 사용할 수 있으며 자신의 매핑을 사용 하 여 확장할 수도 있습니다.  
  
#### <a name="to-extend-a-default-property-mapping"></a>기본 속성 매핑을 확장 하려면  
  
-   에 대 한 정의에 다음 코드를 복사는 `Window1` 클래스입니다.  
  
     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]  
  
     `ExtendBackgroundMapping` 메서드는 사용자 지정 속성 변환기를 기존 추가 <xref:System.Windows.Controls.Control.Background%2A> 속성 매핑.  
  
     `OnBackgroundChange` 메서드는 특정 이미지를 호스팅된 컨트롤의 할당 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성입니다. `OnBackgroundChange` 기본 속성 매핑을 적용 된 후 메서드가 호출 됩니다.  
  
## <a name="initializing-your-property-mappings"></a>속성 매핑 초기화  
 이전에 설명한 메서드를 호출 하 여 속성 매핑을 설정의 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기입니다.  
  
#### <a name="to-initialize-your-property-mappings"></a>속성 매핑을 초기화 하려면  
  
1.  에 대 한 정의에 다음 코드를 복사는 `Window1` 클래스입니다.  
  
     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]  
  
     `WindowLoaded` 메서드 핸들은 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 다음 초기화를 수행 하 고 있습니다.  
  
    -   만듭니다는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> 제어 합니다.  
  
    -   속성 매핑을 설정 하는 연습의 앞부분에서 정의한 메서드를 호출 합니다.  
  
    -   매핑된 속성을 초기 값을 할당 합니다.  
  
2.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. 효과 확인 하려면이 확인란을 클릭 합니다.는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 매핑. 확인란을 클릭 하는 경우 레이아웃의 왼쪽에서 오른쪽 방향을 반대로 바꿉니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Windows Forms 및 WPF 속성 매핑](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [WPF 디자이너](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)   
 [연습: WPF에서 Windows Forms 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)