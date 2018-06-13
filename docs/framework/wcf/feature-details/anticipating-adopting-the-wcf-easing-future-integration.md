---
title: 'Windows Communication Foundation 채택 예상: 이후의 통합을 용이하게 함'
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: f81e158a5e7f897307c0c6d376dfe01dac127ead
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489598"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a><span data-ttu-id="b0910-102">Windows Communication Foundation 채택 예상: 이후의 통합을 용이하게 함</span><span class="sxs-lookup"><span data-stu-id="b0910-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>
<span data-ttu-id="b0910-103">현재 ASP.NET을 사용 하 고 나중에 WCF를 사용할 계획인 경우이 항목에서는 WCF 응용 프로그램도 함께 새 ASP.NET 웹 서비스는 사용할 수 있도록 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-103">If you use ASP.NET today, and anticipate using WCF in the future, this topic provides guidance to ensure that new ASP.NET Web services will work well together with WCF applications.</span></span>  
  
## <a name="general-recommendations"></a><span data-ttu-id="b0910-104">일반 권장 사항</span><span class="sxs-lookup"><span data-stu-id="b0910-104">General Recommendations</span></span>  
 <span data-ttu-id="b0910-105">새로운 서비스를 위해 ASP.NET 2.0을 채택하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0910-105">Adopt ASP.NET 2.0 for any new services.</span></span> <span data-ttu-id="b0910-106">이렇게 하면 새 버전의 개선 사항과 향상된 내용에 접근할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-106">Doing so will provide access to the improvements and enhancements of the new version.</span></span> <span data-ttu-id="b0910-107">그러나 WCF 구성 요소와 함께 ASP.NET 2.0 구성 요소를 사용 하 여 동일한 응용 프로그램의 가능성을도 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-107">However, it will also allow for the possibility of using ASP.NET 2.0 components together with WCF components in the same application.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="b0910-108">프로토콜</span><span class="sxs-lookup"><span data-stu-id="b0910-108">Protocols</span></span>  
 <span data-ttu-id="b0910-109">ASP.NET 2.0의 새 기능을 사용하여 WS-I Basic Profile 1.1 준수에 대한 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-109">Use ASP.NET 2.0’s new facility for validating conformity to the WS-I Basic Profile 1.1:</span></span>  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="b0910-110">Ws 준수는 ASP.NET 웹 서비스-Basic Profile 1.1 상호 운용 가능 합니다 WCF 클라이언트와 WCF 미리 정의 된 바인딩을 사용 하 여 <xref:System.ServiceModel.BasicHttpBinding>합니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-110">ASP.NET Web services that conform to WS-I Basic Profile 1.1 will be interoperable with WCF clients by using WCF predefined binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="b0910-111">서비스 개발</span><span class="sxs-lookup"><span data-stu-id="b0910-111">Service Development</span></span>  
 <span data-ttu-id="b0910-112">SOAPAction HTTP 헤더가 아닌 SOAP 메시지 본문 요소의 정규화된 이름을 기반으로 메서드로 메시지를 라우팅하려면 <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> 특성을 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b0910-112">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the SOAPAction HTTP header.</span></span> <span data-ttu-id="b0910-113">WCF 라우팅 메시지에 대해 SOAPAction HTTP 헤더를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-113">WCF uses the SOAPAction HTTP header for routing messages.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="b0910-114">데이터 표현</span><span class="sxs-lookup"><span data-stu-id="b0910-114">Data Representation</span></span>  
 <span data-ttu-id="b0910-115"><xref:System.Xml.Serialization.XmlSerializer>에서 기본적으로 형식을 serialize하는 XML은 해당 XML에 대한 네임스페이스가 명시적으로 정의되어 있는 경우 <xref:System.Runtime.Serialization.DataContractSerializer>에서 형식을 serialize하는 XML과 의미상 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-115">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="b0910-116">나중에 위해 도입 WCF의 ASP.NET 웹 서비스와 함께 사용 하기 위해 데이터 형식을 정의 하는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-116">When defining a data type for use with ASP.NET Web services in anticipation of adopting WCF in the future, do the following:</span></span>  
  
1.  <span data-ttu-id="b0910-117">XML 스키마가 아닌 .NET Framework 클래스를 사용하여 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-117">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
2.  <span data-ttu-id="b0910-118">클래스에는 <xref:System.SerializableAttribute> 및 <xref:System.Xml.Serialization.XmlRootAttribute>만 추가하며, 형식에 대한 네임스페이스를 명시적으로 정의하려면 후자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-118">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="b0910-119">.NET Framework 클래스를 XML로 변환하는 방법을 제어하려면 <xref:System.Xml.Serialization> 네임스페이스로부터 특성을 추가하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b0910-119">Do no add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
 <span data-ttu-id="b0910-120">이 방법을 채택하면 전송을 위해 클래스가 serialize되도록 XML을 크게 변경하지 않고 나중에 <xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute>를 추가하여 .NET 클래스를 데이터 계약으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-120">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="b0910-121">WCF 응용 프로그램에 더 나은 성능 이점도 비롯 한 ASP.NET 웹 서비스에서 메시지에 사용 되는 형식 WCF 응용 프로그램에서 데이터 계약으로 처리 되어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-121">The types used in messages by ASP.NET Web services will be able to be processed as data contracts by WCF applications, yielding, amongst other benefits, better performance in WCF applications.</span></span>  
  
## <a name="security"></a><span data-ttu-id="b0910-122">보안</span><span class="sxs-lookup"><span data-stu-id="b0910-122">Security</span></span>  
 <span data-ttu-id="b0910-123">IIS(인터넷 정보 서비스)에서 제공하는 인증 옵션은 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b0910-123">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="b0910-124">WCF 클라이언트를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-124">WCF clients do not support them.</span></span> <span data-ttu-id="b0910-125">서비스를 보호 하는 경우 이러한 옵션은 더 풍부 하며 표준 프로토콜을 기반으로 하기 때문에, WCF에서 제공 하는 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0910-125">If a service needs to be secured, use the options provided by WCF, because these options are richer and are based on standard protocols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0910-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0910-126">See Also</span></span>  
 [<span data-ttu-id="b0910-127">Windows Communication Foundation 채택 예상: 이후의 마이그레이션을 용이하게 함</span><span class="sxs-lookup"><span data-stu-id="b0910-127">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
