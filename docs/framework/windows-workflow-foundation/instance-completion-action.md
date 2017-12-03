---
title: "인스턴스 완료 동작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 83dec7ef4c911c0bca94caf7cc4c4bf832c8e1b6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="instance-completion-action"></a><span data-ttu-id="2677b-102">인스턴스 완료 동작</span><span class="sxs-lookup"><span data-stu-id="2677b-102">Instance Completion Action</span></span>
<span data-ttu-id="2677b-103">**인스턴스 완료 동작** SQL 워크플로 인스턴스 저장소의 속성을 사용 하면 삭제 여부를 데이터와 메타 데이터의 워크플로 인스턴스는 지 속성 데이터베이스에서 인스턴스를 완료 한 후를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2677b-103">The **Instance Completion Action** property of the SQL Workflow Instance Store lets you specify whether the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span> <span data-ttu-id="2677b-104">이 속성에 대 한 허용 된 값은 **DeleteAll** 및 **DeleteNothing**합니다.</span><span class="sxs-lookup"><span data-stu-id="2677b-104">The allowed values for this property are **DeleteAll** and **DeleteNothing**.</span></span> <span data-ttu-id="2677b-105">다음 목록에서는 이러한 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2677b-105">The following list describes these options:</span></span>  
  
-   <span data-ttu-id="2677b-106">**DeleteAll (기본값)입니다.**</span><span class="sxs-lookup"><span data-stu-id="2677b-106">**DeleteAll (default).**</span></span> <span data-ttu-id="2677b-107">속성의 값을 DeleteAll로 설정하면 인스턴스가 완료된 후 워크플로 인스턴스의 데이터와 메타데이터가 지속성 데이터베이스에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="2677b-107">If the value of the property is set to DeleteAll, the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span>  
  
-   <span data-ttu-id="2677b-108">**DeleteNothing 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2677b-108">**DeleteNothing.**</span></span> <span data-ttu-id="2677b-109">속성의 값을 DeleteNothing으로 설정하면 인스턴스가 완료된 후에도 워크플로 인스턴스의 데이터와 메타데이터가 지속성 데이터베이스에 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="2677b-109">If the value of the property is set to DeleteNothing, the data and metadata of workflow instances is kept in the persistence database even after the instances are completed.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="2677b-110">인스턴스가 완료된 후 인스턴스 상태 정보를 유지하면 지속성 데이터베이스의 크기가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="2677b-110">Keeping instance state information after the instances are completed causes the persistence database to grow in size.</span></span> <span data-ttu-id="2677b-111">데이터베이스 크기가 증가할수록 지속성 하위 시스템이 수행하는 데이터베이스 작업이 더 오래 걸리므로, 서비스가 성능 필요에 맞는 수준으로 수행되도록 하려면 정기적으로 지속성 데이터베이스에서 인스턴스 상태 정보를 비워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2677b-111">As the size of the database grows the database operations that the persistence subsystem performs take longer, so you need to purge the instance state information from the persistence database periodically to have services perform at the level that satisfy your performance needs.</span></span>
