---
title: "방법: ASP.NET 웹 서비스 클라이언트 코드를 Windows Communication Foundation으로 마이그레이션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b93460fd6d331b43b49f10cf78fc8863ca1d8d88
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a><span data-ttu-id="f9c48-102">방법: ASP.NET 웹 서비스 클라이언트 코드를 Windows Communication Foundation으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f9c48-102">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="f9c48-103">다음 절차에서는 ASP.NET 웹 서비스 클라이언트 코드를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 마이그레이션하기 위해 수행해야 하는 전체 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c48-103">The following procedure describes the broad steps that need to be followed to migrate ASP.NET Web Service client code to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="f9c48-104">프로시저</span><span class="sxs-lookup"><span data-stu-id="f9c48-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a><span data-ttu-id="f9c48-105">ASP.NET 웹 서비스 클라이언트 코드를 WCF로 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="f9c48-105">To migrate ASP.NET Web Service client code to WCF</span></span>  
  
1.  <span data-ttu-id="f9c48-106">클라이언트에 대한 종합적인 테스트 집합이 존재하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c48-106">Ensure that a comprehensive set of tests exist for the client.</span></span>  
  
2.  <span data-ttu-id="f9c48-107">Visual Studio 2005를 사용하여 클라이언트 응용 프로그램을 .NET 2.0으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c48-107">Use Visual Studio 2005 to upgrade the client application to .NET 2.0.</span></span> <span data-ttu-id="f9c48-108">테스트 집합을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c48-108">Run the set of tests.</span></span>  
  
3.  <span data-ttu-id="f9c48-109">클라이언트 프로젝트에서 ASP.NET 클라이언트 코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c48-109">Remove ASP.NET client code from the client project.</span></span> <span data-ttu-id="f9c48-110">해당 코드는 WSDL.exe 도구를 사용하여 생성된 모듈에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c48-110">That code is in modules generated using the WSDL.exe tool.</span></span>  
  
4.  <span data-ttu-id="f9c48-111">생성 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 사용 하 여 클라이언트 코드는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c48-111">Generate [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client code using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="f9c48-112">해당 코드를 클라이언트 프로젝트에 추가하고, 구성 출력을 클라이언트의 기존 구성 파일로 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c48-112">Add that code to the client project and merge the configuration output into the client’s existing configuration file.</span></span>  
  
5.  <span data-ttu-id="f9c48-113">응용 프로그램을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c48-113">Compile the application.</span></span> <span data-ttu-id="f9c48-114">이전 ASP.NET 클라이언트 형식에 대한 참조를 새 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 형식에 대한 참조로 교체하여 컴파일 오류를 복구합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c48-114">Repair the compilation errors by replacing references to the former ASP.NET client types with references to the new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client types.</span></span>  
  
6.  <span data-ttu-id="f9c48-115">테스트 집합을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c48-115">Run the set of tests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9c48-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9c48-116">See Also</span></span>  
 [<span data-ttu-id="f9c48-117">방법: Windows Communication Foundation에 ASP.NET 웹 서비스 코드 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f9c48-117">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
