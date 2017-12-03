---
title: '&lt;bindingExtensions&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 02f29ec698584ebe8b2ca1b5d438ac06ba6503b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltbindingextensionsgt"></a><span data-ttu-id="389f5-102">&lt;bindingExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="389f5-102">&lt;bindingExtensions&gt;</span></span>
<span data-ttu-id="389f5-103">이 섹션은 시스템 또는 응용 프로그램 구성 파일의 사용자 정의 바인딩을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="389f5-103">This section enables the use of a user defined binding from a machine or application configuration file.</span></span> <span data-ttu-id="389f5-104">`add` 키워드를 사용하고 요소의 `type` 특성을 사용자 정의 바인딩으로 설정하고 `name` 특성을 사용자 정의 바인딩의 이름으로 설정하여 사용자 정의 바인딩을 이 컬렉션에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389f5-104">You can add a user defined binding to this collection by using the `add` keyword, and setting the `type` attribute of the element to a user defined binding, as well as the `name` attribute to the name of the user defined binding.</span></span>  
  
 <span data-ttu-id="389f5-105">바인딩 확장을 사용하면 끝점 구성의 일부로 사용할 사용자 정의 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389f5-105">Binding extensions enable the user to create user-defined bindings for use as part an endpoint configuration.</span></span> <span data-ttu-id="389f5-106">프로그래밍에서 바인딩 확장은 추상 클래스 <xref:System.ServiceModel.Channels.Binding>을 구현하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="389f5-106">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.Binding>.</span></span>  
  
 <span data-ttu-id="389f5-107">다음 예제에서는 `add` 요소와 `name` 특성을 사용하여 구성 파일의 `bindingElementExtensions` 섹션에 바인딩 확장을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="389f5-107">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <bindingExtensions>  
           <add name="MyBinding" type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="389f5-108">요소에 구성 기능을 추가하려면 `bindingSection` 요소를 작성하고 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="389f5-108">To add configuration abilities to the element, the user needs to write and register a `bindingSection` element.</span></span> <span data-ttu-id="389f5-109">이에 대한 자세한 내용은 <xref:System.Configuration> 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="389f5-109">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="389f5-110">요소 및 해당 구성 형식이 정의되면 다음 예제와 같이 확장을 끝점의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389f5-110">After the element and its configuration type are defined, the extension can be used as part of an endpoint as shown in the following example.</span></span>  
  
```xml  
<services>  
    <service name="MyService">  
        <endpoint address="myAddress" binding="MyBinding" />  
    </service>  
</services>  
```  
  
## <a name="see-also"></a><span data-ttu-id="389f5-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="389f5-111">See Also</span></span>  
 [<span data-ttu-id="389f5-112">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="389f5-112">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
