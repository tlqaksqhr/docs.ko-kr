---
title: "여러 IIS 사이트 바인딩 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ebe433d1c18d46e0868f9566a273124e6bd63f1c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="supporting-multiple-iis-site-bindings"></a><span data-ttu-id="c5ee2-102">여러 IIS 사이트 바인딩 지원</span><span class="sxs-lookup"><span data-stu-id="c5ee2-102">Supporting Multiple IIS Site Bindings</span></span>
<span data-ttu-id="c5ee2-103">IIS(인터넷 정보 서비스) 7.0에서 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 호스팅하는 경우 동일한 사이트에 대해 동일한 프로토콜을 사용하는 여러 기본 주소를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-103">When hosting a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service under Internet Information Services (IIS) 7.0, you may want to provide multiple base addresses that use the same protocol on the same site.</span></span> <span data-ttu-id="c5ee2-104">이렇게 하면 동일한 서비스에서 여러 다른 URI에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-104">This allows the same service to respond to a number of different URIs.</span></span> <span data-ttu-id="c5ee2-105">이는 http://www.contoso.com 및 http://contoso.com에서 수신 대기하는 서비스를 호스팅하거나 내부 사용자에 대한 기본 주소와 외부 사용자에 대한 별도의 기본 주소가 있는 서비스를 만들려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-105">This is useful when you want to host a service that listens on http://www.contoso.com and http://contoso.com. It is also useful to create a service that has a base address for internal users and a separate base address for external users.</span></span> <span data-ttu-id="c5ee2-106">유용합니다(예: http://internal.contoso.com 및 http://www.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c5ee2-106">For example: http://internal.contoso.com and http://www.contoso.com.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5ee2-107">이 기능은 HTTP 프로토콜을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-107">This functionality is only available using the HTTP protocol.</span></span>  
  
## <a name="multiple-base-addresses"></a><span data-ttu-id="c5ee2-108">여러 기본 주소</span><span class="sxs-lookup"><span data-stu-id="c5ee2-108">Multiple Base Addresses</span></span>  
 <span data-ttu-id="c5ee2-109">이 기능은 IIS에서 호스팅되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-109">This feature is only available to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services that are hosted under IIS.</span></span> <span data-ttu-id="c5ee2-110">이 기능은 기본적으로 사용하지 않도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-110">This feature is not enabled by default.</span></span> <span data-ttu-id="c5ee2-111">사용 하도록 설정 하려면 추가 해야 합니다는 `multipleSiteBindingsEnabled` 특성을 <`serviceHostingEnvironment`> 요소 Web.config 파일에 파일을로 설정 `true`다음 예제에 나온 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-111">To enable it you must add the `multipleSiteBindingsEnabled` attribute to the <`serviceHostingEnvironment`> element in your Web.config file and set it to `true`, as shown in the following example.</span></span>  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 <span data-ttu-id="c5ee2-112">IIS에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호스팅하는 경우 응용 프로그램이 들어 있는 가상 디렉터리의 URI를 기반으로 하나의 기본 주소가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-112">When hosting a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service under IIS, IIS creates one base address for you based on the URI to the virtual directory that contains the application.</span></span> <span data-ttu-id="c5ee2-113">인터넷 정보 서비스 관리자를 사용하여 웹 사이트에 하나 이상의 바인딩을 추가하여 동일한 프로토콜을 사용하는 기본 주소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-113">You can add additional base addresses that use the same protocol by using Internet Information Services Manager to add one or more bindings to your Web site.</span></span> <span data-ttu-id="c5ee2-114">각 바인딩에 대해 프로토콜(HTTP 또는 HTTPS), IP 주소, 포트 및 호스트 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-114">For each binding specify a protocol (HTTP or HTTPS), an IP address, a port, and a host name.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c5ee2-115">인터넷 정보 서비스 관리자를 사용 하 여 참조 [IIS 관리자 (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164057)합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-115"> using Internet Information Services Manager, see [IIS Manager (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164057).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c5ee2-116">참조 사이트에 바인딩을 추가, [(IIS 7) 웹 사이트 만들기](http://go.microsoft.com/fwlink/?LinkId=164060)</span><span class="sxs-lookup"><span data-stu-id="c5ee2-116"> adding bindings to a site, see [Create a Web Site (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164060)</span></span>  
  
 <span data-ttu-id="c5ee2-117">동일한 사이트에 대해 여러 기본 주소를 지정하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 도움말 페이지의 내용, 스키마 가져오기 및 서비스에서 생성되는 WSDL/MEX 정보에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-117">Specifying multiple base addresses for the same site affects the content of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Help page, importing schema, and the WSDL/MEX information generated by the service.</span></span> <span data-ttu-id="c5ee2-118">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 도움말 페이지에는 서비스와 통신할 수 있는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트를 생성하는 데 사용할 명령줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-118">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Help page displays the command line to use to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that can communicate with the service.</span></span> <span data-ttu-id="c5ee2-119">이 명령줄에는 웹 사이트에 대한 IIS 바인딩에 지정된 첫 번째 주소만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-119">This command line contains only the first address specified in the IIS binding for the Web site.</span></span> <span data-ttu-id="c5ee2-120">마찬가지로 스키마를 가져올 때도 IIS 바인딩에 지정된 첫 번째 기본 주소만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-120">Similarly when importing schema, only the first base address specified in the IIS binding is used.</span></span> <span data-ttu-id="c5ee2-121">WSDL 및 MEX 데이터에는 IIS 바인딩에 지정된 모든 기본 주소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-121">WSDL and MEX data contain all the base addresses specified in the IIS bindings.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c5ee2-122">이는 서비스에 두 개의 기본 주소가 있으면 하나는 내부 사용자용이고 다른 하나는 외부 사용자용이며, 두 주소 모두 서비스에서 생성되는 WSDL/MEX 정보에 지정됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-122">This means that if a service has two base addresses, one for internal users and one for external users, both are specified in the WSDL/MEX information generated by the service.</span></span>
