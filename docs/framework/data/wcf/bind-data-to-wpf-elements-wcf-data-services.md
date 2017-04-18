---
title: "방법: Windows Presentation Foundation 요소에 데이터 바인딩(WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "데이터 바인딩, WCF Data Services"
  - "WCF Data Services, 데이터 바인딩"
ms.assetid: d6538ab0-0abe-426a-b9d9-e6f3a5ca2016
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 방법: Windows Presentation Foundation 요소에 데이터 바인딩(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하면 <xref:System.Data.Services.Client.DataServiceContext>를 컨트롤의 데이터 변경 내용과 동기화된 상태로 유지하기 위해 컨트롤이 발생시키는 이벤트를 처리하는 <xref:System.Data.Services.Client.DataServiceCollection%601> 인스턴스에 <xref:System.Windows.Controls.ListBox>``또는 <xref:System.Windows.Controls.ComboBox>와 같은 WPF\(Windows Presentation Foundation\) 요소를 바인딩할 수 있습니다.  자세한 내용은 [컨트롤에 데이터 바인딩](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)을 참조하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다.  이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료하면 만들어집니다.  
  
## 예제  
 다음 예제는 WPF에서 `SalesOrders` 창을 정의하는 XAML\(Extensible Application Markup Language\) 페이지에 대한 코드 숨김 페이지에서 가져온 것입니다.  창을 로드하면 고객을 국가별로 필터링하여 반환하는 쿼리 결과를 기준으로 <xref:System.Data.Services.Client.DataServiceCollection%601>이 만들어집니다.  이 페이징 결과의 모든 페이지가 관련 주문과 함께 로드되고 WPF 창의 루트 레이아웃 컨트롤인 <xref:System.Windows.Controls.StackPanel>의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성에 바인딩됩니다.  자세한 내용은 [지연된 콘텐츠 로드](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)을 참조하세요.  
  
 [!code-csharp[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf3.xaml.cs#bindpageddata)]
 [!code-vb[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml.vb#bindpageddata)]  
  
## 예제  
 다음 XAML에서는 위 예제의 `SalesOrders` 창을 WPF에서 정의합니다.  
  
 [!code-xml[Astoria Northwind Client#BindPagedDataXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml#bindpageddataxaml)]  
  
## 예제  
 다음 예제는 WPF에서 `SalesOrders` 창을 정의하는 XAML\(Extensible Application Markup Language\) 페이지에 대한 코드 숨김 페이지에서 가져온 것입니다.  창을 로드하면 관련 개체와 함께 고객을 국가별로 필터링하여 반환하는 쿼리 결과를 기준으로 <xref:System.Data.Services.Client.DataServiceCollection%601>이 만들어집니다.  이 결과는 WPF 창의 루트 레이아웃 컨트롤인 <xref:System.Windows.Controls.StackPanel>의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성에 바인딩됩니다.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf.xaml.cs#wpfdatabinding)]
 [!code-vb[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml.vb#wpfdatabinding)]  
  
## 예제  
 다음 XAML에서는 위 예제의 `SalesOrders` 창을 WPF에서 정의합니다.  
  
 [!code-xml[Astoria Northwind Client#WpfDataBindingXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml#wpfdatabindingxaml)]