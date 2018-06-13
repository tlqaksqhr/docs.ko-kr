---
title: WCF 검색
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 175f79096d2bbda81a602d38e027d5a6d871fa12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497960"
---
# <a name="wcf-discovery"></a><span data-ttu-id="6dc21-102">WCF 검색</span><span class="sxs-lookup"><span data-stu-id="6dc21-102">WCF Discovery</span></span>
<span data-ttu-id="6dc21-103">Windows Communication Foundation (WCF)는 Ws-discovery 프로토콜을 사용 하는 상호 운용 가능한 방식으로 런타임에 검색 가능 하도록 서비스를 사용 하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dc21-103">Windows Communication Foundation (WCF) provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="6dc21-104">WCF 서비스는 멀티 캐스트 메시지를 사용 하 여 네트워크 또는 검색 프록시 서버에 자신의 가용성을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dc21-104">WCF services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="6dc21-105">클라이언트 응용 프로그램은 네트워크나 검색 프록시 서버를 검색하여 일련의 조건을 만족하는 서비스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6dc21-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="6dc21-106">이 단원의 항목에서는 이 기능의 프로그램 모델에 대한 개요와 자세한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6dc21-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6dc21-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6dc21-107">In This Section</span></span>  
 [<span data-ttu-id="6dc21-108">WCF 검색 개요</span><span class="sxs-lookup"><span data-stu-id="6dc21-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="6dc21-109">WCF에서 제공 하는 Ws-discovery 지원의 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dc21-109">Provides an overview of WS-Discovery support provided by WCF.</span></span>  
  
 [<span data-ttu-id="6dc21-110">WCF 검색 개체 모델</span><span class="sxs-lookup"><span data-stu-id="6dc21-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="6dc21-111">개체 모델의 클래스와 WS-Discovery 지원의 확장성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6dc21-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="6dc21-112">방법: 프로그래밍 방식으로 WCF 서비스 및 클라이언트에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="6dc21-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="6dc21-113">Windows Communication Foundation (WCF) 서비스를 검색 가능 하 게 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6dc21-113">Shows how to make a Windows Communication Foundation (WCF) service discoverable.</span></span>  
  
 [<span data-ttu-id="6dc21-114">검색 프록시 구현</span><span class="sxs-lookup"><span data-stu-id="6dc21-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="6dc21-115">검색 프록시, 검색 프록시에 등록할 검색 가능한 서비스 및 검색 프록시를 사용하여 검색 가능한 서비스를 찾는 클라이언트를 구현하는 데 필요한 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6dc21-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="6dc21-116">검색 버전 관리</span><span class="sxs-lookup"><span data-stu-id="6dc21-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="6dc21-117">일부 새 검색 기능의 프로토타입 구현에 대해 간략하게 설명하고</span><span class="sxs-lookup"><span data-stu-id="6dc21-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="6dc21-118">사용할 검색 버전을 선택하는 방법에 대해서도 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6dc21-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="6dc21-119">구성 파일에서 검색 구성</span><span class="sxs-lookup"><span data-stu-id="6dc21-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="6dc21-120">구성에서 검색을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6dc21-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="6dc21-121">검색 클라이언트 채널 사용</span><span class="sxs-lookup"><span data-stu-id="6dc21-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="6dc21-122">WCF 클라이언트 응용 프로그램을 작성할 때 Discovery 클라이언트 채널을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6dc21-122">Shows how to use a Discovery Client Channel when writing a WCF client application.</span></span>
