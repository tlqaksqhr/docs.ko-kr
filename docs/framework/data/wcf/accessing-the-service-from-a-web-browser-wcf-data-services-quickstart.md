---
title: "웹 브라우저에서 서비스 액세스(WCF Data Services 빠른 시작)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49deb2e209127f92a333195e9fcd0d1e1bece7d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="c48e4-102">웹 브라우저에서 서비스 액세스(WCF Data Services 빠른 시작)</span><span class="sxs-lookup"><span data-stu-id="c48e4-102">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>
<span data-ttu-id="c48e4-103">이 작업에서는 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]를 시작하고 웹 브라우저에서 선택적으로 피드 읽기를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-103">In this task, you will start the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] from [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="c48e4-104">또한 서비스 정의 문서를 검색 됩니다 있을 뿐만 아니라 노출 된 리소스를 웹 브라우저를 통해 HTTP GET 요청을 제출 하 여 데이터 서비스 리소스에 액세스 한 다음 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-104">You will then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c48e4-105">기본적으로 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서는 사용자 컴퓨터에서 `localhost` URI에 포트 번호를 자동으로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-105">By default, [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="c48e4-106">이 작업에서는 URI 예제에서 포트 번호 `12345`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-106">This task uses the port number `12345` in the URI examples.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c48e4-107">에 특정 포트 번호를 설정 하 여 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 프로젝트 참조 [데이터 서비스를 만드는](../../../../docs/framework/data/wcf/creating-the-data-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-107"> how to set a specific port number in your [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] project see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
### <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="c48e4-108">Internet Explorer를 사용하여 기본 서비스 문서를 요청하려면</span><span class="sxs-lookup"><span data-stu-id="c48e4-108">To request the default service document by using Internet Explorer</span></span>  
  
1.  <span data-ttu-id="c48e4-109">Internet Explorer에서에서 **도구** 메뉴 선택 **인터넷 옵션**, 클릭는 **콘텐츠** 탭을 클릭 **설정을**, 의선택을취소하고 **피드 읽기용 보기 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-109">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>  
  
     <span data-ttu-id="c48e4-110">이렇게 하면 피드 읽기가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-110">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="c48e4-111">이 기능을 사용하지 않도록 설정하지 않으면 웹 브라우저에서 원시 XML 데이터를 표시하지 않고 반환된 AtomPub 인코딩 문서를 XML 피드로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-111">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c48e4-112">브라우저에서 피드를 원시 XML 데이터로 표시할 수 없는 경우 피드를 페이지의 소스 코드로 볼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-112">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>  
  
2.  <span data-ttu-id="c48e4-113">[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 F5 키를 눌러 응용 프로그램 디버깅을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-113">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], press the F5 key to start debugging the application.</span></span>  
  
3.  <span data-ttu-id="c48e4-114">로컬 컴퓨터에서 웹 브라우저를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-114">Open a Web browser on the local computer.</span></span> <span data-ttu-id="c48e4-115">주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-115">In the address bar, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc  
    ```  
  
     <span data-ttu-id="c48e4-116">이 데이터 서비스에서 노출하는 엔터티 집합 목록을 포함하는 기본 서비스 문서가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-116">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>  
  
### <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="c48e4-117">웹 브라우저에서 엔터티 집합 리소스에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="c48e4-117">To access entity set resources from a Web browser</span></span>  
  
1.  <span data-ttu-id="c48e4-118">웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-118">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers  
    ```  
  
     <span data-ttu-id="c48e4-119">Northwind 샘플 데이터베이스의 모든 고객 집합이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-119">This returns a set of all customers in the Northwind sample database.</span></span>  
  
2.  <span data-ttu-id="c48e4-120">웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-120">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')  
    ```  
  
     <span data-ttu-id="c48e4-121">특정 고객 `ALFKI`의 엔터티 인스턴스가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-121">This returns an entity instance for the specific customer, `ALFKI`.</span></span>  
  
3.  <span data-ttu-id="c48e4-122">웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-122">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders  
    ```  
  
     <span data-ttu-id="c48e4-123">고객과 주문 간의 관계가 이동되어 특정 고객 `ALFKI`에 대한 모든 주문 집합이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-123">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>  
  
4.  <span data-ttu-id="c48e4-124">웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-124">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643  
    ```  
  
     <span data-ttu-id="c48e4-125">제공한 `ALFKI` 값을 기반으로 특정 주문만 반환되도록 특정 고객 `OrderID`에 속하는 주문이 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-125">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c48e4-126">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c48e4-126">Next Steps</span></span>  
 <span data-ttu-id="c48e4-127">웹 브라우저에서 성공적으로 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에 액세스했으며 브라우저가 지정된 리소스로 HTTP GET 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-127">You have successfully accessed the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="c48e4-128">웹 브라우저를 사용하면 간편하게 요청의 주소 지정 구문을 실행해 보고 그 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-128">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="c48e4-129">그러나 프로덕션 데이터 서비스는 대개 이 방법으로 액세스되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-129">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="c48e4-130">응용 프로그램은 일반적으로 응용 프로그램 코드나 스크립트 언어를 통해 데이터 서비스와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-130">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="c48e4-131">다음에는 클라이언트 라이브러리를 사용하여 CLR(공용 언어 런타임) 개체인 것처럼 데이터 서비스 리소스에 액세스하는 클라이언트 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c48e4-131">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>  
  
 [<span data-ttu-id="c48e4-132">.NET Framework 클라이언트 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="c48e4-132">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a><span data-ttu-id="c48e4-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c48e4-133">See Also</span></span>  
 [<span data-ttu-id="c48e4-134">데이터 서비스 리소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="c48e4-134">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
