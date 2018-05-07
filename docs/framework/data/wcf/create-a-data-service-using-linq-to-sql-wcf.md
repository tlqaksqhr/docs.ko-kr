---
title: '방법: LINQ to SQL 데이터 원본을 사용하여 데이터 서비스 만들기(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
ms.openlocfilehash: 5769ff5296d096df41b59104ad0581f0e816c648
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a>방법: LINQ to SQL 데이터 원본을 사용하여 데이터 서비스 만들기(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서는 엔터티 데이터를 데이터 서비스로 노출합니다. 리플렉션 공급자 반환 하는 멤버를 노출 하는 클래스를 기반으로 하는 데이터 모델을 정의할 수 있습니다는 <xref:System.Linq.IQueryable%601> 구현 합니다. 데이터 소스의 데이터를 업데이트할 수 있으려면 이러한 클래스도 <xref:System.Data.Services.IUpdatable> 인터페이스를 구현해야 합니다. 자세한 내용은 참조 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)합니다. 이 항목에서는 리플렉션 공급자를 사용하여 Northwind 샘플 데이터베이스에 액세스하는 LINQ to SQL 클래스를 만드는 방법과 이러한 데이터 클래스를 기반으로 하는 데이터 서비스를 만드는 방법을 보여 줍니다.  
  
### <a name="to-add-linq-to-sql-classes-to-a-project"></a>프로젝트에 LINQ to SQL 클래스를 추가하려면  
  
1.  Visual Basic 또는 C# 응용 프로그램 내에 **프로젝트** 메뉴를 클릭 **새 항목 추가**합니다.  
  
2.  클릭는 **LINQ to SQL 클래스** 템플릿.  
  
3.  이름을 변경한 **Northwind.dbml**합니다.  
  
4.  **추가**를 클릭합니다.  
  
     Northwind.dbml 파일이 프로젝트에 추가되고 Object Relational Designer(O/R Designer)가 열립니다.  
  
5.  **서버**/**데이터베이스 탐색기**, Northwind에서 확장 **테이블** 끌어서는 `Customers` Object Relational Designer (O/R로 테이블 디자이너)입니다.  
  
     `Customer` 엔터티 클래스가 만들어져 디자인 화면에 표시됩니다.  
  
6.  `Orders`, `Order_Details` 및 `Products` 테이블에 대해 6단계를 반복합니다.  
  
7.  LINQ to SQL 클래스 및 클릭 나타내는 새.dbml 파일을 마우스 오른쪽 단추로 클릭 **코드 보기**합니다.  
  
     이렇게 하면 <xref:System.Data.Linq.DataContext> 클래스에서 상속되는 클래스(이 경우 `NorthwindDataContext`)의 partial 클래스 정의가 포함된 Northwind.cs라는 새 코드 숨김 페이지가 만들어집니다.  
  
8.  Northwind.cs 코드 파일의 내용을 다음 코드로 바꿉니다. 이 코드는 LINQ to SQL에서 생성된 <xref:System.Data.Linq.DataContext> 및 데이터 클래스를 확장하여 리플렉션 공급자를 구현합니다.  
  
     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.vb#linq2sqlprovider)]  
  
### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a>LINQ to SQL 기반 데이터 모델을 사용하여 데이터 서비스를 만들려면  
  
1.  **솔루션 탐색기**ASP.NET 프로젝트 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **새 항목 추가**합니다.  
  
2.  에 **새 항목 추가** 대화 상자에서 **WCF 데이터 서비스**합니다.  
  
3.  서비스에 대 한 이름을 입력 한 다음 클릭 **확인**합니다.  
  
     Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다. 기본적으로 코드 편집기 창이 열립니다.  
  
4.  데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식(이 경우 `NorthwindDataContext`)으로 바꿉니다.  
  
5.  데이터 서비스 코드에서 `InitializeService` 함수의 자리 표시자 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.svc.vb#enableaccess)]  
  
     이렇게 하면 권한 있는 클라이언트가 지정된 세 개 엔터티 집합의 리소스에 액세스할 수 있습니다.  
  
6.  웹 브라우저를 사용 하 여 Northwind.svc 데이터 서비스를 테스트 하려면이 항목의 지침에 따라 [웹 브라우저에서 서비스 액세스](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: ADO.NET Entity Framework 데이터 원본을 사용하여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)  
 [방법: 리플렉션 공급자 사용하여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [Data Services 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
