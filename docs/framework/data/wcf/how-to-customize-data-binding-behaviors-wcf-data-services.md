---
title: "방법: 데이터 바인딩 동작 사용자 지정(WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, 사용자 지정"
  - "WCF Data Services, 데이터 바인딩"
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 방법: 데이터 바인딩 동작 사용자 지정(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하면 바인딩 컬렉션에 개체가 추가 또는 제거되거나 속성 변경이 검색될 때 <xref:System.Data.Services.Client.DataServiceCollection%601>에서 호출하는 사용자 지정 논리를 제공할 수 있습니다.  이 사용자 지정 논리는 사용자 지정 메서드가 완료될 때 기본 동작이 수행되어야 하는 경우 `false` 값을 반환하고, 이벤트의 후속 처리가 중지되어야 하는 경우 `true`를 반환하는 메서드로 제공되며 <xref:System.Func%602> 대리자로 참조됩니다.  
  
 이 항목의 예제에서는 <xref:System.Data.Services.Client.DataServiceCollection%601>의 `entityChanged` 및 `entityCollectionChanged` 매개 변수에 대해 모두 사용자 지정 메서드를 제공합니다.  이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다.  이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료하면 만들어집니다.  
  
## 예제  
 XAML 파일에 대한 다음 코드 숨김 페이지에서는 바인딩 컬렉션에 바인딩된 데이터가 변경될 때 호출되는 사용자 지정 메서드를 사용하여 <xref:System.Data.Services.Client.DataServiceCollection%601>을 만듭니다.  <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged> 이벤트가 발생할 경우 제공된 메서드는 바인딩 컬렉션에서 제거된 항목이 데이터 서비스에서 삭제되지 않도록 합니다.  <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged> 이벤트가 발생할 경우 `ShipDate` 값의 유효성이 검사되어 이미 운송된 주문이 변경되지 않도록 합니다.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## 예제  
 다음 XAML에서는 이전 예제의 창을 정의합니다.  
  
 [!code-xml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## 참고 항목  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)