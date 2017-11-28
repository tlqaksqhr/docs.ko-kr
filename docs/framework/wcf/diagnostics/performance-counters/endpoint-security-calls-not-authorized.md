---
title: "끝점: Security Calls Not Authorized"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d25095ff-9ff0-4c69-a674-4e6a9fe3f4dc
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 59922fad717ea464d8e023c25c8e17a3c17f1846
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-security-calls-not-authorized"></a><span data-ttu-id="b32bb-102">끝점: Security Calls Not Authorized</span><span class="sxs-lookup"><span data-stu-id="b32bb-102">Endpoint: Security Calls Not Authorized</span></span>
<span data-ttu-id="b32bb-103">카운터 이름: Security Calls Not Authorized</span><span class="sxs-lookup"><span data-stu-id="b32bb-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b32bb-104">설명</span><span class="sxs-lookup"><span data-stu-id="b32bb-104">Description</span></span>  
 <span data-ttu-id="b32bb-105">이 카운터는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 메서드가 `false`를 반환할 때 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="b32bb-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="b32bb-106">들어오는 메시지가 올바른 사용자로부터 전송되고 적절하게 보호되지만 해당 사용자에게 특정 작업을 수행할 수 있는 권한이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b32bb-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
