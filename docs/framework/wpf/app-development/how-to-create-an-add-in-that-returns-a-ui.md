---
title: "방법: UI를 반환하는 추가 기능 만들기 | Microsoft Docs"
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
  - "추가 기능[WPF], UI 반환"
  - "UI를 반환하는 추가 기능 만들기[WPF]"
  - "추가 기능 파이프라인 세그먼트 구현[WPF]"
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: UI를 반환하는 추가 기능 만들기
이 예제에서는 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]를 호스트 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 독립 실행형 응용 프로그램에 반환하는 추가 기능을 만드는 방법을 보여 줍니다.  
  
 추가 기능에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 사용자 컨트롤인 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 반환합니다.  이 사용자 컨트롤의 콘텐츠는 클릭했을 때 메시지 상자를 표시하는 하나의 단추입니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 독립 실행형 응용 프로그램에서는 이 추가 기능을 호스팅하고 추가 기능에서 반환되는 사용자 컨트롤을 주 응용 프로그램 창 콘텐츠로 표시합니다.  
  
 **사전 요구 사항**  
  
 이 예제에서는 이 시나리오를 지원하는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델에 대한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 확장을 중점적으로 다루며 다음과 같은 사항이 필요합니다.  
  
-   파이프라인, 추가 기능 및 호스트 개발을 포함한 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델에 대해 알고 있습니다.  이러한 개념에 대해 잘 모를 경우에는 [추가 기능 및 확장성](../../../../ml/index.xml)를 참조하십시오.  파이프라인, 추가 기능 및 호스트 응용 프로그램의 구현을 설명하는 자습서를 보려면 [연습: 확장 가능한 응용 프로그램 만들기](../Topic/Walkthrough:%20Creating%20an%20Extensible%20Application.md)를 참조하십시오.  
  
-   [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델의 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 확장에 대해 알고 있어야 합니다. 이에 대해서는 [WPF 추가 기능 개요](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)를 참조하십시오.  
  
## 예제  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 반환하는 추가 기능을 만들려면 파이프라인 세그먼트, 추가 기능 및 호스트 응용 프로그램 각각에 대한 특정 코드가 필요합니다.  
  
   
  
<a name="Contract"></a>   
## 계약 파이프라인 세그먼트 구현  
 계약에서는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 반환하고 반환 값이 <xref:System.AddIn.Contract.INativeHandleContract> 형식인 메서드를 정의해야 합니다.  다음 코드에서는 `IWPFAddInContract` 계약의 `GetAddInUI` 메서드를 통해 이를 보여 줍니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## 추가 기능 뷰 파이프라인 세그먼트 구현  
 추가 기능은 <xref:System.Windows.FrameworkElement>의 서브클래스로 제공되는 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 구현하므로 `IWPFAddInView.GetAddInUI`와 연결되는 추가 기능 뷰의 메서드는 <xref:System.Windows.FrameworkElement> 형식의 값을 반환해야 합니다.  다음 코드에서는 인터페이스로 구현된 계약의 추가 기능 뷰를 보여 줍니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## 추가 기능측 어댑터 파이프라인 세그먼트 구현  
 계약 메서드는 <xref:System.AddIn.Contract.INativeHandleContract>를 반환하지만 추가 기능은 추가 기능 뷰로 지정된 <xref:System.Windows.FrameworkElement>를 반환합니다.  따라서 격리 경계를 통과하기 전에 <xref:System.Windows.FrameworkElement>를 <xref:System.AddIn.Contract.INativeHandleContract>로 변환해야 합니다.  다음 코드와 같이 이 작업은 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>를 호출하여 추가 기능측 어댑터에서 수행됩니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## 호스트 뷰 파이프라인 세그먼트 구현  
 호스트 응용 프로그램은 <xref:System.Windows.FrameworkElement>를 표시하므로 `IWPFAddInHostView.GetAddInUI`를 연결하는 호스트 뷰의 메서드는 <xref:System.Windows.FrameworkElement> 형식의 값을 반환해야 합니다.  다음 코드에서는 인터페이스로 구현된 계약의 호스트 뷰를 보여 줍니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## 호스트측 어댑터 파이프라인 세그먼트 구현  
 계약 메서드는 <xref:System.AddIn.Contract.INativeHandleContract>를 반환하지만 호스트 응용 프로그램에는 호스트 뷰로 지정된 <xref:System.Windows.FrameworkElement>가 필요합니다.  따라서 격리 경계를 통과한 후에 <xref:System.AddIn.Contract.INativeHandleContract>를 <xref:System.Windows.FrameworkElement>로 변환해야 합니다.  다음 코드와 같이 이 작업은 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>를 호출하여 호스트측 어댑터에서 수행됩니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## 추가 기능 구현  
 추가 기능측 어댑터와 추가 기능 뷰가 만들어지면 추가 기능\(`WPFAddIn1.AddIn`\)이 <xref:System.Windows.FrameworkElement> 개체\(이 예제의 경우 <xref:System.Windows.Controls.UserControl>\)를 반환하는 `IWPFAddInView.GetAddInUI` 메서드를 구현해야 합니다.  <xref:System.Windows.Controls.UserControl>의 구현인 `AddInUI`는 다음 코드에서 확인할 수 있습니다.  
  
 [!code-xml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 다음 코드에서 볼 수 있듯이 추가 기능을 통한 `IWPFAddInView.GetAddInUI`의 구현은 `AddInUI`의 새 인스턴스를 반환하기만 하면 됩니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## 호스트 응용 프로그램 구현  
 호스트측 어댑터와 호스트 뷰가 만들어지면 호스트 응용 프로그램은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델을 사용하여 파이프라인을 열고 추가 기능의 호스트 뷰를 가져오고 `IWPFAddInHostView.GetAddInUI` 메서드를 호출할 수 있습니다.  이러한 단계는 다음 코드에서 볼 수 있습니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## 참고 항목  
 [추가 기능 및 확장성](../../../../ml/index.xml)   
 [WPF 추가 기능 개요](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)