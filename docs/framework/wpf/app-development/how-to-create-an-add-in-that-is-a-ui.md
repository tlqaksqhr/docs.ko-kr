---
title: "방법: UI인 추가 기능 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fea1c718eedb12d49eced9964e4f9045badf07ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>방법: UI인 추가 기능 만들기
에 있는 추가 기능을 만드는 방법을 보여 주는이 예제는 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 에서 호스팅되는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 독립 실행형 응용 프로그램입니다.  
  
 추가 기능에 한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 즉는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 사용자 정의 컨트롤입니다. 이 사용자 정의 컨트롤의 콘텐츠는 클릭했을 때 메시지 상자를 표시하는 하나의 단추입니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 독립 실행형 응용 프로그램에서 추가 기능을 호스트 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 주 응용 프로그램 창 내용으로 합니다.  
  
 **필수 구성 요소**  
  
 이 예제에서는 강조 표시는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 에 대 한 확장 된 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 이 시나리오를 사용 하 고 다음을 가정 하는 추가 기능 모델:  
  
-   기술 자료는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델, 파이프라인, 추가 기능 및 개발 호스트를 포함 합니다. 이러한 개념을 잘 모르는 경우 참조 [추가 기능 및 확장성](../../../../docs/framework/add-ins/index.md)합니다. 파이프라인, 추가 기능 및 호스트 응용 프로그램의 구현을 설명 하는 자습서를 참조 하십시오. [연습: 확장 가능한 응용 프로그램 만들기](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)합니다.  
  
-   기술 자료는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 에 대 한 확장은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능에서 모델을 찾아볼 수 있습니다: [WPF 추가 기능 개요](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)합니다.  
  
## <a name="example"></a>예  
 에 있는 추가 기능을 만드는 한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 각 파이프라인 세그먼트에서 추가 기능을 하 고 호스트 응용 프로그램에 대 한 특정 코드가 필요 합니다.  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>계약 파이프라인 세그먼트 구현  
 추가 기능에서 경우는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 추가 기능에 대 한 계약을 구현 해야 <xref:System.AddIn.Contract.INativeHandleContract>합니다. 예제에서는 `IWPFAddInContract` 구현 <xref:System.AddIn.Contract.INativeHandleContract>다음 코드에 나온 것 처럼 합니다.  
  
 [!code-csharp[SimpleAddInIsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]  
  
<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>추가 기능 뷰 파이프라인 세그먼트 구현  
 추가 기능에의 하위 클래스로 구현 되기 때문에 <xref:System.Windows.FrameworkElement> 을 수행 해야 하위 클래스 형식, 추가 기능에서 뷰 <xref:System.Windows.FrameworkElement>합니다. 다음 코드에서는으로 구현 된 계약의 추가 기능을 보기는 `WPFAddInView` 클래스입니다.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
  
 추가 기능을 보기에서 파생 되는 여기서 <xref:System.Windows.Controls.UserControl>합니다. 따라서 추가 기능을 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 또한에서 파생 되어야 <xref:System.Windows.Controls.UserControl>합니다.  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>추가 기능 쪽 어댑터 파이프라인 세그먼트 구현  
 계약은 <xref:System.AddIn.Contract.INativeHandleContract>에 추가 하는 한 <xref:System.Windows.FrameworkElement> (뷰 추가 기능 파이프라인 세그먼트에 지정 된 대로). 따라서는 <xref:System.Windows.FrameworkElement> 으로 변환 해야는 <xref:System.AddIn.Contract.INativeHandleContract> 격리 경계를 통과 하기 전에. 이 작업은 호출 하 여 추가 기능 측 어댑터에 의해 수행 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>다음 코드에 나온 것 처럼 합니다.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
  
 모델 추가에서 추가 기능을 반환 하는 위치는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] (참조 [UI는 추가 기능을 반환 하는지 만들](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)), 추가 기능 어댑터 변환는 <xref:System.Windows.FrameworkElement> 에 <xref:System.AddIn.Contract.INativeHandleContract> 호출 하 여 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>합니다. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>도 호출 해야이 모델에는 메서드를 호출 하기 위한 코드를 쓸 수 있는를 구현 해야 합니다. 재정의 하 여이 작업을 수행 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 호출 하는 코드를 구현 하 고 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 경우 호출 하는 코드 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 예상는 <xref:System.AddIn.Contract.INativeHandleContract>합니다. 이 경우 호출자가 호스트 쪽 어댑터가 됩니다. 이에 대해서는 이후의 하위 단원에서 설명합니다.  
  
> [!NOTE]
>  재정의 해야 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 호스트 응용 프로그램 간 탭 이동 사용 하도록 설정 하려면이 모델에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 및 추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다. 자세한 내용은의 "WPF 추가 기능을 제한 사항" 참조 [WPF 추가 기능 개요](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)합니다.  
  
 추가 기능 측 어댑터에서 파생 되는 인터페이스를 구현 하기 때문에 <xref:System.AddIn.Contract.INativeHandleContract>를 구현 해야 <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>이 무시 되더라도 때 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 재정의 됩니다.  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>호스트 뷰 파이프라인 세그먼트 구현  
 이 모델에서는 호스트 응용 프로그램이 일반적으로 예상 되도록 [호스트] 보기는 <xref:System.Windows.FrameworkElement> 하위 클래스입니다. 호스트 측 어댑터 변환 해야 합니다는 <xref:System.AddIn.Contract.INativeHandleContract> 에 <xref:System.Windows.FrameworkElement> 후는 <xref:System.AddIn.Contract.INativeHandleContract> 격리 경계를 통과 합니다. 호스트 응용 프로그램을 여는 메서드를 호출 하지 때문에 <xref:System.Windows.FrameworkElement>, [호스트] 보기 해야 "return"는 <xref:System.Windows.FrameworkElement> 포함 하 여 합니다. [호스트] 보기의 서브 클래스에서 파생 되어야 따라서 <xref:System.Windows.FrameworkElement> 다른 포함할 수 있는 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]와 같은 <xref:System.Windows.Controls.UserControl>합니다. 다음 코드에서는으로 구현 된 계약의 [호스트] 보기에서 `WPFAddInHostView` 클래스입니다.  
  
  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>호스트 측 어댑터 파이프라인 세그먼트 구현  
 계약은 <xref:System.AddIn.Contract.INativeHandleContract>, 호스트 응용 프로그램에서 검색할는 <xref:System.Windows.Controls.UserControl> ([호스트] 보기에서 지정 된 대로). 따라서는 <xref:System.AddIn.Contract.INativeHandleContract> 으로 변환 해야는 <xref:System.Windows.FrameworkElement> [호스트] 보기의 내용으로 설정 하기 전에 격리 경계를 통과 한 후 (에서 파생 되는 <xref:System.Windows.Controls.UserControl>).  
  
 다음 코드와 같이 이 작업은 호스트 쪽 어댑터로 수행됩니다.  
  
  
  
 호스트 측 어댑터 획득 볼 수 있듯이 <xref:System.AddIn.Contract.INativeHandleContract> 추가 기능 측 어댑터를 호출 하 여 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 메서드 (지점 위치는 <xref:System.AddIn.Contract.INativeHandleContract> 격리 경계를 넘는).  
  
 호스트 측 어댑터 그런 다음 변환의 <xref:System.AddIn.Contract.INativeHandleContract> 에 <xref:System.Windows.FrameworkElement> 호출 하 여 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>합니다. 마지막으로 <xref:System.Windows.FrameworkElement> [호스트] 보기의 내용으로 설정 됩니다.  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>추가 기능 구현  
 추가 기능 쪽 어댑터와 추가 기능 뷰를 배치했으면 다음 코드와 같이 추가 기능 뷰에서 파생시켜 추가 기능을 구현할 수 있습니다.  
  
  
  
  
  
 이 예제에서는이 모델의 흥미로운 장점 볼 수 있습니다: 개발자가 추가 기능을 구현 하기만에서 추가 기능 (이므로 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 도), 추가 기능 클래스 및 추가 기능을 대신 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다.  
  
<a name="HostApp"></a>   
## <a name="implementing-the-host-application"></a>호스트 응용 프로그램 구현  
 호스트 응용 프로그램 호스트 측 어댑터와 생성 [호스트] 보기 צ ְ ײ는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 파이프라인을 열고 추가 기능의 호스트 뷰를 가져올 추가 기능 모델입니다. 이러한 단계는 다음 코드에 나와 있습니다.  
  
  
  
 호스트 응용 프로그램에서 일반적인 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 는 추가 기능 활성화, 암시적으로 호스트 응용 프로그램 [호스트] 보기를 반환 하는 추가 기능 모델 코드입니다. 호스트 응용 프로그램에는 이후에 [호스트] 보기 표시 (이 <xref:System.Windows.Controls.UserControl>)에서 <xref:System.Windows.Controls.Grid>합니다.  
  
 추가와 상호 작용을 처리 하기 위한 코드 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 응용 프로그램 도메인에 대 한 추가 기능에서 실행 합니다. 이러한 상호 작용에는 다음이 포함됩니다.  
  
-   처리는 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다.  
  
-   표시는 <xref:System.Windows.MessageBox>합니다.  
  
 이 작업은 호스트 응용 프로그램에서 완전히 격리됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [추가 기능 및 확장성](../../../../docs/framework/add-ins/index.md)  
 [WPF 추가 기능 개요](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
