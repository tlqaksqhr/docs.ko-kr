---
title: '&lt;확장&gt;'
ms.date: 03/30/2017
ms.assetid: bcfe5c44-04ef-4a20-96a5-90bfadf39623
ms.openlocfilehash: 9f25c5f99eafe0f87123d8c8c3f5c182220e8c58
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltextensionsgt"></a><span data-ttu-id="6f5c2-102">&lt;확장&gt;</span><span class="sxs-lookup"><span data-stu-id="6f5c2-102">&lt;extensions&gt;</span></span>
<span data-ttu-id="6f5c2-103">이 구성 요소에는 표준 검색 가능 메타데이터(EPR, ContractTypeName, BindingName, Scope 및 ListenURI)와 함께 게시되는 사용자 지정 메타데이터를 포함하는 XML 요소의 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f5c2-103">This configuration element contains a collection of XML elements that contain custom metadata to be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span> <span data-ttu-id="6f5c2-104">다음은 이 구성 요소를 사용하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6f5c2-104">The following is an example of using this configuration element.</span></span>  
  
```xml  
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
     <endpoint binding="basicHttpBinding"  
              address="calculator"  
              contract="ICalculatorService"  
              behaviorConfiguration="calculatorEndpointBehavior" />  
  </service>  
</services>  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDiscovery />  
    </behavior>  
  </serviceBehaviors>  
  <endpointBehaviors>  
    <behavior name="calculatorEndpointBehavior">  
      <endpointDiscovery enable="true">  
        <extensions>  
          <e:Publisher xmlns:e="http://example.org">  
            <e:Name>The Example Organization</e:Name>  
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>  
            <e:Contact>support@example.org</e:Contact>  
          </e:Publisher>  
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>  
        </extensions>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f5c2-105">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f5c2-105">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
