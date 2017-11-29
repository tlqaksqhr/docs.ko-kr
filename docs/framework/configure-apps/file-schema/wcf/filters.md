---
title: "&lt;필터&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37a87222-ec78-4728-8105-9ca1bd961f0c
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 21f2115f83772312e1b9f42a66c53ba8ee2834f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltfiltersgt"></a><span data-ttu-id="f57ce-102">&lt;필터&gt;</span><span class="sxs-lookup"><span data-stu-id="f57ce-102">&lt;filters&gt;</span></span>

<span data-ttu-id="f57ce-103">`filters` 요소는 메시지 로깅 제어에 사용되는 XPath 필터 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="f57ce-103">The `filters` element holds a collection of XPath filters used to control what kind of message is logged.</span></span>

<span data-ttu-id="f57ce-104">필터는 전송 계층에서만 적용됩니다(`logMessagesAtTransportLevel` = `true`).</span><span class="sxs-lookup"><span data-stu-id="f57ce-104">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="f57ce-105">서비스 수준 및 잘못된 형식의 메시지 로깅은 필터의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f57ce-105">Service level and malformed message logging are not affected by filters.</span></span>

<span data-ttu-id="f57ce-106">컬렉션에 필터를 추가하려면 `add` 키워드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f57ce-106">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="f57ce-107">하나 이상의 필터가 정의되면 그 중 최소한 하나의 필터와 일치하는 메시지만 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="f57ce-107">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="f57ce-108">정의된 필터가 없으면 모든 메시지가 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="f57ce-108">If no filter is defined, all messages pass through.</span></span>

<span data-ttu-id="f57ce-109">필터는 모든 XPath 구문을 지원하며, 구성 파일에 표시되는 순서대로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f57ce-109">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="f57ce-110">필터 구문에 오류가 있으면 구성 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f57ce-110">A syntactically incorrect filter results in a configuration exception.</span></span>

<span data-ttu-id="f57ce-111">다음은 SOAP 헤더 섹션이 있는 메시지만 기록하는 필터 구성 방법에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f57ce-111">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>

```xml
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="420">  
  <filters>  
    <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
      /soap:Envelope/soap:Headers  
    </add>  
  </filters>  
</messageLogging>
```

## <a name="see-also"></a><span data-ttu-id="f57ce-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f57ce-112">See also</span></span>

 <span data-ttu-id="f57ce-113"><xref:System.ServiceModel.Configuration.DiagnosticSection><xref:System.ServiceModel.Diagnostics> <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> <xref:System.ServiceModel.Configuration.MessageLoggingElement> <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A> <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection> <xref:System.ServiceModel.Configuration.XPathMessageFilterElement> <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> [메시지 로깅 구성](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) [ \<메시지 로깅 >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)</span><span class="sxs-lookup"><span data-stu-id="f57ce-113"><xref:System.ServiceModel.Configuration.DiagnosticSection> <xref:System.ServiceModel.Diagnostics> <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> <xref:System.ServiceModel.Configuration.MessageLoggingElement> <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A> <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection> <xref:System.ServiceModel.Configuration.XPathMessageFilterElement> <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> [Configuring Message Logging](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) [\<messageLogging>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)</span></span>
