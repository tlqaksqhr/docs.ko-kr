---
title: "호스트 잠금 갱신 기간"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8ba94fc-27e0-4d8e-8f85-50a6d2a3cd43
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fd93e2672851cc0111af6610ade70aebab14442d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="host-lock-renewal-period"></a><span data-ttu-id="24386-102">호스트 잠금 갱신 기간</span><span class="sxs-lookup"><span data-stu-id="24386-102">Host Lock Renewal Period</span></span>
<span data-ttu-id="24386-103">**호스트 잠금 갱신 기간** SQL 워크플로 인스턴스 저장소의 속성을 사용 하면 호스트가 워크플로 인스턴스에서 잠금을 갱신 하는 기간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24386-103">The **Host Lock Renewal Period** property of the SQL Workflow Instance Store lets you specify the time period within which the host renews its lock on a workflow instance.</span></span> <span data-ttu-id="24386-104">잠금은 호스트 잠금 갱신 기간 + 30초 동안 유효한 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="24386-104">The lock remains valid for Host Lock Renewal Period + 30 seconds.</span></span> <span data-ttu-id="24386-105">호스트가 이 기간 내에 잠금을 갱신(대여 연장)하지 못하면 잠금이 만료되고 지속성 공급자가 인스턴스 잠금을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="24386-105">If the host fails to renew the lock (in other words, extend the lease) within this time period, the lock expires and the persistence provider unlocks the instance.</span></span> <span data-ttu-id="24386-106">이 속성의 값은 "h:mm: ss" 형태의 TimeSpan 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="24386-106">The value for this property is of type TimeSpan of the form "hh:mm:ss".</span></span> <span data-ttu-id="24386-107">허용 되는 최소값은 "00: 00:01" (1 초)입니다.</span><span class="sxs-lookup"><span data-stu-id="24386-107">The minimum permitted value is "00:00:01" (1 second).</span></span> <span data-ttu-id="24386-108">이 속성의 기본값은 "00: 00:30" (30 초)입니다.</span><span class="sxs-lookup"><span data-stu-id="24386-108">The default value of this property is "00:00:30" (30 seconds).</span></span>  
  
 <span data-ttu-id="24386-109">이 속성은 워크플로 서비스 호스트가 소유한 워크플로 서비스 인스턴스의 잠금을 해제하기 전에 실패하는 시나리오에서 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="24386-109">This property is significant in scenarios where a workflow service host fails before it can unlock a workflow service instance that it owns.</span></span> <span data-ttu-id="24386-110">이 시나리오에서는 동일한 컴퓨터 또는 서버 팜의 다른 컴퓨터에서 실행하는 다른 워크플로 서비스 호스트가 잠금을 설정하고 워크플로 서비스 인스턴스를 메모리에 로드하여 마지막 유지된 상태부터 실행을 다시 시작할 수 있도록 잠금이 만료된 후 지속성 공급자가 지속성 데이터베이스에서 워크플로 서비스 인스턴스에 대한 잠금을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="24386-110">In this scenario, the lock on the workflow service instance in the persistence database is removed by the persistence provider after the lock expires so that another workflow service host running on the same computer or another computer in a server farm can acquire the lock and load the workflow service instance into memory to resume its execution from its last persisted state.</span></span>  
  
 <span data-ttu-id="24386-111">이 속성에 더 높은 값을 설정하면 유지 데이터베이스에서 워크플로 서비스 인스턴스가 장기간 잠기게 되므로 마지막 지속성 지점부터 인스턴스를 복구하는 작업이 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="24386-111">Setting a higher value for this property causes the workflow service instances to be locked in the persistence database for a longer time and therefore delays the recovery of the instance from the last persistence point.</span></span> <span data-ttu-id="24386-112">이 속성에 짧은 기간을 설정하면 워크플로 서비스 호스트의 새 인스턴스가 오류 워크플로 서비스 인스턴스를 빨리 선택하지만 워크플로 서비스 호스트와 SQL Server 데이터베이스의 작업 부하가 증가하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24386-112">Setting a short interval for this property causes the new instance of the workflow service host to pick up the failed workflow service instance quickly, but causes an increase in workload for the workflow service host and the SQL Server database.</span></span>  
  
 <span data-ttu-id="24386-113">SQL 워크플로 인스턴스 저장소는 정기적으로 다시 시작되어 잠금이 만료된 인스턴스를 검색하는 내부 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="24386-113">The SQL Workflow Instance Store runs an internal task that periodically wakes up and detects instances with expired locks on them.</span></span> <span data-ttu-id="24386-114">잠금이 만료된 인스턴스를 찾으면 이 작업은 워크플로 호스트가 이 인스턴스를 선택하고 실행할 수 있도록 RunnableInstances 테이블에 인스턴스를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="24386-114">When it finds instances with expired locks, it places the instances in the RunnableInstances table so that a workflow host can pick up and run these instances.</span></span>
