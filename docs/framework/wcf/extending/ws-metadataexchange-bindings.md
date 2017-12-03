---
title: "WS-MetadataExchange 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a7267fa8e71a7bbe202bce9897ea09079307be50
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="470a2-102">WS-MetadataExchange 바인딩</span><span class="sxs-lookup"><span data-stu-id="470a2-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="470a2-103">이 항목에서는 여러 가지 전송에 대해 기본 메타데이터 교환 바인딩을 생성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="470a2-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="470a2-104">기본 바인딩</span><span class="sxs-lookup"><span data-stu-id="470a2-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="470a2-105">기본 바인딩 이름</span><span class="sxs-lookup"><span data-stu-id="470a2-105">Default Binding Name</span></span>|<span data-ttu-id="470a2-106">바인딩 생성 방법</span><span class="sxs-lookup"><span data-stu-id="470a2-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="470a2-107">MexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="470a2-107">MexHttpBinding</span></span>|<span data-ttu-id="470a2-108">전송 수준 보안이 비활성화된 <xref:System.ServiceModel.WSHttpBinding>입니다.</span><span class="sxs-lookup"><span data-stu-id="470a2-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="470a2-109">MexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="470a2-109">MexHttpsBinding</span></span>|<span data-ttu-id="470a2-110">전송 수준 보안을 지원하는 <xref:System.ServiceModel.WSHttpBinding>입니다.</span><span class="sxs-lookup"><span data-stu-id="470a2-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="470a2-111">MexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="470a2-111">MexNamedPipeBinding</span></span>|<span data-ttu-id="470a2-112">기본값을 사용하는 <xref:System.ServiceModel.Channels.CustomBinding>가 있는 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>입니다.</span><span class="sxs-lookup"><span data-stu-id="470a2-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="470a2-113">MexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="470a2-113">MexTcpBinding</span></span>|<span data-ttu-id="470a2-114">기본값을 사용하는 <xref:System.ServiceModel.Channels.CustomBinding>가 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>입니다.</span><span class="sxs-lookup"><span data-stu-id="470a2-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
