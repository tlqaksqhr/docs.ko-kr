---
title: 'Windows Communication Foundation 채택 예상: 이후의 통합을 용이하게 함'
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: f81e158a5e7f897307c0c6d376dfe01dac127ead
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Windows Communication Foundation 채택 예상: 이후의 통합을 용이하게 함
현재 ASP.NET을 사용 하 고 나중에 WCF를 사용할 계획인 경우이 항목에서는 WCF 응용 프로그램도 함께 새 ASP.NET 웹 서비스는 사용할 수 있도록 지침을 제공 합니다.  
  
## <a name="general-recommendations"></a>일반 권장 사항  
 새로운 서비스를 위해 ASP.NET 2.0을 채택하십시오. 이렇게 하면 새 버전의 개선 사항과 향상된 내용에 접근할 수 있습니다. 그러나 WCF 구성 요소와 함께 ASP.NET 2.0 구성 요소를 사용 하 여 동일한 응용 프로그램의 가능성을도 허용 됩니다.  
  
## <a name="protocols"></a>프로토콜  
 ASP.NET 2.0의 새 기능을 사용하여 WS-I Basic Profile 1.1 준수에 대한 유효성을 검사합니다.  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 Ws 준수는 ASP.NET 웹 서비스-Basic Profile 1.1 상호 운용 가능 합니다 WCF 클라이언트와 WCF 미리 정의 된 바인딩을 사용 하 여 <xref:System.ServiceModel.BasicHttpBinding>합니다.  
  
## <a name="service-development"></a>서비스 개발  
 SOAPAction HTTP 헤더가 아닌 SOAP 메시지 본문 요소의 정규화된 이름을 기반으로 메서드로 메시지를 라우팅하려면 <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> 특성을 사용하지 마십시오. WCF 라우팅 메시지에 대해 SOAPAction HTTP 헤더를 사용합니다.  
  
## <a name="data-representation"></a>데이터 표현  
 <xref:System.Xml.Serialization.XmlSerializer>에서 기본적으로 형식을 serialize하는 XML은 해당 XML에 대한 네임스페이스가 명시적으로 정의되어 있는 경우 <xref:System.Runtime.Serialization.DataContractSerializer>에서 형식을 serialize하는 XML과 의미상 동일합니다. 나중에 위해 도입 WCF의 ASP.NET 웹 서비스와 함께 사용 하기 위해 데이터 형식을 정의 하는 경우 다음을 수행 합니다.  
  
1.  XML 스키마가 아닌 .NET Framework 클래스를 사용하여 형식을 정의합니다.  
  
2.  클래스에는 <xref:System.SerializableAttribute> 및 <xref:System.Xml.Serialization.XmlRootAttribute>만 추가하며, 형식에 대한 네임스페이스를 명시적으로 정의하려면 후자를 사용합니다. .NET Framework 클래스를 XML로 변환하는 방법을 제어하려면 <xref:System.Xml.Serialization> 네임스페이스로부터 특성을 추가하지 마십시오.  
  
 이 방법을 채택하면 전송을 위해 클래스가 serialize되도록 XML을 크게 변경하지 않고 나중에 <xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute>를 추가하여 .NET 클래스를 데이터 계약으로 만들 수 있습니다. WCF 응용 프로그램에 더 나은 성능 이점도 비롯 한 ASP.NET 웹 서비스에서 메시지에 사용 되는 형식 WCF 응용 프로그램에서 데이터 계약으로 처리 되어야 할 수 있습니다.  
  
## <a name="security"></a>보안  
 IIS(인터넷 정보 서비스)에서 제공하는 인증 옵션은 사용하지 마십시오. WCF 클라이언트를 지원 하지 않습니다. 서비스를 보호 하는 경우 이러한 옵션은 더 풍부 하며 표준 프로토콜을 기반으로 하기 때문에, WCF에서 제공 하는 옵션을 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Communication Foundation 채택 예상: 이후의 마이그레이션을 용이하게 함](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
