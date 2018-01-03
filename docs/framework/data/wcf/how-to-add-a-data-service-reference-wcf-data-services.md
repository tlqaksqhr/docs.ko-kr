---
title: "방법: 데이터 서비스 참조 추가(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fa20e9ed0cefbe587bba90ad25d5460592e3ecf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="e74d5-102">방법: 데이터 서비스 참조 추가(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="e74d5-102">How to: Add a Data Service Reference (WCF Data Services)</span></span>
<span data-ttu-id="e74d5-103">사용할 수는 **서비스 참조 추가** 대화에 대 한 참조를 추가 하려면 Visual Studio에서 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="e74d5-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span> <span data-ttu-id="e74d5-104">이렇게 하면 Visual Studio에서 개발하는 클라이언트 응용 프로그램에서 데이터 서비스에 보다 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e74d5-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="e74d5-105">이 절차를 완료하면 데이터 서비스에서 가져온 메타데이터를 기준으로 데이터 클래스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e74d5-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="e74d5-106">자세한 내용은 참조 [데이터 서비스 클라이언트 라이브러리 생성](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e74d5-106">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span>  
  
### <a name="to-add-a-data-service-reference"></a><span data-ttu-id="e74d5-107">데이터 서비스 참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="e74d5-107">To add a data service reference</span></span>  
  
1.  <span data-ttu-id="e74d5-108">(선택 사항) 데이터 서비스가 솔루션에 포함되어 있지 않고 실행 중이 아닌 경우 데이터 서비스를 시작하고 데이터 서비스의 URI를 적어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="e74d5-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>  
  
2.  <span data-ttu-id="e74d5-109">클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 선택 **서비스 참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="e74d5-109">Right-click the client project and then select **Add Service Reference**.</span></span>  
  
3.  <span data-ttu-id="e74d5-110">클릭 하 여 데이터 서비스는 현재 솔루션의 일부 이면 **Discover**합니다.</span><span class="sxs-lookup"><span data-stu-id="e74d5-110">If the data service is part of the current solution, click **Discover**.</span></span>  
  
     <span data-ttu-id="e74d5-111">또는</span><span class="sxs-lookup"><span data-stu-id="e74d5-111">-or-</span></span>  
  
     <span data-ttu-id="e74d5-112">에 **주소** 텍스트 상자에 입력 데이터 서비스의 기준 URL과 같은 `http://localhost:1234/Northwind.svc`, 클릭 하 고 **이동**합니다.</span><span class="sxs-lookup"><span data-stu-id="e74d5-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>  
  
4.  <span data-ttu-id="e74d5-113">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e74d5-113">Click **OK**.</span></span>  
  
     <span data-ttu-id="e74d5-114">데이터 서비스 리소스에 개체로 액세스하고 상호 작용하는 데 사용되는 데이터 클래스가 포함된 새 코드 파일이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e74d5-114">This adds a new code file that contains the data classes that are used to access and interact with data service resources as objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e74d5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e74d5-115">See Also</span></span>  
 [<span data-ttu-id="e74d5-116">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="e74d5-116">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
