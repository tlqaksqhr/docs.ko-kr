---
title: '방법: Windows Presentation Foundation 요소에 데이터 바인딩(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: d6538ab0-0abe-426a-b9d9-e6f3a5ca2016
ms.openlocfilehash: da89eebb366cebca9933a30b4753e1fbbe2707c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363897"
---
# <a name="how-to-bind-data-to-windows-presentation-foundation-elements-wcf-data-services"></a>방법: Windows Presentation Foundation 요소에 데이터 바인딩(WCF Data Services)
와 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], 같은 Windows Presentation Foundation (WPF) 요소를 바인딩할 수는 <xref:System.Windows.Controls.ListBox>' 또는 <xref:System.Windows.Controls.ComboBox> 의 인스턴스로 <xref:System.Data.Services.Client.DataServiceCollection%601>를 유지 하는 컨트롤에서 발생 한 이벤트를 처리 하는 <xref:System.Data.Services.Client.DataServiceContext> 변경 내용과 동기화 컨트롤의 데이터를 하려고 합니다. 자세한 내용은 참조 [컨트롤에 데이터 바인딩](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)합니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 완료 하면이 서비스 및 클라이언트 데이터 클래스 생성 됩니다는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 WPF에서 `SalesOrders` 창을 정의하는 XAML(Extensible Application Markup Language) 페이지에 대한 코드 숨김 페이지에서 가져온 것입니다. 창을 로드하면 고객을 국가별로 필터링하여 반환하는 쿼리 결과를 기준으로 <xref:System.Data.Services.Client.DataServiceCollection%601>이 만들어집니다. 이 페이징 결과의 모든 페이지가 관련 주문과 함께 로드되고 WPF 창의 루트 레이아웃 컨트롤인 <xref:System.Windows.FrameworkElement.DataContext%2A>의 <xref:System.Windows.Controls.StackPanel> 속성에 바인딩됩니다. 자세한 내용은 참조 [지연 콘텐츠 로드](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)합니다.  
  
 [!code-csharp[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf3.xaml.cs#bindpageddata)]
 [!code-vb[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml.vb#bindpageddata)]  
  
## <a name="example"></a>예제  
 다음 XAML에서는 위 예제의 `SalesOrders` 창을 WPF에서 정의합니다.  
  
 [!code-xaml[Astoria Northwind Client#BindPagedDataXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml#bindpageddataxaml)]  
  
## <a name="example"></a>예제  
 다음 예제는 WPF에서 `SalesOrders` 창을 정의하는 XAML(Extensible Application Markup Language) 페이지에 대한 코드 숨김 페이지에서 가져온 것입니다. 창을 로드하면 관련 개체와 함께 고객을 국가별로 필터링하여 반환하는 쿼리 결과를 기준으로 <xref:System.Data.Services.Client.DataServiceCollection%601>이 만들어집니다. 이 결과는 WPF 창의 루트 레이아웃 컨트롤인 <xref:System.Windows.FrameworkElement.DataContext%2A>의 <xref:System.Windows.Controls.StackPanel> 속성에 바인딩됩니다.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf.xaml.cs#wpfdatabinding)]
 [!code-vb[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml.vb#wpfdatabinding)]  
  
## <a name="example"></a>예제  
 다음 XAML에서는 위 예제의 `SalesOrders` 창을 WPF에서 정의합니다.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml#wpfdatabindingxaml)]
