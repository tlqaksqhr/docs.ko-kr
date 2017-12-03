---
title: "클라이언트 동작 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c63a91683817311b8d644eb4285101e32eaea7f1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-client-behaviors"></a><span data-ttu-id="dab64-102">클라이언트 동작 구성</span><span class="sxs-lookup"><span data-stu-id="dab64-102">Configuring Client Behaviors</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="dab64-103">에서는 클라이언트 응용 프로그램 구성 파일의 `<behavior>` 섹션에 정의된 동작 구성을 참조하거나 호출 응용 프로그램에서 프로그래밍 방식으로 동작을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-103"> configures behaviors in two ways: either by referring to behavior configurations -- which are defined in the `<behavior>` section of a client application configuration file – or programmatically in the calling application.</span></span> <span data-ttu-id="dab64-104">이 항목에서는 두 접근 방식 모두에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-104">This topic describes both approaches.</span></span>  
  
 <span data-ttu-id="dab64-105">구성 파일을 사용할 경우 동작 구성은 구성 설정의 명명된 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-105">When using a configuration file, behavior configuration is a named collection of configuration settings.</span></span> <span data-ttu-id="dab64-106">각 동작 구성의 이름은 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-106">The name of each behavior configuration must be unique.</span></span> <span data-ttu-id="dab64-107">이 문자열은 끝점을 동작에 연결하는 끝점 구성의 `behaviorConfiguration` 특성에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-107">This string is used in the `behaviorConfiguration` attribute of an endpoint configuration to link the endpoint to the behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dab64-108">예제</span><span class="sxs-lookup"><span data-stu-id="dab64-108">Example</span></span>  
 <span data-ttu-id="dab64-109">다음 구성 코드에서는 `myBehavior`라는 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-109">The following configuration code defines a behavior called `myBehavior`.</span></span> <span data-ttu-id="dab64-110">클라이언트 끝점은 `behaviorConfiguration` 특성에서 이 동작을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-110">The client endpoint references this behavior in the `behaviorConfiguration` attribute.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="myBehavior">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <bindings>  
            <basicHttpBinding>  
                <binding name="myBinding" maxReceivedMessageSize="10000" />  
            </basicHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="myAddress" binding="basicHttpBinding" bindingConfiguration="myBinding" behaviorConfiguration="myBehavior" contract="myContract" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-behaviors-programmatically"></a><span data-ttu-id="dab64-111">프로그래밍 방식으로 동작 사용</span><span class="sxs-lookup"><span data-stu-id="dab64-111">Using Behaviors Programmatically</span></span>  
 <span data-ttu-id="dab64-112">클라이언트를 열기 전에 `Behaviors` 클라이언트 개체 또는 클라이언트 채널 팩터리 개체에서 적절한 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 속성을 찾아 프로그래밍 방식으로 동작을 구성 또는 삽입할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-112">You can also configure or insert behaviors programmatically by locating the appropriate `Behaviors` property on the [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] client object or on the client channel factory object prior to opening the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dab64-113">예제</span><span class="sxs-lookup"><span data-stu-id="dab64-113">Example</span></span>  
 <span data-ttu-id="dab64-114">다음 코드 예제에서는 채널 개체를 만들기 전에 <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> 속성에서 반환된 <xref:System.ServiceModel.Description.ServiceEndpoint>의 <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> 속성에 액세스하여 프로그래밍 방식으로 동작을 삽입하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-114">The following code example shows how to programmatically insert a behavior by accessing the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property on the <xref:System.ServiceModel.Description.ServiceEndpoint> returned from the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property prior to the creation of the channel object.</span></span>  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="dab64-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dab64-115">See Also</span></span>  
 [<span data-ttu-id="dab64-116">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="dab64-116">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
