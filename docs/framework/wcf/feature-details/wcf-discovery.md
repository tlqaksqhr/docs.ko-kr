---
title: "WCF 검색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0c9b083180870e451816b54dddc10068ca7ec5db
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-discovery"></a><span data-ttu-id="f6cee-102">WCF 검색</span><span class="sxs-lookup"><span data-stu-id="f6cee-102">WCF Discovery</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="f6cee-103">는 WS-Discovery 프로토콜을 사용하여 런타임에 상호 운용 가능한 방식으로 서비스를 검색할 수 있도록 하는 지원 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f6cee-103"> provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f6cee-104"> 서비스는 멀티캐스트 메시지를 사용하여 네트워크 또는 검색 프록시 서버에 자신의 사용 가능 여부를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6cee-104"> services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="f6cee-105">클라이언트 응용 프로그램은 네트워크나 검색 프록시 서버를 검색하여 일련의 조건을 만족하는 서비스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f6cee-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="f6cee-106">이 단원의 항목에서는 이 기능의 프로그램 모델에 대한 개요와 자세한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f6cee-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6cee-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="f6cee-107">In This Section</span></span>  
 [<span data-ttu-id="f6cee-108">WCF Discovery 개요</span><span class="sxs-lookup"><span data-stu-id="f6cee-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="f6cee-109">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 제공하는 WS-Discovery 지원에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6cee-109">Provides an overview of WS-Discovery support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="f6cee-110">WCF Discovery 개체 모델</span><span class="sxs-lookup"><span data-stu-id="f6cee-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="f6cee-111">개체 모델의 클래스와 WS-Discovery 지원의 확장성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6cee-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="f6cee-112">방법: 프로그래밍 방식으로 WCF 서비스 및 클라이언트에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="f6cee-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="f6cee-113">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 검색 가능하게 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6cee-113">Shows how to make a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service discoverable.</span></span>  
  
 [<span data-ttu-id="f6cee-114">검색 프록시 구현</span><span class="sxs-lookup"><span data-stu-id="f6cee-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="f6cee-115">검색 프록시, 검색 프록시에 등록할 검색 가능한 서비스 및 검색 프록시를 사용하여 검색 가능한 서비스를 찾는 클라이언트를 구현하는 데 필요한 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6cee-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="f6cee-116">검색 버전 관리</span><span class="sxs-lookup"><span data-stu-id="f6cee-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="f6cee-117">일부 새 검색 기능의 프로토타입 구현에 대해 간략하게 설명하고</span><span class="sxs-lookup"><span data-stu-id="f6cee-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="f6cee-118">사용할 검색 버전을 선택하는 방법에 대해서도 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6cee-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="f6cee-119">구성 파일에서 검색 구성</span><span class="sxs-lookup"><span data-stu-id="f6cee-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="f6cee-120">구성에서 검색을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6cee-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="f6cee-121">Discovery 클라이언트 채널을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="f6cee-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="f6cee-122">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 응용 프로그램을 작성할 때 Discovery 클라이언트 채널을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6cee-122">Shows how to use a Discovery Client Channel when writing a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span>
