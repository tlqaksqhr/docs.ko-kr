---
title: 데이터 서비스 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: bb6e2f7c1160fa51cd897cc953ad0ed721559294
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33362839"
---
# <a name="creating-the-data-service"></a><span data-ttu-id="27024-102">데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="27024-102">Creating the Data Service</span></span>
<span data-ttu-id="27024-103">이 작업을 사용 하는 샘플 데이터 서비스 만듭니다 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 노출 하는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Northwind 샘플 데이터베이스를 기반으로 하는 피드입니다.</span><span class="sxs-lookup"><span data-stu-id="27024-103">In this task, you will create a sample data service that uses [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to expose an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed that is based on the Northwind sample database.</span></span> <span data-ttu-id="27024-104">작업에 필요한 기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="27024-104">The task involves the following basic steps:</span></span>  
  
1.  <span data-ttu-id="27024-105">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27024-105">Create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application.</span></span>  
  
2.  <span data-ttu-id="27024-106">[!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] 도구를 사용하여 데이터 모델을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-106">Define the data model by using the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] tools.</span></span>  
  
3.  <span data-ttu-id="27024-107">웹 응용 프로그램에 데이터 서비스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-107">Add the data service to the Web application.</span></span>  
  
4.  <span data-ttu-id="27024-108">데이터 서비스에 액세스할 수 있도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-108">Enable access to the data service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27024-109">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 이 작업을 완료할 때 만드는 웹 응용 프로그램이 실행 되는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 개발 서버를 Visual Studio에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-109">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application that you create when you complete this task runs on the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server provided by Visual Studio.</span></span> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="27024-110"> Development Server는 로컬 컴퓨터에서의 액세스만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-110"> Development Server only supports access from the local computer.</span></span> <span data-ttu-id="27024-111">개발 중에 보다 쉽게 데이터 서비스를 테스트하고 관련 문제를 해결하려면 IIS(인터넷 정보 서비스)를 사용하여 데이터 서비스를 호스트하는 응용 프로그램을 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="27024-111">To also make it easier to test and troubleshoot the data service during development, consider running the application that hosts the data service by using Internet Information Services (IIS).</span></span> <span data-ttu-id="27024-112">자세한 내용은 [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="27024-112">For more information, see [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).</span></span>  
  
### <a name="to-create-the-aspnet-web-application"></a><span data-ttu-id="27024-113">ASP.NET 웹 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="27024-113">To create the ASP.NET Web application</span></span>  
  
1.  <span data-ttu-id="27024-114">Visual Studio에서에 **파일** 메뉴 선택 **새로**를 선택한 후 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-114">In Visual Studio, on the **File** menu, select **New**, and then select **Project**.</span></span>  
  
2.  <span data-ttu-id="27024-115">에 **새 프로젝트** 대화 상자에서 Visual Basic 또는 Visual C#에서 **웹** 템플릿을 선택한 다음 선택 **ASP.NET 웹 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-115">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** template, and then select **ASP.NET Web Application**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27024-116">Visual Studio Web Developer를 사용하는 경우 새 웹 응용 프로그램 대신 새 웹 사이트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-116">If you use Visual Studio Web Developer, you must create a new Web site instead of a new Web application.</span></span>  
  
3.  <span data-ttu-id="27024-117">형식 `NorthwindService` 프로젝트의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-117">Type `NorthwindService` as the name of the project.</span></span>  
  
4.  <span data-ttu-id="27024-118">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="27024-119">(선택 사항) 웹 응용 프로그램의 특정 포트 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-119">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="27024-120">참고: 포트 번호 `12345`가 퀵 스타트의 나머지 부분에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="27024-120">Note: the port number `12345` is used in the rest of the quickstart.</span></span>  
  
    1.  <span data-ttu-id="27024-121">**솔루션 탐색기**의 이름을 마우스 오른쪽 단추로 클릭는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 프로젝트 방금 만든 마우스 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-121">In **Solution Explorer**, right-click the name of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project that you just created, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="27024-122">선택은 **웹** 탭의 값을 설정 하 고는 **특정 포트** 입력란을 `12345`합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-122">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>  
  
### <a name="to-define-the-data-model"></a><span data-ttu-id="27024-123">데이터 모델을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="27024-123">To define the data model</span></span>  
  
1.  <span data-ttu-id="27024-124">**솔루션 탐색기**의 이름을 마우스 오른쪽 단추로 클릭는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 프로젝트를 마우스 클릭 **새 항목 추가 합니다.**</span><span class="sxs-lookup"><span data-stu-id="27024-124">In **Solution Explorer**, right-click the name of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item.**</span></span>  
  
2.  <span data-ttu-id="27024-125">에 **새 항목 추가** 대화 상자를 클릭는 **데이터** 템플릿을 선택한 후 **ADO.NET 엔터티 데이터 모델**합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-125">In the **Add New Item** dialog box, click the **Data** template and then select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="27024-126">데이터 모델의 이름으로 입력 `Northwind.edmx`합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-126">For the name of the data model, type `Northwind.edmx`.</span></span>  
  
4.  <span data-ttu-id="27024-127">에 [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] 마법사 **데이터베이스에서 생성**, 클릭 하 고 **다음**합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-127">In the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard, select **Generate from Database**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="27024-128">다음 단계 중 하나를 수행 하 여 데이터 모델 데이터베이스에 연결 하 고 클릭 **다음**:</span><span class="sxs-lookup"><span data-stu-id="27024-128">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>  
  
    -   <span data-ttu-id="27024-129">데이터베이스 연결이 이미 구성 되어 있으면 클릭 **새 연결** 고 새 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27024-129">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="27024-130">자세한 내용은 참조 [하는 방법: SQL Server 데이터베이스에 대 한 연결 만들기](http://go.microsoft.com/fwlink/?LinkId=123631)합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-130">For more information, see [How to: Create Connections to SQL Server Databases](http://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="27024-131">이 SQL Server 인스턴스에는 Northwind 샘플 데이터베이스가 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-131">This SQL Server instance must have the Northwind sample database attached.</span></span>  
  
         <span data-ttu-id="27024-132">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="27024-132">\- or -</span></span>  
  
    -   <span data-ttu-id="27024-133">Northwind 데이터베이스에 연결할 수 있도록 데이터베이스 연결이 이미 구성되어 있는 경우 연결 목록에서 해당 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-133">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>  
  
6.  <span data-ttu-id="27024-134">마법사의 마지막 페이지에서 데이터베이스의 모든 테이블에 대한 확인란을 선택하고 뷰 및 저장 프로시저에 대한 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-134">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>  
  
7.  <span data-ttu-id="27024-135">클릭 **마침** 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="27024-135">Click **Finish** to close the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27024-136">생성된 이 데이터 모델은 엔터티 형식의 외래 키 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-136">This generated data model exposes foreign key properties on entity types.</span></span> <span data-ttu-id="27024-137">Visual Studio 2008을 사용하여 만들어진 데이터 모델에는 이러한 외래 키 속성이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27024-137">Data models created using Visual Studio 2008 do not include these foreign key properties.</span></span> <span data-ttu-id="27024-138">이 때문에 이 버전의 Northwind 데이터 서비스에 액세스하기 전에 Visual Studio 2008을 사용하여 만들어진 Northwind 데이터 서비스에 액세스하기 위해 만들어진 모든 클라이언트 응용 프로그램의 클라이언트 데이터 서비스 클래스를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-138">Because of this, you must update the client data service classes of any client applications that were created to access the Northwind data service that was created using Visual Studio 2008 before attempting to access this version of the Northwind data service.</span></span>  
  
### <a name="to-create-the-data-service"></a><span data-ttu-id="27024-139">데이터 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="27024-139">To create the data service</span></span>  
  
1.  <span data-ttu-id="27024-140">**솔루션 탐색기**의 이름을 마우스 오른쪽 단추로 클릭 하면 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 프로젝트를 마우스 클릭 **새 항목 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-140">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="27024-141">에 **새 항목 추가** 대화 상자에서 **WCF 데이터 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-141">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
3.  <span data-ttu-id="27024-142">서비스의 이름으로 입력 `Northwind`합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-142">For the name of the service, type `Northwind`.</span></span>  
  
     <span data-ttu-id="27024-143">StudioVisual 275575 새 서비스에 대 한 XML 태그 및 코드 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27024-143">Visual StudioVisual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="27024-144">기본적으로 코드 편집기 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="27024-144">By default, the code-editor window opens.</span></span> <span data-ttu-id="27024-145">**솔루션 탐색기**, 서비스 이름은, 확장명을 갖습니다. svc.cs 또는. svc.vb 합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-145">In **Solution Explorer**, the service will have the name, Northwind, with the extension .svc.cs or .svc.vb.</span></span>  
  
4.  <span data-ttu-id="27024-146">데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식(이 경우 `NorthwindEntities`)으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="27024-146">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="27024-147">클래스 정의는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="27024-147">The class definition should look this the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
### <a name="to-enable-access-to-data-service-resources"></a><span data-ttu-id="27024-148">데이터 서비스 리소스에 액세스할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="27024-148">To enable access to data service resources</span></span>  
  
1.  <span data-ttu-id="27024-149">데이터 서비스 코드에서 `InitializeService` 함수의 자리 표시자 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="27024-149">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="27024-150">이렇게 하면 권한 있는 클라이언트가 지정된 엔터티 집합의 리소스에 대한 읽기 및 쓰기 액세스 권한을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27024-150">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27024-151">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램에 액세스할 수 있는 클라이언트는 데이터 서비스에 의해 노출되는 리소스에도 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27024-151">Any client that can access the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="27024-152">리소스에 무단으로 액세스할 수 없도록 하려면 프로덕션 데이터 서비스에서 응용 프로그램 자체에도 보안을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-152">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="27024-153">자세한 내용은 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27024-153">For more information, see [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="27024-154">다음 단계</span><span class="sxs-lookup"><span data-stu-id="27024-154">Next Steps</span></span>  
 <span data-ttu-id="27024-155">노출 하는 새 데이터 서비스를 성공적으로 만들었습니다는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Northwind 샘플 데이터베이스를 기반으로 하는 피드 액세스에 대 한 사용 권한이 있는 클라이언트에 대 한 피드를 사용 하도록 설정한는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="27024-155">You have successfully created a new data service that exposes an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application.</span></span> <span data-ttu-id="27024-156">다음에는 Visual Studio에서 데이터 서비스를 시작하고 웹 브라우저를 통해 HTTP GET 요청을 전송하여 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="27024-156">Next, you will start the data service from Visual Studio and you will access the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by submitting HTTP GET requests through a Web browser:</span></span>  
  
 [<span data-ttu-id="27024-157">웹 브라우저에서 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="27024-157">Accessing the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a><span data-ttu-id="27024-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27024-158">See Also</span></span>  
 [<span data-ttu-id="27024-159">ADO.NET 엔터티 데이터 모델 도구</span><span class="sxs-lookup"><span data-stu-id="27024-159">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
