---
title: 'Windows Communication Foundation 채택 예상: 이후의 마이그레이션을 용이하게 함'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: aeafc164d16d9dc60ad0b3012da292e9b0bb38b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Windows Communication Foundation 채택 예상: 이후의 마이그레이션을 용이하게 함
을 보장 하기 위해 새로운 ASP.NET 응용 프로그램을 WCF로 쉽게는 향후 마이그레이션 권장 사항 뿐만 아니라 다음 권장 사항을 따릅니다.  
  
## <a name="protocols"></a>프로토콜  
 SOAP 1.2에 대한 ASP.NET 2.0 지원을 사용하지 않습니다.  
  
```xml  
<configuration>  
     <system.web>  
      <webServices >  
          <protocols>  
           <remove name="HttpSoap12"/>  
          </protocols>    
      </webServices>  
     </system.web>   
</configuration>  
```  
  
 WCF SOAP 1.1과 SOAP 1.2 처럼 서로 다른 프로토콜에 맞는 메시지에 게 서로 다른 끝점을 사용 하 여 거치도록 필요 하기 때문에 이렇게 하는 것이 좋습니다. ASP.NET 2.0 웹 서비스는 SOAP 1.1 및 SOAP 1.2 수 없습니다, 기본 구성을 모두 지원 하도록 구성 된 확실히 되는 원래 주소에서 단일 WCF 끝점으로 앞으로 마이그레이션된 경우 ASP.NET 웹의 모든과 호환 가능 서비스의 기존 클라이언트입니다. 또한 SOAP 1.1 대신 1.2를 선택하면 서비스의 클라이언트가 보다 엄격하게 제한됩니다.  
  
## <a name="service-development"></a>서비스 개발  
 WCF 서비스 계약을 적용 하 여 정의할 수 있습니다는 <xref:System.ServiceModel.ServiceContractAttribute> 인터페이스 또는 클래스 중 하나입니다. 이 특성을 인터페이스에 적용하면 원하는 수의 클래스에서 다양하게 구현할 수 있는 계약의 정의가 생성되므로 클래스보다는 인터페이스에 적용하는 것이 좋습니다. ASP.NET 2.0은 클래스뿐만 아니라 인터페이스에도 <xref:System.Web.Services.WebService> 특성을 적용하는 옵션을 지원합니다. 그러나 이미 설명했듯이 ASP.NET 2.0에는 <xref:System.Web.Services.WebService> 특성이 클래스가 아닌 인터페이스에 적용될 경우 이 특성의 Namespace 매개 변수가 아무런 효과가 없다는 결점이 있습니다. 일반적으로 기본 값에서 서비스의 네임 스페이스를 수정 하도록 권장 하는 이후 http://tempuri.org의 Namespace 매개 변수를 사용 하는 <xref:System.Web.Services.WebService> 특성을 적용 하 여 ASP.NET 웹 서비스를 정의 계속 해야 하나는 <xref:System.ServiceModel.ServiceContractAttribute> 인터페이스 또는 클래스 특성입니다.  
  
-   이러한 인터페이스를 정의하는 메서드에 코드를 가능한 한 적게 사용합니다. 메서드의 작업을 다른 클래스에 위임하도록 합니다. 새 WCF 서비스 유형 다음 위임할 수도 상당한 작업을 해당 클래스.  
  
-   `MessageName`의 <xref:System.Web.Services.WebMethodAttribute> 매개 변수를 사용하여 서비스 작업에 명시적 이름을 제공합니다.  
  
    ```  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     ASP.NET에서 작업에 대 한 기본 이름이 WCF에서 제공 된 기본 이름과에서 다르기 때문에 이렇게 하는 것은 중요 합니다. 명시적 이름을 제공함으로써 기본 이름을 사용하지 않아도 됩니다.  
  
-   WCF 다형 메서드를 통한 작업 구현을 지원 하지 않으므로 다형 메서드로 ASP.NET 웹 서비스 작업을 구현 하지 마십시오.  
  
-   <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>를 사용하여 HTTP 요청을 메서드로 라우트할 SOAPAction HTTP 헤더에 명시적 값을 제공합니다.  
  
    ```  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     이 접근 방법을 사용 하지 않아도 되며는 기본 SOAPAction 값 ASP.NET 및 WCF 에서도 마찬가지에서 사용 하는 사용 합니다.  
  
-   SOAP 확장을 사용하지 마세요. SOAP 확장이 필요한 경우 용도 고려 되 고 있는 WCF에서 제공 되는 기능 인지 확인 합니다. 해당 되는 경우 실제로 경우 당장은 WCF 즉시 채택 하지 합니다.  
  
## <a name="state-management"></a>상태 관리  
 서비스의 상태를 유지하지 마세요. 가 상태를 유지 관리 되는 경향이 응용 프로그램의 확장성을 손상 할 뿐만 아니라 WCF는 ASP.NET 호환 모드에서 ASP.NET 메커니즘을 지원 하지만 ASP.NET 및 WCF의 상태 관리 메커니즘은 매우 다릅니다.  
  
## <a name="exception-handling"></a>예외 처리  
 서비스에서 보내고 받을 데이터 형식의 구조를 디자인할 때 클라이언트로 전달하려는 서비스에서 발생할 수 있는 다양한 종류의 예외를 표시하기 위한 구조도 디자인합니다.  
  
```  
[Serializable]  
[XmlRoot(  
     Namespace="ExplicitNamespace", IsNullable=true)]  
    public partial class AnticipatedException {  
  
     private string anticipatedExceptionInformationField;  
  
     public string AnticipatedExceptionInformation {  
      get {  
          return this.anticipatedExceptionInformationField;  
          }  
      set {  
          this.anticipatedExceptionInformationField = value;  
          }  
     }  
}  
```  
  
 다음과 같이 해당 클래스에 자신을 XML로 serialize할 수 있는 기능을 부여합니다.  
  
```  
public XmlNode ToXML()  
{  
     XmlSerializer serializer = new XmlSerializer(  
      typeof(AnticipatedException));  
     MemoryStream memoryStream = new MemoryStream();  
     XmlTextWriter writer = new XmlTextWriter(  
     memoryStream, UnicodeEncoding.UTF8);  
     serializer.Serialize(writer, this);  
     XmlDocument document = new XmlDocument();  
     document.LoadXml(new string(  
     UnicodeEncoding.UTF8.GetChars(  
     memoryStream.GetBuffer())).Trim());  
    return document.DocumentElement;  
}  
```  
  
 그러면 해당 클래스를 사용하여 명시적으로 throw된 <xref:System.Web.Services.Protocols.SoapException> 인스턴스에 대한 자세한 정보를 제공할 수 있습니다.  
  
```  
AnctipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 이 예외 클래스 재사용 하 여 WCF 됩니다<xref:System.ServiceModel.FaultException%601> 새 throw 하는 클래스 `FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>보안  
 다음은 몇 가지 보안 권장 사항입니다.  
  
-   방지 ASP.NET 2.0 프로필을 사용 하 여 사용이 제한 됩니다 ASP.NET 통합 모드의 wcf 서비스를 마이그레이션한 경우.  
  
-   ASP.NET 웹 서비스에서는 인터넷 정보 서비스 (IIS)를 사용 하 여 Acl 서비스에 대 한 액세스를 제어 하려면 Acl을 사용 하지 않도록, WCF 없는-때문 ASP.NET 웹 서비스 IIS 호스팅의 경우 WCF는 반드시 IIS에서 호스트할 필요가 없습니다.  
  
-   서비스 리소스에 대한 액세스 권한을 부여할 때 ASP.NET 2.0 역할 공급자를 사용할 것을 고려해 보세요.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Communication Foundation 채택 예상: 이후의 통합을 용이하게 함](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
