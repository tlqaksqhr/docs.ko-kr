---
title: "COM+ 응용 프로그램과 통합"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, reusing code
- Windows Communication Foundation, reusing code
- Windows Communication Foundation, COM+ integration
- COM+ [WCF], Windows Communication Foundation integration
- COM+ [WCF]
- WCF, COM+ integration
ms.assetid: 98bf7dc4-d49a-4129-a59b-db7a7ec8c241
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a29b28608c9ca16dd5a2023bd3d9e135618d753
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="ee6b1-102">COM+ 응용 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="ee6b1-102">Integrating with COM+ Applications</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="ee6b1-103">에서는 분산 응용 프로그램을 만들기 위한 다양한 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ee6b1-103"> provides a rich environment for creating distributed applications.</span></span> <span data-ttu-id="ee6b1-104">COM+에서 호스팅되는 구성 요소 기반 응용 프로그램 논리에 상당한 노력을 기울인 경우 기존 논리를 다시 작성하지 않고 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하여 기존 논리를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee6b1-104">If you have a substantial investment in component-based application logic hosted in COM+, you can use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to extend your existing logic rather than having to rewrite it.</span></span> <span data-ttu-id="ee6b1-105">이 단원의 항목에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]와 함께 COM+를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ee6b1-105">The topics within this section describe how to use COM+ with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee6b1-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ee6b1-106">In This Section</span></span>  
 [<span data-ttu-id="ee6b1-107">COM+ 응용 프로그램과 통합 개요</span><span class="sxs-lookup"><span data-stu-id="ee6b1-107">Integrating with COM+ Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)  
 <span data-ttu-id="ee6b1-108">COM+ 구성 요소를 통합하는 시기 및 방법에 대한 개요를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ee6b1-108">Gives an overview of when and how to integrate COM+ components.</span></span>  
  
 [<span data-ttu-id="ee6b1-109">방법: COM+ 서비스 모델 구성 도구 사용</span><span class="sxs-lookup"><span data-stu-id="ee6b1-109">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)  
 <span data-ttu-id="ee6b1-110">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스로 노출된 원하는 응용 프로그램 인터페이스를 구성하기 위해 COM+ 서비스 모델 구성 명령줄 도구(ComSvcConfig.exe)를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ee6b1-110">Explains how to use the COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) to configure the application interfaces that you want exposed as [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span>  
  
 [<span data-ttu-id="ee6b1-111">방법: COM+ 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="ee6b1-111">How to: Configure COM+ Service Settings</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)  
 <span data-ttu-id="ee6b1-112">COM+ 개체를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스로 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ee6b1-112">Explains how to configure a COM+ object as a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 [<span data-ttu-id="ee6b1-113">방법: COM+ 통합 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="ee6b1-113">How to: Deploy a COM+ Integration Application</span></span>](../../../../docs/framework/wcf/feature-details/how-to-deploy-a-com-integration-application.md)  
 <span data-ttu-id="ee6b1-114">COM+ 통합 응용 프로그램을 이동하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ee6b1-114">Explains how to move a COM+ integration application.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ee6b1-115">참조</span><span class="sxs-lookup"><span data-stu-id="ee6b1-115">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="ee6b1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee6b1-116">See Also</span></span>  
 [<span data-ttu-id="ee6b1-117">COM 응용 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="ee6b1-117">Integrating with COM Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications.md)
