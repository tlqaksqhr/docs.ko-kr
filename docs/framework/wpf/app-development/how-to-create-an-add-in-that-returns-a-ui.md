---
title: '방법: UI를 반환하는 추가 기능 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: 24b30d61553796840a44a869eacb33232a0b78d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548235"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>방법: UI를 반환하는 추가 기능 만들기
이 예제에서는 호스트에 Windows Presentation Foundation (WPF)를 반환 하는 추가 기능을 만드는 방법을 보여 줍니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 독립 실행형 응용 프로그램입니다.  
  
 추가 기능은 반환는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 즉는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 사용자 정의 컨트롤입니다. 이 사용자 정의 컨트롤의 콘텐츠는 클릭했을 때 메시지 상자를 표시하는 하나의 단추입니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 독립 실행형 응용 프로그램 추가 기능을 호스트 하 고 (추가 기능에서 반환 됨) 사용자 정의 컨트롤의 기본 응용 프로그램 창 내용으로 표시 됩니다.  
  
 **필수 구성 요소**  
  
 이 예제에서는 강조 표시는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 에 대 한 확장 된 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 이 시나리오를 사용 하 고 다음을 가정 하는 추가 기능 모델:  
  
-   기술 자료는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델, 파이프라인, 추가 기능 및 개발 호스트를 포함 합니다. 이러한 개념을 잘 모르는 경우 참조 [추가 기능 및 확장성](../../../../docs/framework/add-ins/index.md)합니다. 파이프라인, 추가 기능 및 호스트 응용 프로그램의 구현을 설명 하는 자습서를 참조 하십시오. [연습: 확장 가능한 응용 프로그램 만들기](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)합니다.  
  
-   기술 자료는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 에 대 한 확장은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능에서 모델을 찾아볼 수 있습니다: [WPF 추가 기능 개요](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)합니다.  
  
## <a name="example"></a>예제  
 반환 하는 추가 기능을 만드는 한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 각 파이프라인 세그먼트에서 추가 기능을 하 고 호스트 응용 프로그램에 대 한 특정 코드가 필요 합니다.  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>계약 파이프라인 세그먼트 구현  
 반환 하기 위한 계약을 통해 메서드를 정의 해야 합니다는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 반환 값 형식 이어야 하 고 <xref:System.AddIn.Contract.INativeHandleContract>합니다. 이 확인할는 `GetAddInUI` 의 메서드는 `IWPFAddInContract` 다음 코드에서 계약입니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>추가 기능 뷰 파이프라인 세그먼트 구현  
 추가 기능을 구현 하기 때문에 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 의 서브 클래스로 제공 <xref:System.Windows.FrameworkElement>, 상관 관계에 있는 추가 기능을 보기에 대 한 메서드가 `IWPFAddInView.GetAddInUI` 형식의 값을 반환 해야 <xref:System.Windows.FrameworkElement>합니다. 다음 코드에서는 인터페이스로 구현된 계약의 추가 기능 뷰를 보여 줍니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>추가 기능 쪽 어댑터 파이프라인 세그먼트 구현  
 계약 메서드의 반환는 <xref:System.AddIn.Contract.INativeHandleContract>, 추가 기능을 반환 하지만 <xref:System.Windows.FrameworkElement> (추가 기능을 보기에 지정 된 대로). 따라서는 <xref:System.Windows.FrameworkElement> 으로 변환 해야는 <xref:System.AddIn.Contract.INativeHandleContract> 격리 경계를 통과 하기 전에. 이 작업은 호출 하 여 추가 기능 측 어댑터에 의해 수행 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>다음 코드에 나온 것 처럼 합니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>호스트 뷰 파이프라인 세그먼트 구현  
 호스트 응용 프로그램이 표시 됩니다는 <xref:System.Windows.FrameworkElement>, 상관 관계에 있는 [호스트] 보기에 대 한 메서드가 `IWPFAddInHostView.GetAddInUI` 형식의 값을 반환 해야 <xref:System.Windows.FrameworkElement>합니다. 다음 코드에서는 인터페이스로 구현된 계약의 호스트 뷰를 보여 줍니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>호스트 측 어댑터 파이프라인 세그먼트 구현  
 계약 메서드의 반환는 <xref:System.AddIn.Contract.INativeHandleContract>, 호스트 응용 프로그램에는 있지만 <xref:System.Windows.FrameworkElement> ([호스트] 보기에서 지정 된 대로). 따라서는 <xref:System.AddIn.Contract.INativeHandleContract> 으로 변환 해야는 <xref:System.Windows.FrameworkElement> 격리 경계를 통과 한 후 합니다. 이 작업은 호출 하 여 호스트 측 어댑터에 의해 수행 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>다음 코드에 나온 것 처럼 합니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>추가 기능 구현  
 추가 기능 측 어댑터 및 추가 기능에서 보기를 만든 추가 기능을 사용 하 여 (`WPFAddIn1.AddIn`)를 구현 해야 합니다는 `IWPFAddInView.GetAddInUI` 반환 하는 메서드는 <xref:System.Windows.FrameworkElement> 개체 (한 <xref:System.Windows.Controls.UserControl> 이 예에서). 구현에서 <xref:System.Windows.Controls.UserControl>, `AddInUI`, 다음 코드에 의해 표시 됩니다.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 구현에서 `IWPFAddInView.GetAddInUI` 추가 기능에서 단순히를 새 인스턴스를 반환 해야 `AddInUI`다음 코드에 의해 표시 된 것 처럼 합니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a>호스트 응용 프로그램 구현  
 호스트 응용 프로그램 호스트 측 어댑터와 생성 [호스트] 보기 צ ְ ײ는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 을 열어이 파이프라인에서 추가 기능을 및 호출 기능의 호스트 뷰를 가져올 추가 기능 모델은 `IWPFAddInHostView.GetAddInUI` 메서드. 이러한 단계는 다음 코드에 나와 있습니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>참고 항목  
 [추가 기능 및 확장성](../../../../docs/framework/add-ins/index.md)  
 [WPF 추가 기능 개요](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
