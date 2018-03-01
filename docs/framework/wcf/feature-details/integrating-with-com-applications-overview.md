---
title: "COM 응용 프로그램과 통합 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5b20ae5329f08e9391fd7b93218c44c3c1978a48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="integrating-with-com-applications-overview"></a><span data-ttu-id="959d9-102">COM 응용 프로그램과 통합 개요</span><span class="sxs-lookup"><span data-stu-id="959d9-102">Integrating with COM Applications Overview</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="959d9-103">은 관리 코드 개발자에게 연결된 응용 프로그램을 만들 수 있는 풍부한 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-103"> provides the managed code developer with a rich environment for creating connected applications.</span></span> <span data-ttu-id="959d9-104">하지만 관리되지 않는 COM 기반 코드에 이미 상당한 투자를 하여 마이그레이션을 원하지 않을 시에는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 모니커를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 웹 서비스를 기존 코드에 바로 통합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-104">However, if you have a substantial investment in unmanaged COM-based code and do not want to migrate, you can still integrate [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web services directly into your existing code by using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker.</span></span> <span data-ttu-id="959d9-105">서비스 모니커는 Office VBA, Visual Basic 6.0 또는 Visual C++ 6.0과 같은 다양한 범위의 COM 기반 개발 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-105">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="959d9-106">서비스 모니커에서는 모든 통신에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 통신 채널을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-106">The service moniker uses a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] communication channel for all communication.</span></span> <span data-ttu-id="959d9-107">이 채널의 보안 및 ID 메커니즘은 표준 COM 및 DCOM 프록시에 사용되는 메커니즘과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-107">The security and identity mechanisms for that channel differ from those used in standard COM and DCOM proxies.</span></span> <span data-ttu-id="959d9-108">또한 서비스 모니커에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 통신 채널을 사용하기 때문에 모든 호출에 대한 기본 시간 제한은 1분입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-108">In addition, because the service moniker uses a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] communication channel the default timeout period is one minute for all calls.</span></span>  
  
 <span data-ttu-id="959d9-109">관리되지 않는 개발자에게 `GetObject` 웹 서비스 호출을 위한 강력한 형식의 COM별 접근 방식을 제공하려면 서비스 모니커를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 함수와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-109">The service moniker is used with the `GetObject` function to provide the unmanaged developer with a strongly-typed, COM-specific approach for calling [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web services.</span></span> <span data-ttu-id="959d9-110">이를 위해서는 사용할 바인딩 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 웹 서비스 계약에 대한 로컬 COM 노출 정의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-110">This requires a local, COM-visible definition of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web service contract and the binding that is to be used.</span></span> <span data-ttu-id="959d9-111">처음 메서드를 호출할 때 COM 프로그래머에 대해 이 채널이 투명하게 생성되지만, 다른 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트와 마찬가지로 서비스 모니커는 서비스에 대한 형식화된 채널을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-111">Like other [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients, the service moniker must construct a typed channel to the service, though this channel construction occurs transparently to the COM programmer on the first method call.</span></span>  
  
 <span data-ttu-id="959d9-112">또한 다른 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트와 공통적으로, 모니커를 사용하면 응용 프로그램에서 서비스와 통신할 주소, 바인딩 및 계약을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-112">In common with other [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients, when using the moniker, applications specify the address, binding and contract to communicate with a service.</span></span> <span data-ttu-id="959d9-113">계약은 다음 방법 중 하나로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-113">The contract can be specified in one of the following ways:</span></span>  
  
-   <span data-ttu-id="959d9-114">형식화된 계약 – 계약이 클라이언트 컴퓨터에 COM 노출 형식으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-114">Typed contract – the contract is registered as a COM visible type on the client machine.</span></span>  
  
-   <span data-ttu-id="959d9-115">WSDL 계약 – 계약이 WSDL 문서 형식으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-115">WSDL contract – the contract is supplied in the form of a WSDL document.</span></span>  
  
-   <span data-ttu-id="959d9-116">MEX 계약 – 계약이 MEX(메타데이터 교환) 끝점에서 런타임에 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-116">MEX contract – the contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>  
  
## <a name="parameters-supported-by-the-service-moniker"></a><span data-ttu-id="959d9-117">서비스 모니커에서 지원하는 매개 변수</span><span class="sxs-lookup"><span data-stu-id="959d9-117">Parameters Supported by the Service Moniker</span></span>  
 <span data-ttu-id="959d9-118">다음 표에서는 서비스 모니커에서 지원하는 매개 변수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-118">The following table shows the parameters that are supported by the service moniker.</span></span>  
  
|<span data-ttu-id="959d9-119">매개 변수</span><span class="sxs-lookup"><span data-stu-id="959d9-119">Parameter</span></span>|<span data-ttu-id="959d9-120">설명</span><span class="sxs-lookup"><span data-stu-id="959d9-120">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="959d9-121">서비스의 URL 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-121">URL location of the service.</span></span>|  
|`binding`|<span data-ttu-id="959d9-122">응용 프로그램 구성의 바인딩 섹션 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-122">Binding section name from the application configuration.</span></span>|  
|`bindingConfiguration`|<span data-ttu-id="959d9-123">명명된 바인딩 섹션 내의 명명된 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-123">Named binding instance from within the named binding section.</span></span>|  
|`contract`|<span data-ttu-id="959d9-124">MEX에서 서비스 계약이나 계약 이름을 나타내는 IID(인터페이스 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-124">Interface identifier (IID) that represents the service contract or the contract name (from MEX).</span></span>|  
|`wsdl`|<span data-ttu-id="959d9-125">계약 정의에 대한 대체 형식을 제공하는 WSDL 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-125">WSDL document that provides an alternative form of contract definition.</span></span>|  
|`spnIdentity`|<span data-ttu-id="959d9-126">서비스와의 통신에 사용되는 SPN(서비스 사용자 이름) ID입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-126">Server principal name (SPN) identity to be used to communicate with the service.</span></span>|  
|`upnIdentity`|<span data-ttu-id="959d9-127">서비스와의 통신에 사용되는 UPN(User Principal Name) ID입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-127">User principal name (UPN) identity to be used to communicate with the service.</span></span>|  
|`dnsIdentity`|<span data-ttu-id="959d9-128">서비스와의 통신에 사용되는 DNS ID입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-128">DNS identity to be used to communicate with the service.</span></span>|  
|`mexAddress`|<span data-ttu-id="959d9-129">서비스의 MEX(메타데이터 교환) 끝점에 대한 URL 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-129">URL location of the Metadata Exchange (MEX) endpoint of the service.</span></span>|  
|`mexBinding`|<span data-ttu-id="959d9-130">MEX 끝점과 연결하기 위한 응용 프로그램 구성의 바인딩 섹션 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-130">Binding section name from the application configuration to connect with the MEX endpoint.</span></span>|  
|`mexBindingConfiguration`|<span data-ttu-id="959d9-131">MEX 끝점과 연결하기 위한 명명된 바인딩 섹션 내의 명명된 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-131">Named binding instance from within the named binding section to connect with the MEX endpoint.</span></span>|  
|`bindingNamespace`|<span data-ttu-id="959d9-132">검색된 MEX의 바인딩 섹션 이름에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-132">Namespace of the binding section name from the retrieved MEX.</span></span>|  
|`contractNamespace`|<span data-ttu-id="959d9-133">검색된 MEX의 계약에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-133">Namespace of the contract from the retrieved MEX.</span></span>|  
|`mexSpnIdentity`|<span data-ttu-id="959d9-134">MEX 끝점과의 통신에 사용되는 SPN(서버 사용자 이름) ID입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-134">Server principal name (SPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexUpnIdentity`|<span data-ttu-id="959d9-135">MEX 끝점과의 통신에 사용되는 UPN(User Principal Name) ID입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-135">User principal name (UPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexDnsIdentity`|<span data-ttu-id="959d9-136">MEX 끝점과의 통신에 사용되는 DNS ID입니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-136">DNS identity to be used to communicate with the MEX endpoint.</span></span>|  
|`serializer`|<span data-ttu-id="959d9-137">"xml" 또는 "datacontract" serializer 사용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-137">Specify the use of either the "xml" or "datacontract" serializer.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="959d9-138">서비스 모니커를 완전한 COM 기반 클라이언트와 함께 사용하더라도 서비스 모니커를 사용하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 지원 .NET Framework 2.0이 클라이언트 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-138">Even when used with entirely COM-based clients, the service moniker requires [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and the supporting .NET Framework 2.0 to be installed on the client computer.</span></span> <span data-ttu-id="959d9-139">또한 서비스 모니커를 사용하는 클라이언트 응용 프로그램에서 올바른 버전의 .NET Framework 런타임을 로드해야 하는 점도 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-139">It is also critical that client applications that use the service moniker load the appropriate version of the .NET Framework runtime.</span></span> <span data-ttu-id="959d9-140">Office 응용 프로그램에서 모니커를 사용할 때 올바른 프레임워크 버전이 로드되도록 하기 위해 구성 파일이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-140">When using the moniker within Office applications, a configuration file may be required to ensure that the correct framework version is loaded.</span></span> <span data-ttu-id="959d9-141">예를 들어 Excel을 사용하는 경우, 다음 텍스트가 Excel.exe 파일과 동일한 디렉터리의 Excel.exe.config라는 파일에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="959d9-141">For example, with Excel, the following text should be placed in a file called Excel.exe.config in the same directory as the Excel.exe file:</span></span>  
>   
>  `<?xml version="1.0" encoding="utf-8"?>`  
>   
>  <span data-ttu-id="959d9-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span><span class="sxs-lookup"><span data-stu-id="959d9-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span></span>  
>   
>  `<startup>`  
>   
>  `<requiredRuntime version="v2.0.50727" />`  
>   
>  `</startup>`  
>   
>  `</configuration>`  
  
## <a name="see-also"></a><span data-ttu-id="959d9-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="959d9-143">See Also</span></span>  
 [<span data-ttu-id="959d9-144">방법: 서비스 모니커 등록 및 구성</span><span class="sxs-lookup"><span data-stu-id="959d9-144">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
