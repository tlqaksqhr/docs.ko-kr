---
title: '방법: 신뢰할 수 있는 세션 내에서 메시지 보안'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4c320d74f7e7966bfa35c824dbe30da768cd1447
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493245"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="14481-102">방법: 신뢰할 수 있는 세션 내에서 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="14481-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="14481-103">이 항목에서는 기본적이지는 않지만 신뢰할 수 있는 세션을 지원하는 시스템 제공 바인딩 중 하나를 사용하여 이러한 세션 내에서 교환된 메시지의 메시지 수준 보안을 사용하도록 설정하는 데 필요한 단계에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="14481-104">구성 파일에 코드를 사용 하 여 명령적으로 또는 선언적으로 안전 하 고 신뢰할 수 있는 세션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="14481-105">이 절차에서는 클라이언트와 서비스 구성 파일을 사용하여 안전하고 신뢰할 수 있는 세션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14481-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="14481-106">이 절차는 다음 세 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="14481-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="14481-107">클라이언트 및 서비스가 신뢰할 수 있는 세션 내에서 메시지를 교환하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="14481-108">신뢰할 수 있는 세션 내에서 메시지 수준 보안이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="14481-109">클라이언트가 서비스에서 인증받는 데 사용해야 하는 클라이언트 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="14481-110">, 끝점 구성 요소를 포함 하는 첫 번째 태스크는 `bindingConfiguration` (이 예제의) 이라는 바인딩 구성을 참조 하는 특성 `MessageSecurity`합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="14481-111">[  **\<바인딩 >** ](../../../../docs/framework/misc/binding.md) 구성 요소에는 다음이 이름을 설정 하 여 신뢰할 수 있는 세션을 사용 하도록 설정 하려면 참조는 `enabled` 특성에는 [  **\<reliableSession >** ](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) 요소의 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-111">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) element to `true`.</span></span> <span data-ttu-id="14481-112">`ordered` 특성을 `true`로 설정하여 신뢰할 수 있는 세션 내에서 순서가 지정된 배달 보증을 사용하는 것이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14481-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="14481-113">이 구성 프로시저의 기반이 되는 예의 원본 사본을 대 한 참조는 [WS 신뢰할 수 있는 세션](../../../../docs/framework/wcf/samples/ws-reliable-session.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="14481-114">두 번째 작업의 필수 항목을 설정 하 여 수행 됩니다는 `mode` 특성에는  **\<보안 >** 에 포함 된 요소는  **\<바인딩 >** 요소는 클라이언트 및 서비스를 `Message`합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="14481-115">세 번째 작업의 필수 항목을 설정 하 여 수행 됩니다는 `clientCredentialType` 특성에는  **\<메시지 >** 에 포함 된 요소는  **\<보안 >** 요소는 클라이언트 및 서비스를 `Certificate`합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="14481-116">신뢰할 수 있는 세션을 갖는 메시지 보안을 사용할 때 첫 번째 실패 시 예외를 throw 하는 대신 시간 초과가 발생할 때까지 인증 되지 않은 클라이언트를 인증 하려고 하는 신뢰할 수 있는 메시징 합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="14481-117">신뢰할 수 있는 세션을 사용 하도록 WSHttpBinding으로 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="14481-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="14481-118">이 절차에 설명 되어 [하는 방법: 교환 메시지 내에서 정도 신뢰할 수 있는 세션](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="14481-119">신뢰할 수 있는 세션을 사용 하도록 WSHttpBinding으로 클라이언트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="14481-120">이 절차에 설명 되어 [하는 방법: 교환 메시지 내에서 정도 신뢰할 수 있는 세션](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="14481-121">구성에서 모드 및 ClientCredentialType을 설정</span><span class="sxs-lookup"><span data-stu-id="14481-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="14481-122">적절 한 바인딩 요소를 추가할는 [  **\<바인딩 >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="14481-122">Add an appropriate binding element to the [**\<bindings>**](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="14481-123">다음 예제에서는 추가 [  **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="14481-123">The following example adds a [**\<wsHttpBinding>**](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="14481-124">추가  **\<바인딩 >** 요소 집합과 해당 `name` 특성을 적절 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="14481-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="14481-125">이 예제에서는 이름을 사용 하 여 `MessageSecurity`합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="14481-126">추가  **\<보안 >** 요소는 `mode` 특성을 `Message`합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="14481-127">내에서  **\<보안 >** 요소를 추가  **\<메시지 >** 요소는 `clientCredentialType` 특성을 `Certificate`합니다.</span><span class="sxs-lookup"><span data-stu-id="14481-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
