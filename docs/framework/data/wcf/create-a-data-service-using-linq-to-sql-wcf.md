---
title: "방법: LINQ to SQL 데이터 원본을 사용하여 데이터 서비스 만들기(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 52529689242342afa8920a7b01b532a24337f562
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a><span data-ttu-id="b3657-102">방법: LINQ to SQL 데이터 원본을 사용하여 데이터 서비스 만들기(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="b3657-102">How to: Create a Data Service Using a LINQ to SQL Data Source (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="b3657-103">에서는 엔터티 데이터를 데이터 서비스로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-103"> exposes entity data as a data service.</span></span> <span data-ttu-id="b3657-104">리플렉션 공급자 반환 하는 멤버를 노출 하는 클래스를 기반으로 하는 데이터 모델을 정의할 수 있습니다는 <xref:System.Linq.IQueryable%601> 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-104">The reflection provider enables you to define a data model that is based on any class that exposes members that return an <xref:System.Linq.IQueryable%601> implementation.</span></span> <span data-ttu-id="b3657-105">데이터 소스의 데이터를 업데이트할 수 있으려면 이러한 클래스도 <xref:System.Data.Services.IUpdatable> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-105">To be able to make updates to data in the data source, these classes must also implement the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="b3657-106">자세한 내용은 참조 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-106">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span> <span data-ttu-id="b3657-107">이 항목에서는 리플렉션 공급자를 사용하여 Northwind 샘플 데이터베이스에 액세스하는 LINQ to SQL 클래스를 만드는 방법과 이러한 데이터 클래스를 기반으로 하는 데이터 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-107">This topic shows you how to create LINQ to SQL classes that access the Northwind sample database by using the reflection provider, as well as how to create the data service that is based on these data classes.</span></span>  
  
### <a name="to-add-linq-to-sql-classes-to-a-project"></a><span data-ttu-id="b3657-108">프로젝트에 LINQ to SQL 클래스를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="b3657-108">To add LINQ to SQL classes to a project</span></span>  
  
1.  <span data-ttu-id="b3657-109">Visual Basic 또는 C# 응용 프로그램 내에 **프로젝트** 메뉴를 클릭 **새 항목 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-109">From within a Visual Basic or C# application, on the **Project** menu, click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="b3657-110">클릭는 **LINQ to SQL 클래스** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="b3657-110">Click the **LINQ to SQL Classes** template.</span></span>  
  
3.  <span data-ttu-id="b3657-111">이름을 변경한 **Northwind.dbml**합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-111">Change the name to **Northwind.dbml**.</span></span>  
  
4.  <span data-ttu-id="b3657-112">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-112">Click **Add**.</span></span>  
  
     <span data-ttu-id="b3657-113">Northwind.dbml 파일이 프로젝트에 추가되고 Object Relational Designer(O/R Designer)가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-113">The Northwind.dbml file is added to the project and the Object Relational Designer (O/R Designer) opens.</span></span>  
  
5.  <span data-ttu-id="b3657-114">**서버**/**데이터베이스 탐색기**, Northwind에서 확장 **테이블** 끌어서는 `Customers` Object Relational Designer (O/R로 테이블 디자이너)입니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-114">In **Server**/**Database Explorer**, under Northwind, expand **Tables** and drag the `Customers` table onto the Object Relational Designer (O/R Designer).</span></span>  
  
     <span data-ttu-id="b3657-115">`Customer` 엔터티 클래스가 만들어져 디자인 화면에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-115">A `Customer` entity class is created and appears on the design surface.</span></span>  
  
6.  <span data-ttu-id="b3657-116">`Orders`, `Order_Details` 및 `Products` 테이블에 대해 6단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-116">Repeat step 6 for the `Orders`, `Order_Details`, and `Products` tables.</span></span>  
  
7.  <span data-ttu-id="b3657-117">LINQ to SQL 클래스 및 클릭 나타내는 새.dbml 파일을 마우스 오른쪽 단추로 클릭 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-117">Right-click the new .dbml file that represents the LINQ to SQL classes and click **View Code**.</span></span>  
  
     <span data-ttu-id="b3657-118">이렇게 하면 <xref:System.Data.Linq.DataContext> 클래스에서 상속되는 클래스(이 경우 `NorthwindDataContext`)의 partial 클래스 정의가 포함된 Northwind.cs라는 새 코드 숨김 페이지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-118">This creates a new code-behind page named Northwind.cs that contains a partial class definition for the class that inherits from the <xref:System.Data.Linq.DataContext> class, which in this case is `NorthwindDataContext`.</span></span>  
  
8.  <span data-ttu-id="b3657-119">Northwind.cs 코드 파일의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-119">Replace the contents of the Northwind.cs code file with the following code.</span></span> <span data-ttu-id="b3657-120">이 코드는 LINQ to SQL에서 생성된 <xref:System.Data.Linq.DataContext> 및 데이터 클래스를 확장하여 리플렉션 공급자를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-120">This code implements the reflection provider by extending the <xref:System.Data.Linq.DataContext> and data classes generated by LINQ to SQL:</span></span>  
  
     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.vb#linq2sqlprovider)]  
  
### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a><span data-ttu-id="b3657-121">LINQ to SQL 기반 데이터 모델을 사용하여 데이터 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b3657-121">To create a data service by using a LINQ to SQL-based data model</span></span>  
  
1.  <span data-ttu-id="b3657-122">**솔루션 탐색기**ASP.NET 프로젝트 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **새 항목 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-122">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="b3657-123">에 **새 항목 추가** 대화 상자에서 **WCF 데이터 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-123">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
3.  <span data-ttu-id="b3657-124">서비스에 대 한 이름을 입력 한 다음 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-124">Supply a name for the service, and then click **OK**.</span></span>  
  
     <span data-ttu-id="b3657-125">Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-125">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="b3657-126">기본적으로 코드 편집기 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-126">By default, the code-editor window opens.</span></span>  
  
4.  <span data-ttu-id="b3657-127">데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식(이 경우 `NorthwindDataContext`)으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-127">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindDataContext`.</span></span>  
  
5.  <span data-ttu-id="b3657-128">데이터 서비스 코드에서 `InitializeService` 함수의 자리 표시자 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-128">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.svc.vb#enableaccess)]  
  
     <span data-ttu-id="b3657-129">이렇게 하면 권한 있는 클라이언트가 지정된 세 개 엔터티 집합의 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-129">This enables authorized clients to access resources for the three specified entity sets.</span></span>  
  
6.  <span data-ttu-id="b3657-130">웹 브라우저를 사용 하 여 Northwind.svc 데이터 서비스를 테스트 하려면이 항목의 지침에 따라 [웹 브라우저에서 서비스 액세스](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3657-130">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3657-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3657-131">See Also</span></span>  
 [<span data-ttu-id="b3657-132">방법: ADO.NET Entity Framework 데이터 원본을 사용 하 여 데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="b3657-132">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)  
 [<span data-ttu-id="b3657-133">방법: 리플렉션 공급자를 사용 하 여 데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="b3657-133">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [<span data-ttu-id="b3657-134">데이터 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="b3657-134">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
