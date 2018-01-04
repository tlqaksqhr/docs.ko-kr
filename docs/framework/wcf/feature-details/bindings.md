---
title: "Windows Communication Foundation 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], bindings
- Windows Communication Foundation [WCF], bindings
- bindings [WCF]
ms.assetid: 83639133-89f7-43f0-b4ef-8d9e57c08d25
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 977bc032d62856673994e07a71b77d3b668ce7af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="windows-communcation-foundation-bindings"></a><span data-ttu-id="1d4ea-102">Windows Communication Foundation 바인딩</span><span class="sxs-lookup"><span data-stu-id="1d4ea-102">Windows Communcation Foundation Bindings</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="1d4ea-103">는 응용 프로그램 소프트웨어를 작성하는 방법과 그러한 소프트웨어가 다른 소프트웨어와 통신하는 방법을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-103"> separates how the software for an application is written from how it communicates with other software.</span></span> <span data-ttu-id="1d4ea-104">바인딩은 클라이언트와 서비스 간에 통신하는 데 필요한 전송, 인코딩 및 프로토콜 세부 정보를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-104">Bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="1d4ea-105">는 바인딩을 사용하여 끝점의 기본 연결 표시를 생성하므로 통신 당사자들이 대부분의 바인딩 상세 정보에 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-105"> uses bindings to generate the underlying wire representation of the endpoint, so most of the binding details must be agreed upon by the parties that are communicating.</span></span> <span data-ttu-id="1d4ea-106">이를 수행하는 가장 쉬운 방법은 서비스 클라이언트가 서비스 끝점에서 사용하는 동일한 바인딩을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-106">The easiest way to achieve this is for clients of a service to use the same binding that the endpoint for the service uses.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="1d4ea-107">이 작업을 수행 하 [구성 Windows Communication Foundation 서비스 및 클라이언트에 대 한 바인딩을 사용 하 여](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-107"> how to do this, see [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb).</span></span>  
  
 <span data-ttu-id="1d4ea-108">바인딩은 바인딩 요소의 컬렉션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-108">A binding is made up of a collection of binding elements.</span></span> <span data-ttu-id="1d4ea-109">각 요소는 끝점이 클라이언트와 통신하는 방법의 일부를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-109">Each element describes some aspect of how the endpoint communicates with clients.</span></span> <span data-ttu-id="1d4ea-110">바인딩에는 하나 이상의 전송 바인딩 요소, 전송 바인딩 요소가 기본적으로 제공할 수 있는 하나 이상의 메시지 인코딩 바인딩 요소 및 여러 개의 다른 프로토콜 바인딩 요소가 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-110">A binding must include at least one transport binding element, at least one message-encoding binding element (which the transport binding element can provide by default), and any number of other protocol binding elements.</span></span> <span data-ttu-id="1d4ea-111">이 설명에서 런타임을 빌드하는 프로세스를 통해 각 바인딩 요소가 코드를 해당 런타임에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-111">The process that builds a runtime out of this description allows each binding element to contribute code to that runtime.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="1d4ea-112">는 공통적인 바인딩 요소가 선택된 바인딩을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-112"> provides bindings that contain common selections of binding elements.</span></span> <span data-ttu-id="1d4ea-113">이러한 바인딩을 기본 설정에 사용하거나 사용자 요구 사항에 따라 그러한 기본값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-113">These can be used with their default settings or you can modify those default values according to user requirements.</span></span> <span data-ttu-id="1d4ea-114">이러한 시스템 제공 바인딩에 바인딩 요소와 해당 설정을 직접 제어할 수 있는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-114">These system-provided bindings have properties that allow direct control over the binding elements and their settings.</span></span> <span data-ttu-id="1d4ea-115">또한 바인딩의 각 버전에 고유한 이름을 지정하여 여러 버전의 바인딩을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-115">You can also easily work side-by-side with multiple versions of a binding by giving each version of the binding its own name.</span></span> <span data-ttu-id="1d4ea-116">자세한 내용은 참조 [Configuring System-Provided 바인딩](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-116">For details, see [Configuring System-Provided Bindings](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md).</span></span>  
  
 <span data-ttu-id="1d4ea-117">이러한 시스템 제공 바인딩 중 하나에서 제공하지 않는 바인딩 요소의 컬렉션이 필요한 경우 필요한 바인딩 요소의 컬렉션으로 구성된 사용자 지정 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-117">If you need a collection of binding elements not provided by one of these system-provided bindings, you can create a custom binding that consists of the collection of binding elements required.</span></span> <span data-ttu-id="1d4ea-118">이러한 사용자 지정 바인딩은 쉽게 만들 수 있고 새 클래스가 필요하지 않지만 바인딩 요소나 해당 설정을 제어하는 속성을 제공하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-118">These custom bindings are easy to create and do not require a new class, but they do not provide properties for controlling the binding elements or their settings.</span></span> <span data-ttu-id="1d4ea-119">바인딩 요소에 액세스하고 그러한 요소를 포함하는 컬렉션을 통해 해당 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-119">You can access the binding elements and modify their settings through the collection that contains them.</span></span> <span data-ttu-id="1d4ea-120">자세한 내용은 참조 [사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-120">For details, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1d4ea-121">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1d4ea-121">In This Section</span></span>  
 [<span data-ttu-id="1d4ea-122">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="1d4ea-122">Configuring System-Provided Bindings</span></span>](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 <span data-ttu-id="1d4ea-123">일반 시나리오를 지원하기 위해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 제공하는 바인딩을 사용하고 수정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-123">Describes how to use and modify the bindings that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides to support common scenarios.</span></span>  
  
 [<span data-ttu-id="1d4ea-124">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="1d4ea-124">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 <span data-ttu-id="1d4ea-125">코드에서 명령적으로 및 구성을 사용하여 선언적으로 서비스 및 클라이언트에 대한 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 바인딩을 정의하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-125">Describes how to define [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bindings for services and clients imperatively in code and declaratively using configuration.</span></span>  
  
 [<span data-ttu-id="1d4ea-126">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="1d4ea-126">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 <span data-ttu-id="1d4ea-127"><xref:System.ServiceModel.Channels.CustomBinding>의 정의와 언제 사용되는지에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ea-127">Describes what a <xref:System.ServiceModel.Channels.CustomBinding> is and when it is used.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1d4ea-128">참조</span><span class="sxs-lookup"><span data-stu-id="1d4ea-128">Reference</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
  
 <xref:System.ServiceModel.Channels.BindingElement>  
  
 <xref:System.ServiceModel.Channels.CustomBinding>  
  
## <a name="related-sections"></a><span data-ttu-id="1d4ea-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="1d4ea-129">Related Sections</span></span>  
 [<span data-ttu-id="1d4ea-130">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="1d4ea-130">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
