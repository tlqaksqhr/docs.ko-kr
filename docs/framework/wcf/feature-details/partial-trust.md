---
title: "부분 신뢰"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489b1587-9909-4d0e-8c1a-5e83c8f8292b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac76f092d5583519220d2d1b7a8d6d1bbb665632
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="partial-trust"></a><span data-ttu-id="2c4bc-102">부분 신뢰</span><span class="sxs-lookup"><span data-stu-id="2c4bc-102">Partial Trust</span></span>
<span data-ttu-id="2c4bc-103">[!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]부터는 부분적으로 신뢰하는 호출자가 <xref:System.ServiceModel>, <xref:System.Runtime.Serialization> 및 <xref:System.ServiceModel.Web>에서 구현된 public 형식 및 메서드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c4bc-103">Starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)], partially trusted callers can access public types and methods implemented in <xref:System.ServiceModel>, <xref:System.Runtime.Serialization>, and <xref:System.ServiceModel.Web>.</span></span> <span data-ttu-id="2c4bc-104">이 단원에서는 낮은 CAS(코드 액세스 보안) 권한으로 실행되는 응용 프로그램에 사용할 수 있는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 기능의 제한된 하위 집합 및 부분 신뢰 응용 프로그램 내에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 사용을 지원하는 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4bc-104">This section describes supported scenarios for using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] within a partially trusted application as well as the limited subset of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] functionality available to applications running with reduced code access security (CAS) permissions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c4bc-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2c4bc-105">In This Section</span></span>  
 [<span data-ttu-id="2c4bc-106">지원되는 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="2c4bc-106">Supported Deployment Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md)  
 <span data-ttu-id="2c4bc-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 실행할 주요 부분 신뢰 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4bc-107">Describes the main partial trust scenarios for running [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="2c4bc-108">부분 신뢰 기능 호환성</span><span class="sxs-lookup"><span data-stu-id="2c4bc-108">Partial Trust Feature Compatibility</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md)  
 <span data-ttu-id="2c4bc-109">부분 신뢰에 사용할 수 없는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c4bc-109">Describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] features that cannot be used with partial trust.</span></span>  
  
 [<span data-ttu-id="2c4bc-110">부분 신뢰를 위한 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="2c4bc-110">Partial Trust Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md)  
 <span data-ttu-id="2c4bc-111">부분 신뢰 응용 프로그램에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하기 위한 최선의 방법이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c4bc-111">Contains best practices for using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in partially trusted applications.</span></span>
