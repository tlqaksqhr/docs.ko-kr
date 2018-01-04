---
title: "AJAX 통합 및 JSON 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cd5c84250349f4adaaac68a302d771280328a4e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="79d2b-102">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="79d2b-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="79d2b-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 AJAX 클라이언트에 작업을 노출할 수 있도록 ASP.NET AJAX(Asynchronous JavaScript and XML) 및 JSON(JavaScript Object Notation) 데이터 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="79d2b-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to expose operations to AJAX clients.</span></span> <span data-ttu-id="79d2b-104">AJAX 클라이언트는 JavaScript 코드를 실행하고, HTTP 요청을 사용하여 이러한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 액세스하는 웹 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="79d2b-104">AJAX clients are Web pages running JavaScript code and accessing these [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services using HTTP requests.</span></span> <span data-ttu-id="79d2b-105">이 단원의 항목에서는 이러한 지원에 대한 정보와 이러한 지원을 구현하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79d2b-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="79d2b-106">ASP.NET AJAX와의 통합을 ASP.NET 2.0과 함께 참조 [ASP.NET AJAX 개요](http://go.microsoft.com/fwlink/?LinkId=96725)합니다.</span><span class="sxs-lookup"><span data-stu-id="79d2b-106"> ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](http://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79d2b-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="79d2b-107">In This Section</span></span>  
 [<span data-ttu-id="79d2b-108">ASP.NET AJAX용 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="79d2b-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="79d2b-109">AJAX 끝점을 자동으로 구성하는 서비스 호스트를 생성하도록 사용자 지정된 서비스 호스트 팩터리를 사용하거나 구성을 통해 적합한 AJAX 끝점을 추가하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 AJAX 클라이언트에 노출시킬 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79d2b-109">Describes how an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="79d2b-110">ASP.NET을 사용하지 않고 WCF AJAX 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="79d2b-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="79d2b-111">ASP.NET을 사용하지 않고 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79d2b-111">Describes how to create an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="79d2b-112">JSON 및 기타 데이터 전송 형식에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="79d2b-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="79d2b-113">ASP.NET AJAX 서비스와의 메시징에 XML 대신 일반적으로 사용되는 JSON 형식의 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79d2b-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="79d2b-114">방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="79d2b-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="79d2b-115">AJAX 사용 ASP.NET 웹 서비스를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 웹 서비스로 마이그레이션하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79d2b-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79d2b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79d2b-116">See Also</span></span>  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [<span data-ttu-id="79d2b-117">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="79d2b-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
