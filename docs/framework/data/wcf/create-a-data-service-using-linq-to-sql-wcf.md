---
title: "방법: LINQ to SQL 데이터 소스를 사용하여 데이터 서비스 만들기(WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, LINQ to SQL"
  - "WCF Data Services, 공급자"
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 방법: LINQ to SQL 데이터 소스를 사용하여 데이터 서비스 만들기(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서는 엔터티 데이터를 데이터 서비스로 노출합니다.  리플렉션 공급자를 사용하면 <xref:System.Linq.IQueryable%601> 구현을 반환하는 멤버를 노출하는 클래스를 기반으로 하여 데이터 모델을 정의할 수 있습니다.  데이터 소스의 데이터를 업데이트할 수 있으려면 이러한 클래스도 <xref:System.Data.Services.IUpdatable> 인터페이스를 구현해야 합니다.  자세한 내용은 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)을 참조하세요.  이 항목에서는 리플렉션 공급자를 사용하여 Northwind 샘플 데이터베이스에 액세스하는 LINQ to SQL 클래스를 만드는 방법과 이러한 데이터 클래스를 기반으로 하는 데이터 서비스를 만드는 방법을 보여 줍니다.  
  
### 프로젝트에 LINQ to SQL 클래스를 추가하려면  
  
1.  Visual Basic 또는 C\# 응용 프로그램의 **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
2.  **LINQ to SQL 클래스** 템플릿을 클릭합니다.  
  
3.  이름을 Northwind.dbml로 변경합니다.  
  
4.  **추가**를 클릭합니다.  
  
     Northwind.dbml 파일이 프로젝트에 추가되고 Object Relational Designer\(O\/R Designer\)가 열립니다.  
  
5.  **서버**\/**데이터베이스 탐색기**에서 Northwind 아래의 **테이블**을 확장하고 `Customers` 테이블을 Object Relational Designer\(O\/R Designer\)로 끌어 옵니다.  
  
     `Customer` 엔터티 클래스가 만들어져 디자인 화면에 표시됩니다.  
  
6.  `Orders`, `Order_Details` 및 `Products` 테이블에 대해 6단계를 반복합니다.  
  
7.  LINQ to SQL 클래스를 나타내는 새 .dbml 파일을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 클릭합니다.  
  
     이렇게 하면 <xref:System.Data.Linq.DataContext> 클래스에서 상속되는 클래스\(이 경우 `NorthwindDataContext`\)의 partial 클래스 정의가 포함된 Northwind.cs라는 새 코드 숨김 페이지가 만들어집니다.  
  
8.  Northwind.cs 코드 파일의 내용을 다음 코드로 바꿉니다.  이 코드는 LINQ to SQL에서 생성된 <xref:System.Data.Linq.DataContext> 및 데이터 클래스를 확장하여 리플렉션 공급자를 구현합니다.  
  
     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.vb#linq2sqlprovider)]  
  
### LINQ to SQL 기반 데이터 모델을 사용하여 데이터 서비스를 만들려면  
  
1.  **솔루션 탐색기**에서 ASP.NET 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **새 항목 추가**를 클릭합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **WCF Data Services**를 선택합니다.  
  
3.  서비스의 이름을 지정하고 **확인**을 클릭합니다.  
  
     Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다.  기본적으로 코드 편집기 창이 열립니다.  
  
4.  데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식\(이 경우 `NorthwindDataContext`\)으로 바꿉니다.  
  
5.  데이터 서비스 코드에서 `InitializeService` 함수의 자리 표시자 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.svc.vb#enableaccess)]  
  
     이렇게 하면 권한 있는 클라이언트가 지정된 세 개 엔터티 집합의 리소스에 액세스할 수 있습니다.  
  
6.  웹 브라우저를 사용하여 Northwind.svc 데이터 서비스를 테스트하려면 [웹 브라우저에서 서비스 액세스](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md) 항목의 지침을 따릅니다.  
  
## 참고 항목  
 [방법: ADO.NET Entity Framework 데이터 원본을 사용하여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)   
 [방법: 리플렉션 공급자를 사용하여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)   
 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)