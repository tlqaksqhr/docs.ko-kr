---
title: '방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션'
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: 048408adf8678c243a225a233cb1173c9b7f869f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495553"
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a>방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션
이 항목에서는 기본 ASP.NET AJAX 서비스는 해당 하는 AJAX 사용 WCF Windows Communication Foundation () 서비스를 마이그레이션하는 절차를 설명 합니다. ASP.NET AJAX 서비스의 기능적으로 동일한 WCF 버전을 작성 하는 방법을 보여 줍니다. 두 서비스는 함께 사용할 수 있습니다 또는 WCF 서비스는 ASP.NET AJAX 서비스를 바꾸는 데 사용할 수 있습니다.  
  
 기존 ASP.NET AJAX 마이그레이션 WCF AJAX 서비스에 서비스 제공 다음과 같은 이점을 제공 합니다.  
  
-   최소의 추가 구성만으로 AJAX 서비스를 SOAP 서비스로 노출할 수 있습니다.  
  
-   추적을 같은 WCF 기능에서 이점을 얻을 수 있으며 등 수 있습니다.  
  
 다음 절차에서는 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 사용하고 있다고 가정합니다.  
  
 이 항목에서 간략히 설명된 절차에서 얻어진 코드는 다음 예제에 나와 있습니다.  
  
 AJAX 사용 끝점을 통해 WCF 서비스를 노출 하는 방법에 대 한 자세한 내용은 참조는 [하는 방법: ASP.NET AJAX 끝점 추가를 사용 하 여 구성](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) 항목입니다.  
  
### <a name="to-create-and-test-the-aspnet-web-service-application"></a>ASP.NET 웹 서비스 응용 프로그램을 만들고 테스트하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]를 엽니다.  
  
2.  **파일** 메뉴 선택 **새로**, 다음 **프로젝트**, 다음 **웹**를 선택한 후 **ASP.NET 웹 서비스 응용 프로그램** .  
  
3.  프로젝트 이름을 `ASPHello` 클릭 **확인**합니다.  
  
4.  이 서비스에서 AJAX를 사용하려면 Service1.asmx.cs 파일에서 `System.Web.Script.Services.ScriptService]`가 포함된 행의 주석 처리를 제거합니다.  
  
5.  **빌드** 메뉴 선택 **솔루션 빌드**합니다.  
  
6.  **디버그** 메뉴 선택 **디버깅 하지 않고 시작**합니다.  
  
7.  생성된 웹 페이지에서 `HelloWorld` 작업을 선택합니다.  
  
8.  클릭는 **Invoke** 단추는 `HelloWorld` 테스트 페이지. 다음과 같은 XML 응답을 받게 됩니다.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <string xmlns="http://tempuri.org/">Hello World</string>  
    ```  
  
9. 이 응답을 통해 현재 ASP.NET AJAX 서비스가 작동 중임을 확인할 수 있으며, 특히 해당 서비스가 Service1.asmx/HelloWorld에서 HTTP POST 요청에 응답하는 끝점을 노출하고 XML을 반환함을 확인할 수 있습니다.  
  
     이제 WCF AJAX 서비스를 사용 하도록이 서비스를 변환 준비가 되었습니다.  
  
### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a>동등한 WCF AJAX 서비스 응용 프로그램을 만들려면  
  
1.  마우스 오른쪽 단추로 클릭는 **ASPHello** 프로젝트를 마우스 선택 **추가**, 다음 **새 항목**, 차례로 **AJAX 사용 WCF 서비스**합니다.  
  
2.  서비스 이름을 `WCFHello` 클릭 **추가**합니다.  
  
3.  WCFHello.svc.cs 파일을 엽니다.  
  
4.  Service1.asmx.cs에서 다음 구현과 복사는 `HelloWorld` 작업 합니다.  
  
    ```  
    public string HelloWorld()  
    {  
         return "Hello World";  
    }  
    ```  
  
5.  붙여넣기 구현을 `HelloWorld` WCFHello.svc.cs 파일에 다음 코드 대신에 작업을 합니다.  
  
    ```  
    public void DoWork()  
    {  
          // Add your operation implementation here  
          return;  
    }  
    ```  
  
6.  지정 된 `Namespace` 특성 <xref:System.ServiceModel.ServiceContractAttribute> 으로 `WCFHello`합니다.  
  
    ```  
    [ServiceContract(Namespace="WCFHello")]  
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]  
    public class WCFHello  
    { … }  
    ```  
  
7.  추가 <xref:System.ServiceModel.Web.WebInvokeAttribute> 에 `HelloWorld` 작업 집합과 <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> 반환할 속성 <xref:System.ServiceModel.Web.WebMessageFormat.Xml>합니다. 이 속성을 설정하지 않은 경우 기본 반환 형식은 <xref:System.ServiceModel.Web.WebMessageFormat.Json>입니다.  
  
    ```  
    [OperationContract]  
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]  
    public string HelloWorld()  
    {  
        return "Hello World";  
    }  
    ```  
  
8.  **빌드** 메뉴 선택 **솔루션 빌드**합니다.  
  
9. WCFHello.svc 파일을 열고 들어오고는 **디버그** 메뉴 선택 **디버깅 하지 않고 시작**합니다.  
  
10. 서비스는 끝점을 노출 이제 `WCFHello.svc/HelloWorld`, HTTP POST 요청에 응답 하 합니다. HTTP POST 요청은 브라우저에서 테스트할 수 없지만 끝점은 다음과 같은 XML을 반환합니다.  
  
    ```xml  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>  
    ```  
  
11. `WCFHello.svc/HelloWorld` 및 `Service1.aspx/HelloWorld` 끝점은 현재 기능적으로 동일 합니다.  
  
## <a name="example"></a>예제  
 이 항목에서 간략히 설명된 절차에서 얻어진 코드는 다음 예제에 나와 있습니다.  
  
```  
//This is the ASP.NET code in the Service1.asmx.cs file.  
  
using System;  
using System.Collections;  
using System.ComponentModel;  
using System.Data;  
using System.Linq;  
using System.Web;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using System.Xml.Linq;  
using System.Web.Script.Services;  
  
namespace ASPHello  
{  
    /// <summary>  
    /// Summary description for Service1.  
    /// </summary>  
    [WebService(Namespace = "http://tempuri.org/")]  
    [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]  
    [ToolboxItem(false)]  
    // To allow this Web Service to be called from script, using ASP.NET AJAX, uncomment the following line.   
    [System.Web.Script.Services.ScriptService]  
    public class Service1 : System.Web.Services.WebService  
    {  
  
        [WebMethod]  
        public string HelloWorld()  
        {  
            return "Hello World";  
        }  
    }  
}   
  
//This is the WCF code in the WCFHello.svc.cs file.  
using System;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Activation;  
using System.ServiceModel.Web;  
  
namespace ASPHello  
{  
    [ServiceContract(Namespace = "WCFHello")]  
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
    public class WCFHello  
    {  
        // Add [WebInvoke] attribute to use HTTP GET.  
        [OperationContract]  
        [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]  
        public string HelloWorld()  
        {  
            return "Hello World";  
        }  
  
        // Add more operations here and mark them with [OperationContract].  
    }  
}  
```  
  
 <xref:System.Xml.XmlDocument> 형식은 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 통해 serialize할 수 없으므로 <xref:System.Xml.Serialization.XmlSerializer>에서 지원하지 않습니다. 대신 <xref:System.Xml.Linq.XDocument> 형식을 사용하거나 <xref:System.Xml.XmlDocument.DocumentElement%2A>를 serialize할 수 있습니다.  
  
 ASMX 웹 서비스 업그레이드 하는-함께 WCF 서비스를 마이그레이션할 경우 클라이언트에서 같은 이름의 두 형식 매핑 하지 마십시오. 이 경우 같은 형식을 <xref:System.Web.Services.WebMethodAttribute> 및 <xref:System.ServiceModel.ServiceContractAttribute>에서 사용하면 serializer에 예외가 발생합니다.  
  
-   WCF 서비스가 먼저 추가 되 면에서 예외가 발생 ASMX 웹 서비스에 대 한 메서드 호출 <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> WCF 스타일 정의 순서가 프록시 우선 하기 때문에 있습니다.  
  
-   ASMX 웹 서비스는 먼저 추가 되 면 WCF 서비스에서 메서드를 호출 하면에서 예외가 발생 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 웹 서비스 스타일 정의 순서가 프록시 우선 하기 때문에 있습니다.  
  
 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>와 ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>의 동작에는 상당한 차이점이 있습니다. 예를 들어, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>는 키/값 쌍의 배열로 사전을 나타내고, ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>는 실제 JSON 개체로 사전을 나타냅니다. 따라서 ASP.NET AJAX에서 사전은 다음과 같이 나타납니다.  
  
```  
Dictionary<string, int> d = new Dictionary<string, int>();  
d.Add("one", 1);  
d.Add("two", 2);  
```  
  
 이 사전은 다음 목록에 표시된 것처럼 JSON 개체로 표현됩니다.  
  
-   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>에 의한 [{"Key":"one","Value":1},{"Key":"two","Value":2}]  
  
-   {"one": 1, "two": 2} ASP.NET ajax <xref:System.Web.Script.Serialization.JavaScriptSerializer>  
  
 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>는 키 유형이 문자열이 아닌 사전을 처리할 수 있다는 점에서 훨씬 강력합니다. 반면 <xref:System.Web.Script.Serialization.JavaScriptSerializer>는 키 유형이 문자열이 아닌 사전을 처리할 수 없습니다. 그러나 후자가 JSON에 더 적합합니다.  
  
 이 두 serializer의 중요한 차이점이 다음 표에 요약되어 있습니다.  
  
|차이의 범주|DataContractJsonSerializer|ASP.NET AJAX JavaScriptSerializer|  
|-----------------------------|--------------------------------|---------------------------------------|  
|빈 버퍼(새 바이트[0])를 <xref:System.Object> 또는 <xref:System.Uri> 또는 다른 클래스로 deserialize함|SerializationException|null|  
|<xref:System.DBNull.Value>의 serialization|{} (또는 {"__type": "#System"})|Null|  
|[Serializable] 형식의 private 멤버 serialization|serialize됨|serialize되지 않음|  
|<xref:System.Runtime.Serialization.ISerializable> 형식의 .public 속성 serialization|serialize되지 않음|serialize됨|  
|JSON "확장"|개체 멤버 이름({"a":"hello"})에 따옴표를 사용해야 하는 JSON 사양 준수|따옴표가 없는 개체 멤버 이름({a:"hello"}) 지원|  
|<xref:System.DateTime> UTC(협정 세계시)|형식을 지원 하지 않습니다 "\\/Date(123456789U)\\/" 또는 "\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\\\/)".|지원 형식 "\\/Date(123456789U)\\/" 및 "\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\ \\/) "형식을 DateTime 값으로.|  
|사전의 표현|KeyValuePair의 배열\<K, V >, 문자열이 아닌 키 유형을 처리 합니다.|실제 JSON 개체로 문자열인 키 유형만 처리합니다.|  
|이스케이프된 문자|항상 이스케이프 슬래시(/)가 포함되고, "\n"과 같이 이스케이프되지 않은 잘못된 JSON 문자는 사용할 수 없습니다.|DateTime 값에 이스케이프 슬래시(/)가 포함됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [방법: 구성을 사용하여 ASP.NET AJAX 끝점 추가](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
