---
title: "Windows Communication Foundation 채택 예상: 이후의 통합을 용이하게 함"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8f60b2566895acfd7d2b749729fab9c3f5deb20c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a><span data-ttu-id="833d6-102">Windows Communication Foundation 채택 예상: 이후의 통합을 용이하게 함</span><span class="sxs-lookup"><span data-stu-id="833d6-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>
<span data-ttu-id="833d6-103">현재 ASP.NET을 사용하고 있으며 나중에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용할 계획인 경우에 이 항목에서는 새 ASP.NET 웹 서비스를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램과 함께 사용하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="833d6-103">If you use ASP.NET today, and anticipate using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in the future, this topic provides guidance to ensure that new ASP.NET Web services will work well together with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="general-recommendations"></a><span data-ttu-id="833d6-104">일반 권장 사항</span><span class="sxs-lookup"><span data-stu-id="833d6-104">General Recommendations</span></span>  
 <span data-ttu-id="833d6-105">새로운 서비스를 위해 ASP.NET 2.0을 채택하십시오.</span><span class="sxs-lookup"><span data-stu-id="833d6-105">Adopt ASP.NET 2.0 for any new services.</span></span> <span data-ttu-id="833d6-106">이렇게 하면 새 버전의 개선 사항과 향상된 내용에 접근할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="833d6-106">Doing so will provide access to the improvements and enhancements of the new version.</span></span> <span data-ttu-id="833d6-107">그러나 동일한 응용 프로그램에서 ASP.NET 2.0 구성 요소를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구성 요소와 함께 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="833d6-107">However, it will also allow for the possibility of using ASP.NET 2.0 components together with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] components in the same application.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="833d6-108">프로토콜</span><span class="sxs-lookup"><span data-stu-id="833d6-108">Protocols</span></span>  
 <span data-ttu-id="833d6-109">ASP.NET 2.0의 새 기능을 사용하여 WS-I Basic Profile 1.1 준수에 대한 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="833d6-109">Use ASP.NET 2.0’s new facility for validating conformity to the WS-I Basic Profile 1.1:</span></span>  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="833d6-110">WS-I Basic Profile 1.1을 준수하는 ASP.NET 웹 서비스는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 미리 정의된 바인딩인 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]을 사용하여 <xref:System.ServiceModel.BasicHttpBinding> 클라이언트와 상호 운용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="833d6-110">ASP.NET Web services that conform to WS-I Basic Profile 1.1 will be interoperable with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients by using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] predefined binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="833d6-111">서비스 개발</span><span class="sxs-lookup"><span data-stu-id="833d6-111">Service Development</span></span>  
 <span data-ttu-id="833d6-112">SOAPAction HTTP 헤더가 아닌 SOAP 메시지 본문 요소의 정규화된 이름을 기반으로 메서드로 메시지를 라우팅하려면 <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> 특성을 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="833d6-112">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the SOAPAction HTTP header.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="833d6-113">는 라우팅 메시지에 대해 SOAPAction HTTP 헤더를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="833d6-113"> uses the SOAPAction HTTP header for routing messages.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="833d6-114">데이터 표현</span><span class="sxs-lookup"><span data-stu-id="833d6-114">Data Representation</span></span>  
 <span data-ttu-id="833d6-115"><xref:System.Xml.Serialization.XmlSerializer>에서 기본적으로 형식을 serialize하는 XML은 해당 XML에 대한 네임스페이스가 명시적으로 정의되어 있는 경우 <xref:System.Runtime.Serialization.DataContractSerializer>에서 형식을 serialize하는 XML과 의미상 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="833d6-115">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="833d6-116">나중에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 채택하기 위해 ASP.NET 웹 서비스와 함께 사용하도록 데이터 형식을 정의하려면 다음을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="833d6-116">When defining a data type for use with ASP.NET Web services in anticipation of adopting [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in the future, do the following:</span></span>  
  
1.  <span data-ttu-id="833d6-117">XML 스키마가 아닌 .NET Framework 클래스를 사용하여 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="833d6-117">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
2.  <span data-ttu-id="833d6-118">클래스에는 <xref:System.SerializableAttribute> 및 <xref:System.Xml.Serialization.XmlRootAttribute>만 추가하며, 형식에 대한 네임스페이스를 명시적으로 정의하려면 후자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="833d6-118">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="833d6-119">.NET Framework 클래스를 XML로 변환하는 방법을 제어하려면 <xref:System.Xml.Serialization> 네임스페이스로부터 특성을 추가하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="833d6-119">Do no add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
 <span data-ttu-id="833d6-120">이 방법을 채택하면 전송을 위해 클래스가 serialize되도록 XML을 크게 변경하지 않고 나중에 <xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute>를 추가하여 .NET 클래스를 데이터 계약으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="833d6-120">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="833d6-121">ASP.NET 웹 서비스에 의해 메시지에서 사용된 형식은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에 의해 데이터 계약으로 처리될 수 있습니다. 이 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램의 성능 향상을 비롯한 여러 가지 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="833d6-121">The types used in messages by ASP.NET Web services will be able to be processed as data contracts by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications, yielding, amongst other benefits, better performance in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="security"></a><span data-ttu-id="833d6-122">보안</span><span class="sxs-lookup"><span data-stu-id="833d6-122">Security</span></span>  
 <span data-ttu-id="833d6-123">IIS(인터넷 정보 서비스)에서 제공하는 인증 옵션은 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="833d6-123">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="833d6-124"> 클라이언트에서는 이를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="833d6-124"> clients do not support them.</span></span> <span data-ttu-id="833d6-125">서비스 보안이 필요한 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 제공하는 옵션을 사용하십시오. 이러한 옵션은 더 풍부하며 표준 프로토콜을 기반으로 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="833d6-125">If a service needs to be secured, use the options provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], because these options are richer and are based on standard protocols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="833d6-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="833d6-126">See Also</span></span>  
 [<span data-ttu-id="833d6-127">Windows Communication Foundation 채택 예상: 이후의 마이그레이션을 용이 하 게 함</span><span class="sxs-lookup"><span data-stu-id="833d6-127">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
