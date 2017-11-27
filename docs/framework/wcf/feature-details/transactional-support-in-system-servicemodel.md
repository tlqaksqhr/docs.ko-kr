---
title: "System.ServiceModel의 트랜잭션 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7e54ed3-d1e5-4aa7-a653-1300c6b304eb
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 172cda7e675a37d49d2e57c8bc93e8c8882df72e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="transactional-support-in-systemservicemodel"></a><span data-ttu-id="7566b-102">System.ServiceModel의 트랜잭션 지원</span><span class="sxs-lookup"><span data-stu-id="7566b-102">Transactional Support in System.ServiceModel</span></span>
<span data-ttu-id="7566b-103">이 단원의 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 제공하는 트랜잭션 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-103">The topics in this section describe the transactional functionalities [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7566b-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="7566b-104">In This Section</span></span>  
 [<span data-ttu-id="7566b-105">ServiceModel 트랜잭션 특성</span><span class="sxs-lookup"><span data-stu-id="7566b-105">ServiceModel Transaction Attributes</span></span>](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)  
 <span data-ttu-id="7566b-106"><xref:System.ServiceModel> 서비스에 대한 트랜잭션의 동작을 구성할 수 있는 두 가지 표준 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-106">Describes the two standard <xref:System.ServiceModel> attributes that enable you to configure the behavior of transactions for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 [<span data-ttu-id="7566b-107">ServiceModel 트랜잭션 구성</span><span class="sxs-lookup"><span data-stu-id="7566b-107">ServiceModel Transaction Configuration</span></span>](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 <span data-ttu-id="7566b-108">서비스에 대한 트랜잭션을 활성화하는 데 사용할 수 있는 다양한 구성 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-108">Describes the various configuration settings that can be used to enable transaction for a service.</span></span>  
  
 [<span data-ttu-id="7566b-109">트랜잭션 흐름 사용</span><span class="sxs-lookup"><span data-stu-id="7566b-109">Enabling Transaction Flow</span></span>](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 <span data-ttu-id="7566b-110">트랜잭션 흐름을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-110">Describes how to enable transaction flow.</span></span>  
  
 [<span data-ttu-id="7566b-111">방법: 트랜잭션 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="7566b-111">How to: Create a Transactional Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-transactional-service.md)  
 <span data-ttu-id="7566b-112">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 트랜잭션 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-112">Demonstrates how to create a transactional service in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="7566b-113">트랜잭션 응용 프로그램 진단</span><span class="sxs-lookup"><span data-stu-id="7566b-113">Diagnosing Transactional Applications</span></span>](../../../../docs/framework/wcf/feature-details/diagnosing-transactional-applications.md)  
 <span data-ttu-id="7566b-114">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 관리 및 진단 기능을 사용하여 트랜잭션 응용 프로그램 문제를 해결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-114">Describes how to use the management and diagnostics feature in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to troubleshoot your transactional application.</span></span>  
  
 [<span data-ttu-id="7566b-115">COM + 및 ServiceModel의 트랜잭션 비교</span><span class="sxs-lookup"><span data-stu-id="7566b-115">Comparing Transactions in COM+ and ServiceModel</span></span>](../../../../docs/framework/wcf/feature-details/comparing-transactions-in-com-and-servicemodel.md)  
 <span data-ttu-id="7566b-116"><xref:System.ServiceModel> 네임스페이스가 제공하는 특성을 사용하여 트랜잭션 COM+ 서비스의 동작을 시뮬레이션하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-116">Describes how to simulate the behavior of a transactional COM+ service using the attributes provided by the <xref:System.ServiceModel> namespace.</span></span>  
  
 [<span data-ttu-id="7566b-117">엔터프라이즈 통합 서비스 트랜잭션 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7566b-117">Integrating Enterprise Services Transactional Components</span></span>](../../../../docs/framework/wcf/feature-details/integrating-enterprise-services-transactional-components.md)  
 <span data-ttu-id="7566b-118">엔터프라이즈 서비스를 사용하는 코드와 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 통합하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-118">Describes how to integrate your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services with code that uses enterprise service.</span></span>
