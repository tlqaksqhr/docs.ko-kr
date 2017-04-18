---
title: "방법: 비동기 Windows Presentation Framework 응용 프로그램 만들기(WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, 비동기 작업"
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 방법: 비동기 Windows Presentation Framework 응용 프로그램 만들기(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하면 데이터 서비스에서 가져온 데이터를 WPF\(Windows Presentation Framework\) 응용 프로그램의 UI 요소에 바인딩할 수 있습니다.  자세한 내용은 [컨트롤에 데이터 바인딩](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)을 참조하세요. 비동기 방식으로 데이터 서비스에 대해 작업을 실행할 수도 있습니다. 이렇게 하면 응용 프로그램이 데이터 서비스 요청에 대한 응답을 기다리는 동안 계속 응답할 수 있습니다.  데이터 서비스에 비동기적으로 액세스하려면 Silverlight용 응용 프로그램이 필요합니다.  자세한 내용은 [비동기 작업](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)을 참조하세요.  
  
 이 항목에서는 데이터 서비스에 비동기적으로 액세스하고 그 결과를 WPF 응용 프로그램의 요소에 바인딩하는 방법을 보여 줍니다.  이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다.  이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료하면 만들어집니다.  
  
## 예제  
 다음 XAML에서는 WPF 응용 프로그램의 창을 정의합니다.  
  
 [!code-xml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## 예제  
 XAML 파일의 다음 코드 숨김 페이지에서는 데이터 서비스를 사용하여 비동기 쿼리를 실행하고 그 결과를 WPF 창의 요소에 바인딩합니다.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## 참고 항목  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)