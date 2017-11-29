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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4d1e0f367ef167e5bf47d0936e0b3200ca7dbe19
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="instance-completion-action"></a><span data-ttu-id="f04d3-102">인스턴스 완료 동작</span><span class="sxs-lookup"><span data-stu-id="f04d3-102">Instance Completion Action</span></span>
<span data-ttu-id="f04d3-103">**인스턴스 완료 동작** SQL 워크플로 인스턴스 저장소의 속성을 사용 하면 삭제 여부를 데이터와 메타 데이터의 워크플로 인스턴스는 지 속성 데이터베이스에서 인스턴스를 완료 한 후를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04d3-103">The **Instance Completion Action** property of the SQL Workflow Instance Store lets you specify whether the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span> <span data-ttu-id="f04d3-104">이 속성에 대 한 허용 된 값은 **DeleteAll** 및 **DeleteNothing**합니다.</span><span class="sxs-lookup"><span data-stu-id="f04d3-104">The allowed values for this property are **DeleteAll** and **DeleteNothing**.</span></span> <span data-ttu-id="f04d3-105">다음 목록에서는 이러한 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f04d3-105">The following list describes these options:</span></span>  
  
-   <span data-ttu-id="f04d3-106">**DeleteAll (기본값)입니다.**</span><span class="sxs-lookup"><span data-stu-id="f04d3-106">**DeleteAll (default).**</span></span> <span data-ttu-id="f04d3-107">속성의 값을 DeleteAll로 설정하면 인스턴스가 완료된 후 워크플로 인스턴스의 데이터와 메타데이터가 지속성 데이터베이스에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04d3-107">If the value of the property is set to DeleteAll, the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span>  
  
-   <span data-ttu-id="f04d3-108">**DeleteNothing 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f04d3-108">**DeleteNothing.**</span></span> <span data-ttu-id="f04d3-109">속성의 값을 DeleteNothing으로 설정하면 인스턴스가 완료된 후에도 워크플로 인스턴스의 데이터와 메타데이터가 지속성 데이터베이스에 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04d3-109">If the value of the property is set to DeleteNothing, the data and metadata of workflow instances is kept in the persistence database even after the instances are completed.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="f04d3-110">인스턴스가 완료된 후 인스턴스 상태 정보를 유지하면 지속성 데이터베이스의 크기가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04d3-110">Keeping instance state information after the instances are completed causes the persistence database to grow in size.</span></span> <span data-ttu-id="f04d3-111">데이터베이스 크기가 증가할수록 지속성 하위 시스템이 수행하는 데이터베이스 작업이 더 오래 걸리므로, 서비스가 성능 필요에 맞는 수준으로 수행되도록 하려면 정기적으로 지속성 데이터베이스에서 인스턴스 상태 정보를 비워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04d3-111">As the size of the database grows the database operations that the persistence subsystem performs take longer, so you need to purge the instance state information from the persistence database periodically to have services perform at the level that satisfy your performance needs.</span></span>
