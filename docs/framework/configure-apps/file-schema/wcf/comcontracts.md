---
title: '&lt;comContracts&gt;'
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: b44c09e7e32129ba21834f7fbb8dc4699904e46b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746412"
---
# <a name="ltcomcontractsgt"></a><span data-ttu-id="3c8b2-102">&lt;comContracts&gt;</span><span class="sxs-lookup"><span data-stu-id="3c8b2-102">&lt;comContracts&gt;</span></span>
<span data-ttu-id="3c8b2-103">`comContracts` 구성 섹션에는 COM+ 통합 서비스 계약의 다양한 속성을 지정할 수 있게 해 주는 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b2-103">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="3c8b2-104">네임스페이스 및 계약 지정</span><span class="sxs-lookup"><span data-stu-id="3c8b2-104">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="3c8b2-105">COM + 통합 서비스 계약은 현재 제한 되며는 "http://tempuri.org" 네임 스페이스, 계약 이름은 지원 COM 인터페이스에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b2-105">COM+ integration service contracts are currently restricted to the "http://tempuri.org" namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="3c8b2-106">그러나 구성 파일에서 `comContracts` 섹션을 사용하여 대안을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b2-106">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="3c8b2-107">예를 들어 다음 구성을 사용하여 서비스 계약의 네임스페이스 및 계약 이름과 세션 바인딩에 사용법을 적용할 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b2-107">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
  </comContract>  
</comContracts>  
```  
  
 <span data-ttu-id="3c8b2-108">지정된 네임스페이스와 계약 이름은 서비스가 초기화될 때 생성된 서비스 설명에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b2-108">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="3c8b2-109">이 섹션이 비어 있으면 서비스 초기화에서는 지원 COM 인터페이스 ID에서 가져온 기본 네임스페이스 및 계약 이름을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b2-109">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="3c8b2-110">또한 사용할 수 있습니다는 [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) COM + 구성 요소의 인터페이스가 웹 서비스로 노출 될 때 노출 되는 COM + 메서드를 지정 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b2-110">In addition, you can use the [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="3c8b2-111">사용할 수도 있습니다는 [ \<persistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) 통합에 사용 되는 지속 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b2-111">You can also use the [\<persistableTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="3c8b2-112">마지막으로 사용할 수 있습니다는 [ \<userDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) 요소 형식을 UDT (사용자 정의)를 서비스 계약에 포함 하는 포함 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b2-112">Finally, you can use the [\<userDefinedType>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c8b2-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c8b2-113">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="3c8b2-114">\<exposedMethod></span><span class="sxs-lookup"><span data-stu-id="3c8b2-114">\<exposedMethod></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)  
 [<span data-ttu-id="3c8b2-115">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="3c8b2-115">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)  
 [<span data-ttu-id="3c8b2-116">\<userDefinedType></span><span class="sxs-lookup"><span data-stu-id="3c8b2-116">\<userDefinedType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)  
 [<span data-ttu-id="3c8b2-117">\<comContract></span><span class="sxs-lookup"><span data-stu-id="3c8b2-117">\<comContract></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)  
 [<span data-ttu-id="3c8b2-118">COM+ 응용 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="3c8b2-118">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="3c8b2-119">방법: COM+ 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="3c8b2-119">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
