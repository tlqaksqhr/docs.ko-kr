---
title: "방법: 프로젝트 데이터 원본을 사용하여 데이터 바인딩(WCF Data Services) | Microsoft Docs"
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
ms.assetid: 2477af0a-676f-44f7-b73d-e66208785509
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 방법: 프로젝트 데이터 원본을 사용하여 데이터 바인딩(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 응용 프로그램에서 생성된 데이터 개체를 기반으로 하는 데이터 소스를 만들 수 있습니다.  **서비스 참조 추가** 대화 상자를 사용하여 데이터 서비스에 참조를 추가하면 생성된 클라이언트 데이터 클래스와 함께 프로젝트 데이터 소스가 만들어집니다. 데이터 서비스가 노출하는 각 엔터티 집합에 대해 하나의 데이터 소스가 만들어집니다.  **데이터 소스** 창에서 디자이너로 이러한 데이터 소스 항목을 끌어다 놓으면 서비스의 데이터를 표시하는 폼을 만들 수 있습니다.  이러한 항목은 데이터 소스에 바인딩된 컨트롤이 됩니다.  실행 중에 이 데이터 소스는 데이터 서비스 쿼리에서 반환하는 개체로 채워지는 <xref:System.Data.Services.Client.DataServiceCollection%601> 클래스 인스턴스에 바인딩됩니다.  자세한 내용은 [컨트롤에 데이터 바인딩](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)을 참조하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다.  이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료하면 만들어집니다.  
  
### WPF 창에서 프로젝트 데이터 소스를 사용하려면  
  
1.  WPF 프로젝트에서 Northwind 데이터 서비스에 대한 참조를 추가합니다.  자세한 내용은 [방법: 데이터 서비스 참조 추가](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)을 참조하세요.  
  
2.  **데이터 소스** 창의 **NorthwindEntities** 프로젝트 데이터 소스에서 `Customers` 노드를 확장합니다.  
  
3.  **CustomerID** 항목을 클릭하고 목록에서 **ComboBox**를 선택한 다음 **Customers** 노드에서 디자이너로 **CustomerID** 항목을 끌어다 놓습니다.  
  
     창에 대한 XAML 파일에 다음 개체 요소가 만들어집니다.  
  
    -   `customersViewSource`라는 <xref:System.Windows.Data.CollectionViewSource> 요소.  최상위 <xref:System.Windows.Controls.Grid> 개체 요소의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성은 새 <xref:System.Windows.Data.CollectionViewSource>로 설정됩니다.  
  
    -   `CustomerID`라는 데이터 바인딩된 <xref:System.Windows.Controls.ComboBox>  
  
    -   <xref:System.Windows.Controls.Label>  
  
4.  **Orders** 탐색 속성을 디자이너로 끌어다 놓습니다.  
  
     창에 대한 XAML 파일에 다음 개체 요소가 추가로 만들어집니다.  
  
    -   소스가 `customerViewSource`인 `customersOrdersViewSource`라는 두 번째 <xref:System.Windows.Data.CollectionViewSource> 요소  
  
    -   `ordersDataGrid`라는 데이터 바인딩된 <xref:System.Windows.Controls.DataGrid> 컨트롤  
  
5.  \(선택 사항\) **Customers** 노드에서 디자이너로 추가 항목을 끌어다 놓습니다.  
  
6.  폼의 코드 페이지를 열고 다음 `using` 문\(Visual Basic에서는 `Imports`\)을 추가합니다.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersusingwpf)]  
  
7.  폼을 정의하는 partial 클래스에서 <xref:System.Data.Objects.ObjectContext> 인스턴스를 만들고 `customerID` 상수를 정의하는 다음 코드를 추가합니다.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersdefinitionwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf2.xaml.vb#customersordersdefinitionwpf)]  
  
8.  디자이너에서 창을 선택합니다.  
  
    > [!NOTE]
    >  창 안에 있는 콘텐츠를 선택하는 대신 창 자체를 선택해야 합니다.  창을 선택하면 **속성** 창의 위쪽에 있는 **이름** 텍스트 상자에 창의 이름이 포함되어야 합니다.  
  
9. **속성** 창에서 **이벤트** 단추를 선택합니다.  
  
10. **로드됨** 이벤트를 찾은 후 이 이벤트 옆에 있는 드롭다운 목록을 두 번 클릭합니다.  
  
     창에 대한 코드 숨김 파일이 열리고 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기가 생성됩니다.  
  
11. 새로 만들어진 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기에서 다음 코드를 복사하여 붙여 넣습니다.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersdatabindingwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf2.xaml.vb#customersordersdatabindingwpf)]  
  
12. 이 코드에서는 Northwind 데이터 서비스의 관련 `Orders` 개체와 함께 `Customers`의 <xref:System.Collections.Generic.IEnumerable%601>을 반환하고 `customersViewSource`에 바인딩하는 LINQ 쿼리의 실행을 기준으로 `Customers` 형식에 대해 <xref:System.Data.Services.Client.DataServiceCollection%601> 인스턴스를 만듭니다.  
  
### Windows Form에서 프로젝트 데이터 소스를 사용하려면  
  
1.  **데이터 소스** 창의 **NorthwindEntities** 프로젝트 데이터 소스에서 **Customers** 노드를 확장합니다.  
  
2.  **CustomerID** 항목을 클릭하고 목록에서 **ComboBox**를 선택한 다음 **Customers** 노드에서 디자이너로 **CustomerID** 항목을 끌어다 놓습니다.  
  
     폼에 다음 컨트롤이 만들어집니다.  
  
    -   `customersBindingSource`라는 <xref:System.Windows.Forms.BindingSource> 인스턴스.  
  
    -   `customersBindingNavigator`라는 <xref:System.Windows.Forms.BindingNavigator> 인스턴스.  이 컨트롤은 필요 없으므로 삭제할 수 있습니다.  
  
    -   `CustomerID`라는 데이터 바인딩된 <xref:System.Windows.Forms.ComboBox>  
  
    -   <xref:System.Windows.Forms.Label>  
  
3.  **Orders** 탐색 속성을 폼으로 끌어다 놓습니다.  
  
4.  컨트롤의 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성이 `customersBindingSource`로 설정되고 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 속성이 `Customers`로 설정된 `ordersBindingSource` 컨트롤이 만들어집니다.  `ordersDataGridView` 데이터 바인딩된 컨트롤도 폼에 만들어지며, 적절한 제목의 레이블 컨트롤이 함께 표시됩니다.  
  
5.  \(선택 사항\) **Customers** 노드에서 디자이너로 추가 항목을 끌어다 놓습니다.  
  
6.  폼의 코드 페이지를 열고 다음 `using` 문\(Visual Basic에서는 `Imports`\)을 추가합니다.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders.cs#customersordersusing)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders.vb#customersordersusing)]  
  
7.  폼을 정의하는 partial 클래스에서 <xref:System.Data.Objects.ObjectContext> 인스턴스를 만들고 `customerID` 상수를 정의하는 다음 코드를 추가합니다.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders.cs#customersordersdefinition)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders.vb#customersordersdefinition)]  
  
8.  폼 디자이너에서 폼을 두 번 클릭합니다.  
  
     폼에 대한 코드 페이지가 열리고 폼의 `Load` 이벤트를 처리하는 메서드가 만들어집니다.  
  
9. `Load` 이벤트 처리기에서 다음 코드를 복사하여 붙여 넣습니다.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders.cs#customersordersdatabinding)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders.vb#customersordersdatabinding)]  
  
10. 이 코드에서는 Northwind 데이터 서비스에서 `Customers`의 <xref:System.Collections.Generic.IEnumerable%601>을 반환하고 `customersBindingSource`에 바인딩하는 <xref:System.Data.Services.Client.DataServiceQuery%601>의 실행을 기준으로 `Customers` 형식에 대해 <xref:System.Data.Services.Client.DataServiceCollection%601> 인스턴스를 만듭니다.  
  
## 참고 항목  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [방법: Windows Presentation Foundation 요소에 데이터 바인딩](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)