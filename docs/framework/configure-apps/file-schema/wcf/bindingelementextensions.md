---
title: '&lt;t e x&gt;'
ms.date: 03/30/2017
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
ms.openlocfilehash: a93474a4f86fac2a6b211652e3ddc86901cf197f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltbindingelementextensionsgt"></a><span data-ttu-id="ecc5e-102">&lt;t e x&gt;</span><span class="sxs-lookup"><span data-stu-id="ecc5e-102">&lt;bindingElementExtensions&gt;</span></span>
<span data-ttu-id="ecc5e-103">이 섹션은 시스템 또는 응용 프로그램 구성 파일의 사용자 지정 요소를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc5e-103">This section enables the use of a custom binding element from a machine or application configuration file.</span></span> <span data-ttu-id="ecc5e-104">`add` 키워드를 사용하고 요소의 `type` 특성을 바인딩 요소 확장으로, `name` 특성을 사용자 지정 바인딩 요소로 설정하여 사용자 지정 바인딩 요소를 이 컬렉션에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc5e-104">You can add a custom binding element to this collection by using the `add` keyword, and setting the `type` attribute of the element to a binding element extension, as well as the `name` attribute to the custom binding element.</span></span>  
  
 <span data-ttu-id="ecc5e-105">바인딩 확장을 사용하면 사용자 지정 바인딩에 사용할 사용자 정의 바인딩 요소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc5e-105">Binding extensions enable the user to create user-defined binding elements for use as part of custom bindings.</span></span> <span data-ttu-id="ecc5e-106">프로그래밍에서 바인딩 확장은 추상 클래스 <xref:System.ServiceModel.Channels.BindingElement>을 구현하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ecc5e-106">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.BindingElement>.</span></span> <span data-ttu-id="ecc5e-107">구성 파일에서 `bindingElementExtensions` 섹션을 사용하여 확장 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc5e-107">In the configuration file, the `bindingElementExtensions` section is used to define an extension element.</span></span>  
  
 <span data-ttu-id="ecc5e-108">다음 예제에서는 `add` 요소와 `name` 특성을 사용하여 구성 파일의 `bindingElementExtensions` 섹션에 바인딩 확장을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc5e-108">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <bindingElementExtensions>  
           <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportSection, UdpTransport,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingElementExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="ecc5e-109">요소에 구성 기능을 추가하려면 `bindingElementExtensionSection` 요소를 작성하고 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc5e-109">To add configuration abilities to the element, the user needs to write and register a `bindingElementExtensionSection` element.</span></span> <span data-ttu-id="ecc5e-110">이에 대한 자세한 내용은 <xref:System.Configuration> 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ecc5e-110">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="ecc5e-111">요소 및 해당 구성 형식이 정의되면 다음 예제와 같이 확장을 사용자 지정 바인딩의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc5e-111">After the element and its configuration type are defined, the extension can be used as part of a custom binding as shown in the following example.</span></span>  
  
```xml  
<customBinding>  
     <binding name="test2">  
         <udpTransport />  
         <binaryMessageEncoding maxReadPoolSize="211" maxWritePoolSize="2132"  
             maxSessionSize="3141" />  
         </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ecc5e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ecc5e-112">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>  
 [<span data-ttu-id="ecc5e-113">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="ecc5e-113">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
