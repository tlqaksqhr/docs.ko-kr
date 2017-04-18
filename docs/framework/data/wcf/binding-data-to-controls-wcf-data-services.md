---
title: "컨트롤에 데이터 바인딩(WCF Data Services) | Microsoft Docs"
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
  - "클라이언트 응용 프로그램, WCF Data Services"
  - "데이터 바인딩, WCF Data Services"
  - "WCF Data Services, 클라이언트 라이브러리"
ms.assetid: b32e1d49-c214-4cb1-867e-88fbb3d08c8d
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 컨트롤에 데이터 바인딩(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하면 `ComboBox`, `ListView` 등의 컨트롤을 <xref:System.Data.Services.Client.DataServiceCollection%601> 클래스 인스턴스에 바인딩할 수 있습니다. <xref:System.Collections.ObjectModel.ObservableCollection%601> 클래스에서 상속하는 이 컬렉션에는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드의 데이터가 들어 있습니다.  이 클래스는 항목이 추가 또는 제거될 때 알림을 제공하는 동적 데이터 컬렉션을 나타냅니다.  데이터 바인딩에 <xref:System.Data.Services.Client.DataServiceCollection%601> 인스턴스를 사용하는 경우 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리는 이러한 이벤트를 처리하여 <xref:System.Data.Services.Client.DataServiceContext>에 의해 추적되는 개체가 바인딩된 UI 요소의 데이터와 동기화된 상태로 유지되도록 합니다.  
  
 <xref:System.Data.Services.Client.DataServiceCollection%601> 클래스는 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스를 간접적으로 구현하여 개체가 컬렉션에 추가 또는 제거된 경우 컨텍스트에 알립니다.  <xref:System.Data.Services.Client.DataServiceCollection%601>과 함께 사용된 데이터 서비스 형식 개체는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스도 구현하여 바인딩 컬렉션의 개체 속성이 변경된 경우 <xref:System.Data.Services.Client.DataServiceCollection%601>에 알려야 합니다.  
  
> [!NOTE]
>  **서비스 참조 추가** 대화 상자나 [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) 도구에 `/dataservicecollection` 옵션을 사용하여 클라이언트 데이터 서비스 클래스를 생성하는 경우 생성된 데이터 클래스는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현합니다.  자세한 내용은 [방법: 수동으로 클라이언트 데이터 서비스 클래스 생성](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)을 참조하세요.  
  
## 바인딩 컬렉션 만들기  
 제공된 <xref:System.Data.Services.Client.DataServiceContext> 인스턴스와 선택적으로 실행 시 <xref:System.Collections.Generic.IEnumerable%601> 인스턴스를 반환하는 <xref:System.Data.Services.Client.DataServiceQuery%601> 또는 LINQ 쿼리를 통해 클래스 생성자 메서드 중 하나를 호출하여 <xref:System.Data.Services.Client.DataServiceCollection%601> 클래스의 새 인스턴스를 만듭니다.  이 <xref:System.Collections.Generic.IEnumerable%601>은 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에서 구체화되는 개체 소스를 바인딩 컬렉션에 제공합니다.  자세한 내용은 [개체 구체화](../../../../docs/framework/data/wcf/object-materialization-wcf-data-services.md)을 참조하세요.  기본적으로 컬렉션에 삽입된 항목 및 바인딩된 개체의 변경 내용은 <xref:System.Data.Services.Client.DataServiceContext>에 의해 자동으로 추적됩니다.  수동으로 이러한 변경 내용을 추적해야 하는 경우 `trackingMode` 매개 변수를 사용하는 생성자 메서드 중 하나를 호출하고 <xref:System.Data.Services.Client.TrackingMode> 값을 지정합니다.  
  
 다음 예제에서는 제공된 <xref:System.Data.Services.Client.DataServiceContext> 및 관련 주문과 함께 모든 고객을 반환하는 <xref:System.Data.Services.Client.DataServiceQuery%601>를 기반으로 <xref:System.Data.Services.Client.DataServiceCollection%601> 인스턴스를 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrders2Binding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders2.cs#customersorders2binding)]
 [!code-vb[Astoria Northwind Client#CustomersOrders2Binding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders2.vb#customersorders2binding)]  
  
## Windows Presentation Foundation 요소에 데이터 바인딩  
 <xref:System.Data.Services.Client.DataServiceCollection%601> 클래스는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 클래스에서 상속하기 때문에 바인딩에 <xref:System.Collections.ObjectModel.ObservableCollection%601> 클래스를 사용할 때처럼 WPF\(Windows Presentation Foundation\) 응용 프로그램의 요소 또는 컨트롤에 개체를 바인딩할 수 있습니다.  자세한 내용은 [데이터 바인딩\(Windows Presentation Foundation\)](../../../../docs/framework/wpf/data/data-binding-wpf.md)을 참조하세요.  데이터 서비스 데이터를 WPF 컨트롤에 바인딩하는 한 가지 방법은 요소의 `DataContext` 속성을 쿼리 결과가 포함된 <xref:System.Data.Services.Client.DataServiceCollection%601> 클래스 인스턴스로 설정하는 것입니다.  이 경우 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 사용하여 컨트롤의 개체 소스를 설정합니다.  <xref:System.Windows.Controls.ItemsControl.DisplayMemberPath%2A> 속성을 사용하면 표시할 바인딩된 개체의 속성을 지정할 수 있습니다.  탐색 속성에서 반환된 관련 개체에 요소를 바인딩하는 경우 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성의 정의된 바인딩에 경로를 포함합니다.  이 경로는 부모 컨트롤의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성에 설정된 루트 개체에 상대적입니다.  다음 예제에서는 <xref:System.Windows.Controls.StackPanel> 요소의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 설정하여 부모 컨트롤을 고객 개체의 <xref:System.Data.Services.Client.DataServiceCollection%601>에 바인딩합니다.  
  
 [!code-csharp[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderscustom.xaml.cs#masterdetailbinding)]
 [!code-csharp[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf.xaml.cs#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml.vb#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml.vb#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom2.xaml.vb#masterdetailbinding)]  
  
 다음 예제에서는 자식 <xref:System.Windows.Controls.DataGrid> 및 <xref:System.Windows.Controls.ComboBox> 컨트롤의 XAML 바인딩 정의를 보여 줍니다.  
  
 [!code-xml[Astoria Northwind Client#MasterDetailXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml#masterdetailxaml)]  
  
 자세한 내용은 [방법: Windows Presentation Foundation 요소에 데이터 바인딩](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)을 참조하세요.  
  
 엔터티가 일대다 또는 다대다 관계에 참여하는 경우 관계의 탐색 속성에서 관련 개체의 컬렉션을 반환합니다.  **서비스 참조 추가** 대화 상자나 DataSvcUtil.exe 도구를 사용하여 클라이언트 데이터 서비스 클래스를 생성하는 경우 탐색 속성에서 <xref:System.Data.Services.Client.DataServiceCollection%601> 인스턴스를 반환합니다.  이렇게 하면 관련 개체를 컨트롤에 바인딩하고 관련 엔터티에 대한 마스터\-세부 정보 바인딩 패턴과 같은 일반적인 WPF 바인딩 시나리오를 지원할 수 있습니다.  위의 XAML 예제에 포함된 XAML 코드에서는 마스터 <xref:System.Data.Services.Client.DataServiceCollection%601>을 루트 데이터 요소에 바인딩합니다.  주문 <xref:System.Windows.Controls.DataGrid>는 선택한 고객 개체에서 반환된 주문 <xref:System.Data.Services.Client.DataServiceCollection%601>에 바인딩되고, 고객 개체는 <xref:System.Windows.Window>의 루트 데이터 요소에 바인딩됩니다.  
  
## Windows Forms 컨트롤에 데이터 바인딩  
 개체를 Windows Form 컨트롤에 바인딩하려면 컨트롤의 `DataSource` 속성을 쿼리 결과가 포함된 <xref:System.Data.Services.Client.DataServiceCollection%601> 클래스 인스턴스로 설정합니다.  
  
> [!NOTE]
>  데이터 바인딩은 <xref:System.Collections.Specialized.INotifyCollectionChanged> 및 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하여 변경 이벤트를 수신 대기하는 컨트롤에만 지원됩니다.  컨트롤이 이러한 종류의 변경 알림을 지원하지 않으면 기본 <xref:System.Data.Services.Client.DataServiceCollection%601>에 대한 변경 내용이 바인딩된 컨트롤에 반영되지 않습니다.  
  
 다음 예제에서는 <xref:System.Data.Services.Client.DataServiceCollection%601>을 <xref:System.Windows.Forms.ComboBox> 컨트롤에 바인딩합니다.  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders.cs#customersordersdatabindingspecific)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders.vb#customersordersdatabindingspecific)]  
  
 **서비스 참조 추가** 대화 상자를 사용하여 클라이언트 데이터 서비스 클래스를 생성하는 경우 생성된 <xref:System.Data.Services.Client.DataServiceContext>를 기반으로 하는 프로젝트 데이터 소스도 만들어집니다.  이 데이터 소스를 사용하면 **데이터 소스** 창에서 디자이너로 항목을 끌어다 놓는 간단한 방법으로 데이터 서비스의 데이터를 표시하는 UI 요소나 컨트롤을 만들 수 있습니다.  이러한 항목은 데이터 소스에 바인딩된 응용 프로그램 UI의 요소가 됩니다.  자세한 내용은 [방법: 프로젝트 데이터 원본을 사용하여 데이터 바인딩](../../../../docs/framework/data/wcf/how-to-bind-data-using-a-project-data-source-wcf-data-services.md)을 참조하세요.  
  
## 페이징 데이터 바인딩  
 단일 응답 메시지에 반환되는 쿼리된 데이터 양을 제한하도록 데이터 서비스를 구성할 수 있습니다.  자세한 내용은 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)을 참조하세요.  데이터 서비스에서 응답 데이터를 페이징하는 경우 각 응답에 다음 결과 페이지를 반환하는 데 사용되는 링크가 포함됩니다.  자세한 내용은 [지연된 콘텐츠 로드](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)을 참조하세요.  이 경우 다음 예제와 같이 <xref:System.Data.Services.Client.DataServiceQueryContinuation.NextLinkUri%2A> 속성에서 가져온 URI를 전달하여 <xref:System.Data.Services.Client.DataServiceCollection%601>의 <xref:System.Data.Services.Client.DataServiceCollection%601.Load%2A> 메서드를 호출함으로써 명시적으로 페이지를 로드해야 합니다.  
  
 [!code-csharp[Astoria Northwind Client#BindPagedDataSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf3.xaml.cs#bindpageddataspecific)]
 [!code-vb[Astoria Northwind Client#BindPagedDataSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml.vb#bindpageddataspecific)]  
  
 관련 개체도 유사한 방식으로 로드됩니다.  자세한 내용은 [방법: Windows Presentation Foundation 요소에 데이터 바인딩](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)을 참조하세요.  
  
## 데이터 바인딩 동작 사용자 지정  
 <xref:System.Data.Services.Client.DataServiceCollection%601> 클래스를 사용하면 개체 추가 또는 제거와 같이 컬렉션이 변경될 때 및 컬렉션의 개체 속성이 변경될 때 발생하는 이벤트를 가로챌 수 있습니다.  데이터 바인딩 이벤트를 수정하여 다음 제약 조건이 포함된 기본 동작을 재정의할 수 있습니다.  
  
-   대리자 내에서는 유효성 검사가 수행되지 않습니다.  
  
-   엔터티를 추가하면 자동으로 관련 엔터티가 추가됩니다.  
  
-   엔터티를 삭제해도 관련 엔터티는 삭제되지 않습니다.  
  
 새 <xref:System.Data.Services.Client.DataServiceCollection%601> 인스턴스를 만드는 경우 바인딩된 개체가 변경될 때 발생하는 이벤트를 처리하는 메서드에 대리자를 정의하는 다음 매개 변수를 지정할 수 있습니다.  
  
-   `entityChanged` \- 바인딩된 개체의 속성이 변경될 때 호출되는 메서드입니다.  이 <xref:System.Func%602> 대리자는 <xref:System.Data.Services.Client.EntityChangedParams> 개체를 받아들이고 <xref:System.Data.Services.Client.DataServiceContext>에서 <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A>를 호출하는 기본 동작이 수행되어야 하는지 여부를 나타내는 부울 값을 반환합니다.  
  
-   `entityCollectionChanged` \- 개체가 바인딩 컬렉션에 추가 또는 제거될 때 호출되는 메서드입니다.  이 <xref:System.Func%602> 대리자는 <xref:System.Data.Services.Client.EntityCollectionChangedParams> 개체를 받아들이고 <xref:System.Collections.Specialized.NotifyCollectionChangedAction> 작업에 대해 <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A>를 호출하거나 <xref:System.Data.Services.Client.DataServiceContext>에서 <xref:System.Collections.Specialized.NotifyCollectionChangedAction> 작업에 대해 <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A>를 호출하는 기본 동작이 수행되어야 하는지 여부를 나타내는 부울 값을 반환합니다.  
  
> [!NOTE]
>  [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 이러한 대리자에 구현한 사용자 지정 동작의 유효성 검사를 수행하지 않습니다.  
  
 다음 예제에서 <xref:System.Collections.Specialized.NotifyCollectionChangedAction> 작업은 <xref:System.Data.Services.Client.DataServiceContext.DeleteLink%2A> 및 <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> 메서드를 호출하여 삭제된 `Orders` 엔터티에 속하는 `Orders_Details` 엔터티를 제거하도록 사용자 지정됩니다.  이 사용자 지정 작업은 부모 엔터티가 삭제될 때 종속 엔터티가 자동으로 삭제되지 않으므로 수행됩니다.  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderscustom.xaml.cs#customersordersdeleterelated)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml.vb#customersordersdeleterelated)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom2.xaml.vb#customersordersdeleterelated)]  
  
 자세한 내용은 [방법: 데이터 바인딩 동작 사용자 지정](../../../../docs/framework/data/wcf/how-to-customize-data-binding-behaviors-wcf-data-services.md)을 참조하세요.  
  
 <xref:System.Collections.ObjectModel.Collection%601.Remove%2A> 메서드를 사용하여 <xref:System.Data.Services.Client.DataServiceCollection%601>에서 개체가 제거될 때의 기본 동작은 해당 개체가 <xref:System.Data.Services.Client.DataServiceContext>에서도 삭제된 것으로 표시되는 것입니다.  이 동작을 변경하려면 <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> 이벤트가 발생할 때 호출되는 `entityCollectionChanged` 매개 변수의 메서드로 대리자를 지정합니다.  
  
## 사용자 지정 클라이언트 데이터 클래스를 사용하여 데이터 바인딩  
 개체를 <xref:System.Data.Services.Client.DataServiceCollection%601>으로 로드할 수 있으려면 개체 자체에서 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현해야 합니다.  **서비스 참조 추가** 대화 상자나 [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) 도구를 사용할 때 생성되는 데이터 서비스 클라이언트 클래스는 이 인터페이스를 구현합니다.  고유한 클라이언트 데이터 클래스를 제공하는 경우 데이터 바인딩에 다른 컬렉션 형식을 사용해야 합니다.  개체가 변경되면 데이터 바인딩된 컨트롤에서 이벤트를 처리하여 <xref:System.Data.Services.Client.DataServiceContext> 클래스의 다음 메서드를 호출해야 합니다.  
  
-   <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> \- 새 개체가 컬렉션에 추가된 경우  
  
-   <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> \- 개체가 컬렉션에서 제거된 경우  
  
-   <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> \- 컬렉션에 있는 개체의 속성이 변경된 경우  
  
-   <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> \- 개체가 관련 개체의 컬렉션에 추가된 경우  
  
-   <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> \- 개체가 관련 개체의 컬렉션에 추가된 경우  
  
 자세한 내용은 [데이터 서비스 업데이트](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)을 참조하세요.  
  
## 참고 항목  
 [방법: 수동으로 클라이언트 데이터 서비스 클래스 생성](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)   
 [방법: 데이터 서비스 참조 추가](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)