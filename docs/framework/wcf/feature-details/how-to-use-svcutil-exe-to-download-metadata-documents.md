---
title: '방법: Svcutil.exe를 사용하여 메타데이터 문서 다운로드'
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: a8872bbf04e688906fb0229e3d8215fb92cdbc3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492400"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a><span data-ttu-id="e6915-102">방법: Svcutil.exe를 사용하여 메타데이터 문서 다운로드</span><span class="sxs-lookup"><span data-stu-id="e6915-102">How to: Use Svcutil.exe to Download Metadata Documents</span></span>
<span data-ttu-id="e6915-103">Svcutil.exe를 사용하면 실행 중인 서비스에서 메타데이터를 다운로드하여 로컬 파일에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-103">You can use Svcutil.exe to download metadata from running services and to save the metadata to local files.</span></span> <span data-ttu-id="e6915-104">HTTP 및 HTTPS URL 체계에 대 한 Svcutil.exe에서 Ws-metadataexchange를 사용 하 여 메타 데이터를 검색 하려고 하 고 [XML 웹 서비스 검색](http://go.microsoft.com/fwlink/?LinkId=94950)합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-104">For HTTP and HTTPS URL schemes, Svcutil.exe attempts to retrieve metadata using WS-MetadataExchange and [XML Web Service Discovery](http://go.microsoft.com/fwlink/?LinkId=94950).</span></span> <span data-ttu-id="e6915-105">기타 URL 스키마의 경우 Svcutil.exe에서 WS-MetadataExchange만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-105">For all other URL schemes, Svcutil.exe uses only WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="e6915-106">기본적으로 Svcutil.exe는 <xref:System.ServiceModel.Description.MetadataExchangeBindings> 클래스에 정의된 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-106">By default, Svcutil.exe uses the bindings defined in the <xref:System.ServiceModel.Description.MetadataExchangeBindings> class.</span></span> <span data-ttu-id="e6915-107">WS-MetadataExchange에 사용되는 바인딩을 구성하려면 `IMetadataExchange` 계약을 사용하고 메타데이터 끝점 주소의 URI(Uniform Resource Identifier) 스키마와 이름이 같은 Svcutil.exe(svcutil.exe.config)의 구성 파일에서 클라이언트 끝점을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-107">To configure the binding used for WS-MetadataExchange, you must define a client endpoint in the configuration file for Svcutil.exe (svcutil.exe.config) that uses the `IMetadataExchange` contract and that has the same name as the Uniform Resource Identifier (URI) scheme of the metadata endpoint address.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e6915-108">각각 같은 이름의 작업을 포함 하는 계약 서로 다른 두 서비스를 노출 하는 서비스에 대 한 메타 데이터를 가져오려는 Svcutil.exe를 실행 하는 경우 Svcutil.exe에 오류가 표시, "를 가져올 수 없습니다에서 메타 데이터..." 예를 들어 라는 서비스 계약을 노출 하는 서비스 있으면 작업이 정의 되어 ICarService Get (Car c)와 동일한 서비스 작업이 Get (Book b) 된 ibookservice 서비스 계약을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-108">When running Svcutil.exe to get metadata for a service that exposes two different service contracts that each contain an operation of the same name, Svcutil.exe displays an error saying, "Cannot obtain Metadata from ...." For example, if you have a service that exposes a service contract called ICarService that has an operation Get(Car c) and the same service exposes a service contract called IBookService that has an operation Get(Book b).</span></span> <span data-ttu-id="e6915-109">이 문제를 해결하려면 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-109">To work around this issue, do one of the following:</span></span>  
>   
>  -   <span data-ttu-id="e6915-110">작업 중 하나의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-110">Rename one of the operations</span></span>  
> -   <span data-ttu-id="e6915-111"><xref:System.ServiceModel.OperationContractAttribute.Name%2A>을 다른 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-111">Set the <xref:System.ServiceModel.OperationContractAttribute.Name%2A> to a different name.</span></span>  
> -   <span data-ttu-id="e6915-112"><xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> 속성을 사용하여 작업 중 하나의 네임스페이스를 다른 네임스페이스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-112">Set one of the operations' namespaces to a different namespace using the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
### <a name="to-download-metadata-using-svcutilexe"></a><span data-ttu-id="e6915-113">Svcutil.exe를 사용하여 메타데이터를 다운로드하려면</span><span class="sxs-lookup"><span data-stu-id="e6915-113">To download metadata using Svcutil.exe</span></span>  
  
1.  <span data-ttu-id="e6915-114">다음 위치에서 Svcutil.exe 도구를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-114">Locate the Svcutil.exe tool at the following location:</span></span>  
  
     <span data-ttu-id="e6915-115">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span><span class="sxs-lookup"><span data-stu-id="e6915-115">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span></span>  
  
2.  <span data-ttu-id="e6915-116">명령 프롬프트에서 다음 형식을 사용하여 이 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-116">At the command prompt, launch the tool using the following format.</span></span>  
  
    ```  
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     <span data-ttu-id="e6915-117">메타데이터를 다운로드하려면 `/t:metadata` 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-117">You must specify the `/t:metadata` option to download metadata.</span></span> <span data-ttu-id="e6915-118">그렇지 않으면 클라이언트 코드와 구성이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-118">Otherwise, client code and configuration are generated.</span></span>  
  
3.  <span data-ttu-id="e6915-119"><`url`> 인수는 메타 데이터를 제공 하는 서비스 끝점 또는 온라인으로 호스팅되는 메타 데이터 문서의 URL을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-119">The <`url`>argument specifies the URL to a service endpoint that provides metadata or to a metadata document hosted online.</span></span> <span data-ttu-id="e6915-120"><`epr`> 인수는 Ws-addressing 포함 된 XML 파일의 경로를 지정 `EndpointAddress` Ws-metadataexchange를 지 원하는 서비스 끝점에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-120">The <`epr`> argument specifies the path to an XML file that contains a WS-Addressing `EndpointAddress` for a service endpoint that supports WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="e6915-121">이 도구를 사용 하 여 메타 데이터 다운로드 하는 방법에 대 한 추가 옵션에 대 한 참조 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-121">For more options about using this tool for metadata download, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6915-122">예제</span><span class="sxs-lookup"><span data-stu-id="e6915-122">Example</span></span>  
 <span data-ttu-id="e6915-123">다음 명령은 실행 중인 서비스에서 메타데이터 문서를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e6915-123">The following command downloads metadata documents from a running service.</span></span>  
  
```  
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6915-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6915-124">See Also</span></span>  
 [<span data-ttu-id="e6915-125">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="e6915-125">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
