---
title: '&lt;c o m m&gt;'
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: aaf89f73b6de250aaa572b8fef31e5a1ebd5482b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltcommonbehaviorsgt"></a><span data-ttu-id="c96f2-102">&lt;c o m m&gt;</span><span class="sxs-lookup"><span data-stu-id="c96f2-102">&lt;commonBehaviors&gt;</span></span>
<span data-ttu-id="c96f2-103">`commonBehaviors` 섹션은 machine.config 파일에만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c96f2-103">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="c96f2-104">이 섹션은 두 자식 컬렉션 `endpointBehaviors` 및 `serviceBehaviors`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c96f2-104">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="c96f2-105">각 컬렉션은 컴퓨터의 모든 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 끝점 및 서비스가 사용하는 동작 요소를 각각 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c96f2-105">Each collection defines behavior elements consumed by all [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] endpoints and services on the machine respectively.</span></span> <span data-ttu-id="c96f2-106">`endpointBehaviors`에 정의된 동작은 클라이언트에만 적용되고 `serviceBehaviors`에 정의된 동작은 서비스에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c96f2-106">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="c96f2-107">두 `commonBehaviors` 및 `behaviors` 섹션 모두에서 동작이 정의되는 경우 `behaviors` 섹션의 동작이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="c96f2-107">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
