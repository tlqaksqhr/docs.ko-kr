---
title: COM 응용 프로그램과 통합 개요
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
ms.openlocfilehash: c789d4a52da9b2785fb5919a674bf19f23d23509
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493398"
---
# <a name="integrating-with-com-applications-overview"></a><span data-ttu-id="8c473-102">COM 응용 프로그램과 통합 개요</span><span class="sxs-lookup"><span data-stu-id="8c473-102">Integrating with COM Applications Overview</span></span>
<span data-ttu-id="8c473-103">Windows Communication Foundation (WCF)은 관리 코드 개발자와 연결 된 응용 프로그램을 만들기 위한 풍부한 환경 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-103">Windows Communication Foundation (WCF) provides the managed code developer with a rich environment for creating connected applications.</span></span> <span data-ttu-id="8c473-104">그러나 관리 되지 않는 COM 기반 코드에 이미 상당한 투자 하 고 마이그레이션할 하지 않으려는 경우 통합할 수도 있습니다 WCF 웹 서비스 기존 코드에 직접 WCF 서비스 모니커를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-104">However, if you have a substantial investment in unmanaged COM-based code and do not want to migrate, you can still integrate WCF Web services directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="8c473-105">서비스 모니커는 Office VBA, Visual Basic 6.0 또는 Visual C++ 6.0과 같은 다양한 범위의 COM 기반 개발 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-105">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c473-106">서비스 모니커는 모든 통신에 대 한 WCF 통신 채널을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-106">The service moniker uses a WCF communication channel for all communication.</span></span> <span data-ttu-id="8c473-107">이 채널의 보안 및 ID 메커니즘은 표준 COM 및 DCOM 프록시에 사용되는 메커니즘과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-107">The security and identity mechanisms for that channel differ from those used in standard COM and DCOM proxies.</span></span> <span data-ttu-id="8c473-108">또한 서비스 모니커는 WCF 통신 채널을 기본 제한 시간을 사용 하기 때문에 모든 호출에 대해 1 분입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-108">In addition, because the service moniker uses a WCF communication channel the default timeout period is one minute for all calls.</span></span>  
  
 <span data-ttu-id="8c473-109">서비스 모니커는 서비스와 함께 사용 되는 `GetObject` WCF 웹 서비스 호출 하는 강력한 형식의 COM 별 접근 방식으로 관리 되지 않는 개발자를 제공 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-109">The service moniker is used with the `GetObject` function to provide the unmanaged developer with a strongly-typed, COM-specific approach for calling WCF Web services.</span></span> <span data-ttu-id="8c473-110">로컬, 사용할 바인딩 및 WCF 웹 서비스 계약의 COM 노출 정의가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-110">This requires a local, COM-visible definition of the WCF Web service contract and the binding that is to be used.</span></span> <span data-ttu-id="8c473-111">다른 WCF 클라이언트와 같은 서비스 모니커는 서비스의 첫 번째 메서드 호출 때 COM 프로그래머에 게 투명 하 게이 채널 생성 되지만 서비스에 대 한 형식화 된 채널을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-111">Like other WCF clients, the service moniker must construct a typed channel to the service, though this channel construction occurs transparently to the COM programmer on the first method call.</span></span>  
  
 <span data-ttu-id="8c473-112">다른 WCF 클라이언트, 모니커를 사용 하는 경우, 공통 된 응용 프로그램 주소, 바인딩 및 서비스와 통신 하는 계약을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-112">In common with other WCF clients, when using the moniker, applications specify the address, binding and contract to communicate with a service.</span></span> <span data-ttu-id="8c473-113">계약은 다음 방법 중 하나로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-113">The contract can be specified in one of the following ways:</span></span>  
  
-   <span data-ttu-id="8c473-114">형식화된 계약 – 계약이 클라이언트 컴퓨터에 COM 노출 형식으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-114">Typed contract – the contract is registered as a COM visible type on the client machine.</span></span>  
  
-   <span data-ttu-id="8c473-115">WSDL 계약 – 계약이 WSDL 문서 형식으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-115">WSDL contract – the contract is supplied in the form of a WSDL document.</span></span>  
  
-   <span data-ttu-id="8c473-116">MEX 계약 – 계약이 MEX(메타데이터 교환) 끝점에서 런타임에 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-116">MEX contract – the contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>  
  
## <a name="parameters-supported-by-the-service-moniker"></a><span data-ttu-id="8c473-117">서비스 모니커에서 지원하는 매개 변수</span><span class="sxs-lookup"><span data-stu-id="8c473-117">Parameters Supported by the Service Moniker</span></span>  
 <span data-ttu-id="8c473-118">다음 표에서는 서비스 모니커에서 지원하는 매개 변수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-118">The following table shows the parameters that are supported by the service moniker.</span></span>  
  
|<span data-ttu-id="8c473-119">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8c473-119">Parameter</span></span>|<span data-ttu-id="8c473-120">설명</span><span class="sxs-lookup"><span data-stu-id="8c473-120">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="8c473-121">서비스의 URL 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-121">URL location of the service.</span></span>|  
|`binding`|<span data-ttu-id="8c473-122">응용 프로그램 구성의 바인딩 섹션 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-122">Binding section name from the application configuration.</span></span>|  
|`bindingConfiguration`|<span data-ttu-id="8c473-123">명명된 바인딩 섹션 내의 명명된 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-123">Named binding instance from within the named binding section.</span></span>|  
|`contract`|<span data-ttu-id="8c473-124">MEX에서 서비스 계약이나 계약 이름을 나타내는 IID(인터페이스 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-124">Interface identifier (IID) that represents the service contract or the contract name (from MEX).</span></span>|  
|`wsdl`|<span data-ttu-id="8c473-125">계약 정의에 대한 대체 형식을 제공하는 WSDL 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-125">WSDL document that provides an alternative form of contract definition.</span></span>|  
|`spnIdentity`|<span data-ttu-id="8c473-126">서비스와의 통신에 사용되는 SPN(서비스 사용자 이름) ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-126">Server principal name (SPN) identity to be used to communicate with the service.</span></span>|  
|`upnIdentity`|<span data-ttu-id="8c473-127">서비스와의 통신에 사용되는 UPN(User Principal Name) ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-127">User principal name (UPN) identity to be used to communicate with the service.</span></span>|  
|`dnsIdentity`|<span data-ttu-id="8c473-128">서비스와의 통신에 사용되는 DNS ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-128">DNS identity to be used to communicate with the service.</span></span>|  
|`mexAddress`|<span data-ttu-id="8c473-129">서비스의 MEX(메타데이터 교환) 끝점에 대한 URL 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-129">URL location of the Metadata Exchange (MEX) endpoint of the service.</span></span>|  
|`mexBinding`|<span data-ttu-id="8c473-130">MEX 끝점과 연결하기 위한 응용 프로그램 구성의 바인딩 섹션 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-130">Binding section name from the application configuration to connect with the MEX endpoint.</span></span>|  
|`mexBindingConfiguration`|<span data-ttu-id="8c473-131">MEX 끝점과 연결하기 위한 명명된 바인딩 섹션 내의 명명된 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-131">Named binding instance from within the named binding section to connect with the MEX endpoint.</span></span>|  
|`bindingNamespace`|<span data-ttu-id="8c473-132">검색된 MEX의 바인딩 섹션 이름에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-132">Namespace of the binding section name from the retrieved MEX.</span></span>|  
|`contractNamespace`|<span data-ttu-id="8c473-133">검색된 MEX의 계약에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-133">Namespace of the contract from the retrieved MEX.</span></span>|  
|`mexSpnIdentity`|<span data-ttu-id="8c473-134">MEX 끝점과의 통신에 사용되는 SPN(서버 사용자 이름) ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-134">Server principal name (SPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexUpnIdentity`|<span data-ttu-id="8c473-135">MEX 끝점과의 통신에 사용되는 UPN(User Principal Name) ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-135">User principal name (UPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexDnsIdentity`|<span data-ttu-id="8c473-136">MEX 끝점과의 통신에 사용되는 DNS ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-136">DNS identity to be used to communicate with the MEX endpoint.</span></span>|  
|`serializer`|<span data-ttu-id="8c473-137">"xml" 또는 "datacontract" serializer 사용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-137">Specify the use of either the "xml" or "datacontract" serializer.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="8c473-138">완전히 COM 기반 클라이언트를 사용 하는 경우에 클라이언트 컴퓨터에 설치 되는 WCF 및 지원.NET Framework 2.0 서비스 모니커가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-138">Even when used with entirely COM-based clients, the service moniker requires WCF and the supporting .NET Framework 2.0 to be installed on the client computer.</span></span> <span data-ttu-id="8c473-139">또한 서비스 모니커를 사용하는 클라이언트 응용 프로그램에서 올바른 버전의 .NET Framework 런타임을 로드해야 하는 점도 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-139">It is also critical that client applications that use the service moniker load the appropriate version of the .NET Framework runtime.</span></span> <span data-ttu-id="8c473-140">Office 응용 프로그램에서 모니커를 사용할 때 올바른 프레임워크 버전이 로드되도록 하기 위해 구성 파일이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-140">When using the moniker within Office applications, a configuration file may be required to ensure that the correct framework version is loaded.</span></span> <span data-ttu-id="8c473-141">예를 들어 Excel을 사용하는 경우, 다음 텍스트가 Excel.exe 파일과 동일한 디렉터리의 Excel.exe.config라는 파일에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c473-141">For example, with Excel, the following text should be placed in a file called Excel.exe.config in the same directory as the Excel.exe file:</span></span>  
>   
>  `<?xml version="1.0" encoding="utf-8"?>`  
>   
>  <span data-ttu-id="8c473-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span><span class="sxs-lookup"><span data-stu-id="8c473-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span></span>  
>   
>  `<startup>`  
>   
>  `<requiredRuntime version="v2.0.50727" />`  
>   
>  `</startup>`  
>   
>  `</configuration>`  
  
## <a name="see-also"></a><span data-ttu-id="8c473-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c473-143">See Also</span></span>  
 [<span data-ttu-id="8c473-144">방법: 서비스 모니커 등록 및 구성</span><span class="sxs-lookup"><span data-stu-id="8c473-144">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
