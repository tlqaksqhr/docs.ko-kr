---
title: "방법: 데이터 서비스에 액세스할 수 있도록 설정(WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, 구성"
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 방법: 데이터 서비스에 액세스할 수 있도록 설정(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서는 데이터 서비스에서 노출하는 리소스에 대한 액세스 권한을 명시적으로 부여해야 합니다.  즉, 새 데이터 서비스를 만든 후 엔터티 집합으로 개별 리소스에 대한 액세스 권한을 명시적으로 제공해야 합니다.  이 항목에서는 [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료할 때 만들어지는 Northwind 데이터 서비스의 다섯 엔터티 집합에 대한 읽기 및 쓰기 액세스를 활성화하는 방법을 보여 줍니다. <xref:System.Data.Services.EntitySetRights> 열거형은 <xref:System.FlagsAttribute>를 사용하여 정의되기 때문에 논리 OR 연산자를 사용하여 단일 엔터티 집합에 여러 권한을 지정할 수 있습니다.  
  
> [!NOTE]
>  ASP.NET 응용 프로그램에 액세스할 수 있는 클라이언트는 데이터 서비스에 의해 노출되는 리소스에도 액세스할 수 있습니다.  리소스에 무단으로 액세스할 수 없도록 하려면 프로덕션 데이터 서비스에서 응용 프로그램 자체에도 보안을 설정해야 합니다.  자세한 내용은 [NIB: ASP.NET Security](http://msdn.microsoft.com/ko-kr/04b37532-18d9-40b4-8e5f-ee09a70b311d)을 참조하세요.  
  
### 데이터 서비스에 액세스할 수 있도록 설정하려면  
  
-   데이터 서비스 코드에서 `InitializeService` 함수의 자리 표시자 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     이렇게 하면 클라이언트가 `Orders` 및 `Order_Details` 엔터티 집합에 대한 읽기 및 쓰기 액세스 권한과 `Customers` 엔터티 집합에 대한 읽기 전용 액세스 권한을 가질 수 있습니다.  
  
## 참고 항목  
 [방법: IIS에서 실행되는 WCF Data Services 개발](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)   
 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)