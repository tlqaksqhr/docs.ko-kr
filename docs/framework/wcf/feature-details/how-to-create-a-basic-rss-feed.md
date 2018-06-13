---
title: '방법: 기본 RSS 피드 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 431879b8-a5f8-4947-ad1e-4768c726aca8
ms.openlocfilehash: d5b62d968c38401a19fc9009954450bef210e5a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493284"
---
# <a name="how-to-create-a-basic-rss-feed"></a><span data-ttu-id="cf84e-102">방법: 기본 RSS 피드 만들기</span><span class="sxs-lookup"><span data-stu-id="cf84e-102">How to: Create a Basic RSS Feed</span></span>
<span data-ttu-id="cf84e-103">Windows Communication Foundation (WCF)를 사용 하면 배포 피드를 노출 하는 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-103">Windows Communication Foundation (WCF) allows you to create a service that exposes a syndication feed.</span></span> <span data-ttu-id="cf84e-104">이 항목에서는 RSS 배포 피드를 노출하는 배포 서비스를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-104">This topic discusses how to create a syndication service that exposes an RSS syndication feed.</span></span>  
  
### <a name="to-create-a-basic-syndication-service"></a><span data-ttu-id="cf84e-105">기본 배포 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="cf84e-105">To create a basic syndication service</span></span>  
  
1.  <span data-ttu-id="cf84e-106"><xref:System.ServiceModel.Web.WebGetAttribute> 특성으로 표시된 인터페이스를 사용하여 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-106">Define a service contract using an interface marked with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute.</span></span> <span data-ttu-id="cf84e-107">배포 피드로 노출된 각 작업은 <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> 개체를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-107">Each operation that is exposed as a syndication feed should return a <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> object.</span></span>  
  
     [!code-csharp[htRssBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#0)]
     [!code-vb[htRssBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#0)]  
  
    > [!NOTE]
    >  <span data-ttu-id="cf84e-108"><xref:System.ServiceModel.Web.WebGetAttribute> 특성을 적용하는 모든 서비스 작업은 HTTP GET 요청에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-108">All service operations that apply the <xref:System.ServiceModel.Web.WebGetAttribute> attribute are mapped to HTTP GET requests.</span></span> <span data-ttu-id="cf84e-109">작업을 다른 HTTP 메서드에 매핑하려면 <xref:System.ServiceModel.Web.WebInvokeAttribute>를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-109">To map your operation to a different HTTP method, use the <xref:System.ServiceModel.Web.WebInvokeAttribute> instead.</span></span> <span data-ttu-id="cf84e-110">자세한 내용은 참조 [하는 방법: 기본 WCF 웹 HTTP 서비스 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-110">For more information, see [How to: Create a Basic WCF Web HTTP Service](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md).</span></span>  
  
2.  <span data-ttu-id="cf84e-111">서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-111">Implement the service contract.</span></span>  
  
     [!code-csharp[htRssBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#1)]
     [!code-vb[htRssBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#1)]  
  
3.  <span data-ttu-id="cf84e-112"><xref:System.ServiceModel.Syndication.SyndicationFeed> 개체를 만들고 만든 이, 범주 및 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-112">Create a <xref:System.ServiceModel.Syndication.SyndicationFeed> object and add an author, category, and description.</span></span>  
  
     [!code-csharp[htRssBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#2)]
     [!code-vb[htRssBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#2)]  
  
4.  <span data-ttu-id="cf84e-113">여러 <xref:System.ServiceModel.Syndication.SyndicationItem> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-113">Create several <xref:System.ServiceModel.Syndication.SyndicationItem> objects.</span></span>  
  
     [!code-csharp[htRssBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#3)]
     [!code-vb[htRssBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#3)]  
  
5.  <span data-ttu-id="cf84e-114">피드에 <xref:System.ServiceModel.Syndication.SyndicationItem>을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-114">Add the <xref:System.ServiceModel.Syndication.SyndicationItem> to the feed.</span></span>  
  
     [!code-csharp[htRssBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#4)]
     [!code-vb[htRssBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#4)]  
  
6.  <span data-ttu-id="cf84e-115">피드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-115">Return the feed.</span></span>  
  
     [!code-csharp[htRssBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#5)]
     [!code-vb[htRssBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#5)]  
  
### <a name="to-host-a-service"></a><span data-ttu-id="cf84e-116">서비스를 호스팅하려면</span><span class="sxs-lookup"><span data-stu-id="cf84e-116">To host a service</span></span>  
  
1.  <span data-ttu-id="cf84e-117"><xref:System.ServiceModel.Web.WebServiceHost> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-117">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>  
  
     [!code-csharp[htRssBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#6)]
     [!code-vb[htRssBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#6)]  
  
2.  <span data-ttu-id="cf84e-118">서비스 호스트를 열고 사용자가 Enter 키를 누를 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-118">Open the service host and wait until the user presses ENTER.</span></span>  
  
     [!code-csharp[htRssBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#8)]
     [!code-vb[htRssBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a><span data-ttu-id="cf84e-119">HTTP GET을 사용하여 GetBlog()를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="cf84e-119">To call GetBlog() with an HTTP GET</span></span>  
  
1.  <span data-ttu-id="cf84e-120">Internet Explorer를 열고 다음 URL을 입력 하 고 ENTER 키를 누릅니다: http://localhost:8000/BlogService/GetBlog합니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-120">Open Internet Explorer, type the following URL, and press ENTER: http://localhost:8000/BlogService/GetBlog.</span></span> <span data-ttu-id="cf84e-121">서비스의 기본 주소를 포함 하는 URL (http://localhost:8000/BlogService), 끝점 및 호출할 서비스 작업의 상대 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-121">The URL contains the base address of the service (http://localhost:8000/BlogService), the relative address of the endpoint, and the service operation to call.</span></span>  
  
### <a name="to-call-getblog-from-code"></a><span data-ttu-id="cf84e-122">코드에서 GetBlog()를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="cf84e-122">To call GetBlog() from code</span></span>  
  
1.  <span data-ttu-id="cf84e-123">기본 주소 및 호출할 메서드를 사용하여 <xref:System.Xml.XmlReader>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-123">Create an <xref:System.Xml.XmlReader> with the base address and the method you are calling.</span></span>  
  
     [!code-csharp[htRssBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#9)]
     [!code-vb[htRssBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#9)]  
  
2.  <span data-ttu-id="cf84e-124">지금 만든 <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29>를 전달하는 정적 <xref:System.Xml.XmlReader> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-124">Call the static <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> method, passing in the <xref:System.Xml.XmlReader> you just created.</span></span>  
  
     [!code-csharp[htRssBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#10)]
     [!code-vb[htRssBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#10)]  
  
     <span data-ttu-id="cf84e-125">이렇게 하면 서비스 작업이 호출되고 서비스 작업에서 반환된 포맷터로 새 <xref:System.ServiceModel.Syndication.SyndicationFeed>가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-125">This invokes the service operation and populates a new <xref:System.ServiceModel.Syndication.SyndicationFeed> with the formatter returned from the service operation.</span></span>  
  
3.  <span data-ttu-id="cf84e-126">피드 개체에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-126">Access the feed object.</span></span>  
  
     [!code-csharp[htRssBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#11)]
     [!code-vb[htRssBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="cf84e-127">예제</span><span class="sxs-lookup"><span data-stu-id="cf84e-127">Example</span></span>  
 <span data-ttu-id="cf84e-128">다음은 이 예제에 해당되는 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-128">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htRssBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#12)]
 [!code-vb[htRssBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#12)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cf84e-129">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="cf84e-129">Compiling the Code</span></span>  
 <span data-ttu-id="cf84e-130">앞의 코드를 컴파일할 때 System.ServiceModel.dll 및 System.ServiceModel.Web.dll을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="cf84e-130">When compiling the preceding code, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf84e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf84e-131">See Also</span></span>  
 <xref:System.ServiceModel.WebHttpBinding>  
 <xref:System.ServiceModel.Web.WebGetAttribute>
