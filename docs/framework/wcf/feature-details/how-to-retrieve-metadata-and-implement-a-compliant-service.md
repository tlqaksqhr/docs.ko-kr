---
title: "방법: 메타데이터 검색 및 규격 서비스 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 33090cd855aa41607f6d330d695f24a6f60197d6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-retrieve-metadata-and-implement-a-compliant-service"></a><span data-ttu-id="e912c-102">방법: 메타데이터 검색 및 규격 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="e912c-102">How to: Retrieve Metadata and Implement a Compliant Service</span></span>
<span data-ttu-id="e912c-103">서비스를 디자인하는 사람과 구현하는 사람이 다른 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-103">Often, the same person does not design and implement services.</span></span> <span data-ttu-id="e912c-104">상호 운용하는 응용 프로그램이 중요한 환경에서는 WSDL(웹 서비스 기술 언어)로 계약을 디자인하거나 설명할 수 있으며 개발자는 제공된 계약에 따라 서비스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-104">In environments where interoperating applications are important, contracts can be designed or described in Web Services Description Language (WSDL) and a developer must implement a service that complies with the provided contract.</span></span> <span data-ttu-id="e912c-105">기존 서비스를 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]로 마이그레이션하면서 통신 형식을 유지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-105">You may also want to migrate an existing service to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] but preserve the wire format.</span></span> <span data-ttu-id="e912c-106">또한 이중 계약에서는 호출자가 콜백 계약도 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-106">In addition, duplex contracts require callers to implement a callback contract as well.</span></span>  
  
 <span data-ttu-id="e912c-107">이 경우에 사용 해야 합니다는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) (또는 해당 하는 도구)의 요구 사항을 충족 하기 위해 구현할 수 있는 관리 되는 언어에서 서비스 계약 인터페이스를 생성 하는 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-107">In these cases, you must use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) (or an equivalent tool) to generate a service contract interface in a managed language that you can implement to fulfill the requirements of the contract.</span></span> <span data-ttu-id="e912c-108">일반적으로 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 채널 팩터리와 함께 사용 되는 서비스 계약을 획득 하는 데 사용 되는 또는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 뿐만 아니라를 설정 하는 클라이언트 구성 파일에서와 마찬가지로 클라이언트 유형은 올바른 바인딩 및 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-108">Typically the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) is used to acquire a service contract that is used with a channel factory or a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client type as well as with a client configuration file that sets up the correct binding and address.</span></span> <span data-ttu-id="e912c-109">생성된 구성 파일을 사용하려면 해당 파일을 서비스 구성 파일로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-109">To use the generated configuration file, you must change it into a service configuration file.</span></span> <span data-ttu-id="e912c-110">서비스 계약을 수정해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-110">You may also need to modify the service contract.</span></span>  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a><span data-ttu-id="e912c-111">데이터 검색 및 규격 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="e912c-111">To retrieve data and implement a compliant service</span></span>  
  
1.  <span data-ttu-id="e912c-112">사용 하 여 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 메타 데이터 파일이 나 코드 파일을 생성 하는 메타 데이터 끝점에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-112">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) against metadata files or a metadata endpoint to generate a code file.</span></span>  
  
2.  <span data-ttu-id="e912c-113"><xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> 특성으로 표시된 필요한 인터페이스(두 개 이상 있는 경우)를 포함하는 출력 코드 파일 부분을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-113">Search for the portion of the output code file that contains the interface of interest (in case there is more than one) that is marked with the <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="e912c-114">다음 코드 예제에서 생성 된 두 개의 인터페이스를 보여 줍니다. [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-114">The following code example shows the two interfaces generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="e912c-115">첫 번째(`ISampleService`)는 규격 서비스를 만들기 위해 구현하는 서비스 계약 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-115">The first (`ISampleService`) is the service contract interface that you implement to create a compliant service.</span></span> <span data-ttu-id="e912c-116">두 번째(`ISampleServiceChannel`)는 서비스 계약 인터페이스 및 <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>을 모두 확장하는 클라이언트와 클라이언트 응용 프로그램에 사용하기 위한 도우미 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-116">The second (`ISampleServiceChannel`) is a helper interface for client use that extends both the service contract interface and <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> and is for use in a client application.</span></span>  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3.  <span data-ttu-id="e912c-117">WSDL에서 모든 작업에 대한 회신 동작을 지정하지 않으면 생성되는 작업 계약에서 <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> 속성이 와일드카드 문자(*)로 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-117">If the WSDL does not specify a reply action for all of the operations, the generated operation contracts may have the <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> property set to the wildcard character (*).</span></span> <span data-ttu-id="e912c-118">이 속성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-118">Remove this property setting.</span></span> <span data-ttu-id="e912c-119">그렇지 않으면 서비스 계약 메타데이터를 구현할 때 해당 작업에 대해 메타데이터를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-119">Otherwise, when you implement the service contract metadata, the metadata cannot be exported for those operations.</span></span>  
  
4.  <span data-ttu-id="e912c-120">클래스에서 인터페이스를 구현하고 서비스를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-120">Implement the interface on a class and host the service.</span></span> <span data-ttu-id="e912c-121">예를 들어 참조 [하는 방법: 서비스 계약을 구현](../../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md), 하거나 "예" 섹션의 간단한 구현을 아래를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e912c-121">For an example, see [How to: Implement a Service Contract](../../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md), or see a simple implementation below in the Example section.</span></span>  
  
5.  <span data-ttu-id="e912c-122">클라이언트 구성에서 파일을 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 를 생성, 변경의 [ \<클라이언트 >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) 구성 섹션에는 [ \<서비스 >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-122">In the client configuration file that the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generates, change the [\<client>](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) configuration section to a [\<services>](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) configuration section.</span></span> <span data-ttu-id="e912c-123">생성되는 클라이언트 응용 프로그램 구성 파일의 예제를 보려면 다음 "예제" 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e912c-123">(For an example of a generated client application configuration file, see the following "Example" section.)</span></span>  
  
6.  <span data-ttu-id="e912c-124">내에서 [ \<서비스 >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) 구성 섹션을 만듭니다는 `name` 특성에 [ \<서비스 >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) 서비스에 대 한 구성 섹션 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-124">Within the [\<services>](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) configuration section, create a `name` attribute in the [\<services>](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) configuration section for your service implementation.</span></span>  
  
7.  <span data-ttu-id="e912c-125">서비스 `name` 특성을 서비스 구현을 위한 구성 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-125">Set the service `name` attribute to the configuration name for your service implementation.</span></span>  
  
8.  <span data-ttu-id="e912c-126">구현된 서비스 계약을 사용하는 끝점 구성 요소를 서비스 구성 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-126">Add the endpoint configuration elements that use the implemented service contract to the service configuration section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e912c-127">예제</span><span class="sxs-lookup"><span data-stu-id="e912c-127">Example</span></span>  
 <span data-ttu-id="e912c-128">다음 코드 예제를 실행 하 여 생성 된 코드 파일의 대부분을 보여 줍니다.는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 메타 데이터 파일에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-128">The following code example shows the majority of a code file generated by running the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) against metadata files.</span></span>  
  
 <span data-ttu-id="e912c-129">코드 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e912c-129">The following code shows:</span></span>  
  
-   <span data-ttu-id="e912c-130">계약 요구 사항을 준수하는 서비스 계약 인터페이스(구현된 경우)(`ISampleService`).</span><span class="sxs-lookup"><span data-stu-id="e912c-130">The service contract interface that, when implemented, complies with the contract requirements (`ISampleService`).</span></span>  
  
-   <span data-ttu-id="e912c-131">서비스 계약 인터페이스와 <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>을 모두 확장하는 클라이언트와 클라이언트 응용 프로그램에 사용하기 위한 도우미 인터페이스(`ISampleServiceChannel`)</span><span class="sxs-lookup"><span data-stu-id="e912c-131">The helper interface for client use that extends both the service contract interface and <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> and is for use in a client application (`ISampleServiceChannel`).</span></span>  
  
-   <span data-ttu-id="e912c-132"><xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>를 확장하고 클라이언트 응용 프로그램에 사용하기 위한 도우미 클래스(`SampleServiceClient`)</span><span class="sxs-lookup"><span data-stu-id="e912c-132">The helper class that extends <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> and is for use in a client application (`SampleServiceClient`).</span></span>  
  
-   <span data-ttu-id="e912c-133">서비스에서 생성된 구성 파일</span><span class="sxs-lookup"><span data-stu-id="e912c-133">The configuration file generated from the service.</span></span>  
  
-   <span data-ttu-id="e912c-134">간단한 `ISampleService` 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="e912c-134">A simple `ISampleService` service implementation.</span></span>  
  
-   <span data-ttu-id="e912c-135">클라이언트측 구성 파일을 서비스측 버전으로 변환</span><span class="sxs-lookup"><span data-stu-id="e912c-135">A conversion of the client-side configuration file to a service-side version.</span></span>  
  
 [!code-csharp[ClientProxyCodeSample#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#1)]    
 [!code-xml[ClientProxyCodeSample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/client.exe.config#10)]     
 [!code-csharp[ClientProxyCodeSample#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.cs#5)]    
 [!code-xml[ClientProxyCodeSample#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.exe.config#20)]    
  
## <a name="see-also"></a><span data-ttu-id="e912c-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e912c-136">See Also</span></span>  
 [<span data-ttu-id="e912c-137">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="e912c-137">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
