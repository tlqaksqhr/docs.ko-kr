---
title: "COM 응용 프로그램과 통합"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0e625beaf20f6445099d8fb15cb175d3d71a860
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="e2a31-102">COM 응용 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="e2a31-102">Integrating with COM Applications</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="e2a31-103"> 서비스 모니커를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 직접 기존 코드에 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2a31-103"> services can be integrated directly into your existing code by using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker.</span></span> <span data-ttu-id="e2a31-104">서비스 모니커는 Office VBA, Visual Basic 6.0 또는 Visual C++ 6.0과 같은 다양한 범위의 COM 기반 개발 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2a31-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2a31-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="e2a31-105">In This Section</span></span>  
 [<span data-ttu-id="e2a31-106">COM 응용 프로그램 개요와 통합</span><span class="sxs-lookup"><span data-stu-id="e2a31-106">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 <span data-ttu-id="e2a31-107">통합 프로세스의 주요 부분에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e2a31-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="e2a31-108">방법: 등록 하 고 서비스 모니커를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2a31-108">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="e2a31-109">COM 응용 프로그램 내에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 모니커를 사용하려면 필요한 특성을 사용하는 형식을 COM에 등록하고 필요한 바인딩 구성을 사용하여 COM 응용 프로그램과 모니커를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e2a31-109">To use the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="e2a31-110">방법: 등록 없이 Windows Communication Foundation 서비스 모니커를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="e2a31-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="e2a31-111">WSDL(웹 서비스 기술 언어) 문서의 형태로 또는 WS-MetadataExchange 끝점에서 계약 정의를 가져오는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2a31-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="e2a31-112">방법: WSDL 계약을 통해 서비스 모니커 사용</span><span class="sxs-lookup"><span data-stu-id="e2a31-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="e2a31-113">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WSDL 모니커를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 샘플을 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2a31-113">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WSDL moniker.</span></span>  
  
 [<span data-ttu-id="e2a31-114">방법: 서비스 모니커를 사용 하 여 메타 데이터 교환 계약</span><span class="sxs-lookup"><span data-stu-id="e2a31-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="e2a31-115">Mex 끝점을 지정하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 모니커를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 샘플을 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2a31-115">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="e2a31-116">방법: 채널 보안 자격 증명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2a31-116">How to: Specify Channel Security Credentials</span></span>](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="e2a31-117">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 모니커는 채널 자격 증명을 지정하는 다양한 대체 방법을 허용하는 `IChannelCredentials` 인터페이스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e2a31-117">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e2a31-118">참조</span><span class="sxs-lookup"><span data-stu-id="e2a31-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="e2a31-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2a31-119">See Also</span></span>  
 [<span data-ttu-id="e2a31-120">COM + 응용 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="e2a31-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
