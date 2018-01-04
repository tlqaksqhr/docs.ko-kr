---
title: "ServiceHost 및 서비스 모델 계층 확장"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c73af3b9187fa5365d7ea99474ea182d5f5ae86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="extending-servicehost-and-the-service-model-layer"></a><span data-ttu-id="202ba-102">ServiceHost 및 서비스 모델 계층 확장</span><span class="sxs-lookup"><span data-stu-id="202ba-102">Extending ServiceHost and the Service Model Layer</span></span>
<span data-ttu-id="202ba-103">서비스 모델 계층은 기본 채널에서 들어오는 메시지를 끌어와서 응용 프로그램 코드에서 이를 메서드 호출로 변환하여 결과를 다시 호출자에게 보내는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="202ba-103">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span> <span data-ttu-id="202ba-104">서비스 모델 확장은 클라이언트 또는 디스패처 기능, 사용자 지정 동작, 메시지 및 매개 변수 가로채기 그리고 다른 확장명 기능이 포함된 통신 동작 및 기능 또는 실행을 수정하거나 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="202ba-104">Service model extensions modify or implement execution or communication behavior and features involving client or dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="202ba-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="202ba-105">In This Section</span></span>  
 [<span data-ttu-id="202ba-106">클라이언트 확장</span><span class="sxs-lookup"><span data-stu-id="202ba-106">Extending Clients</span></span>](../../../../docs/framework/wcf/extending/extending-clients.md)  
 <span data-ttu-id="202ba-107">사용자 지정 확장을 클라이언트 응용 프로그램에 삽입할 수 있는 클래스뿐 아니라 클라이언트 런타임을 가로채고 수정할 수 있는 인터페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="202ba-107">Describes the interfaces that can intercept and modify the client runtime, as well as the classes into which you can insert your custom extensions in client applications.</span></span> <span data-ttu-id="202ba-108">예를 들어, 사용자 지정 클라이언트 메시지 로깅, 사용자 지정 메시지 serialization 등을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="202ba-108">For example, you can perform custom client message logging, perform custom message serialization, and so on.</span></span>  
  
 [<span data-ttu-id="202ba-109">디스패처 확장</span><span class="sxs-lookup"><span data-stu-id="202ba-109">Extending Dispatchers</span></span>](../../../../docs/framework/wcf/extending/extending-dispatchers.md)  
 <span data-ttu-id="202ba-110">사용자 지정 확장을 서비스 응용 프로그램에 삽입할 수 있는 클래스뿐 아니라 서비스 런타임을 가로채고 수정할 수 있는 인터페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="202ba-110">Describes the interfaces that can intercept and modify the service runtime, as well as the classes into which you can insert your custom extensions in service applications.</span></span> <span data-ttu-id="202ba-111">예를 들어, 사용자 지정 서비스 로깅, 서비스 측 메시지 유효성 검사, 사용자 지정 디스패치 등을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="202ba-111">For example, you can perform custom service logging, service-side message validation, custom dispatching, and so on.</span></span>  
  
 [<span data-ttu-id="202ba-112">확장 가능한 개체</span><span class="sxs-lookup"><span data-stu-id="202ba-112">Extensible Objects</span></span>](../../../../docs/framework/wcf/extending/extensible-objects.md)  
 <span data-ttu-id="202ba-113">5개의 확장 가능한 개체 및 <xref:System.ServiceModel.IExtensibleObject%601> 패턴에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="202ba-113">Describes the five extensible objects and the <xref:System.ServiceModel.IExtensibleObject%601> pattern.</span></span> <span data-ttu-id="202ba-114">새 기능과 함께 기존 런타임 클래스를 확장하거나 새 상태를 개체에 추가하기 위해 확장명 가능한 개체 패턴이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="202ba-114">The extensible object pattern is used to either extend existing runtime classes with new functionality or to add new state to an object.</span></span> <span data-ttu-id="202ba-115">확장명 가능한 개체 중 하나에 연결된 확장은 이 개체에서 액세스할 수 있는 확장명 가능한 일반 개체에 연결된 공유 상태 및 기능에 액세스하는 처리 시에 매우 다른 단계에서 동작을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="202ba-115">Extensions, attached to one of the extensible objects, enable behaviors at very different stages in processing to access shared state and functionality attached to a common extensible object that they can access.</span></span>  
  
 [<span data-ttu-id="202ba-116">동작을 사용하여 런타임 구성 및 확장</span><span class="sxs-lookup"><span data-stu-id="202ba-116">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 <span data-ttu-id="202ba-117">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 런타임에서 설정을 변경하거나 확장을 삽입하려면 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="202ba-117">To change settings on or insert extensions in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime, you use Behaviors.</span></span> <span data-ttu-id="202ba-118">WCF에는 스로틀, 인스턴스 만들기 그리고 서비스 및 작업의 여러 사항을 제어하기 위한 시스템 구현 동작이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="202ba-118">WCF includes system-implemented behaviors for controlling throttling, instancing, and many other aspects of services and operations.</span></span> <span data-ttu-id="202ba-119">이 단원에서는 사용자 지정 동작을 만드는 방법 및 프로그램 방식과 구성 파일을 사용하여 해당 동작을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="202ba-119">This section describes how to create your own custom behaviors and how to make them available for use both programmatically and using configuration files.</span></span>  
  
 [<span data-ttu-id="202ba-120">ServiceHostFactory를 사용하여 호스팅 확장</span><span class="sxs-lookup"><span data-stu-id="202ba-120">Extending Hosting Using ServiceHostFactory</span></span>](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 <span data-ttu-id="202ba-121"><xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>와 <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>를 확장하는 방법 및 <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> 클래스를 사용하여 호스트 환경을 사용자 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="202ba-121">Describes how to extend <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>, and use the <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> classes to customize the host environment.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="202ba-122">참조</span><span class="sxs-lookup"><span data-stu-id="202ba-122">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="202ba-123">관련 단원</span><span class="sxs-lookup"><span data-stu-id="202ba-123">Related Sections</span></span>
