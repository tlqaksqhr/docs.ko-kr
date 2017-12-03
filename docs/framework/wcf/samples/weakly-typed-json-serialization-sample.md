---
title: "약한형 JSON Serialization 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b30e501-4ef5-474d-9fad-a9d559cf9c52
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3b804064a2b7a7bb0f587ae1dc2014769ca6e058
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="weakly-typed-json-serialization-sample"></a>약한형 JSON Serialization 샘플
사용자 정의 형식을 지정된 통신 형식으로 serialize하거나 통신 형식을 사용자 정의 형식으로 다시 deserialize할 경우 서비스와 클라이언트 모두에서 지정된 사용자 정의 형식을 사용할 수 있어야 합니다. 보통 이렇게 하기 위해 이 사용자 정의 형식에 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 적용하고 해당 멤버에 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 적용합니다. 이 메커니즘은 [How to: Serialize and Deserialize JSON Data](../../../../docs/framework/wcf/feature-details/how-to-serialize-and-deserialize-json-data.md)항목에 설명된 대로 JSON(JavaScript Object Notation) 개체로 작업하는 경우에도 적용됩니다.  
  
 일부 시나리오에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스 또는 클라이언트가 개발자의 제어를 벗어난 외부의 서비스 또는 클라이언트로 생성된 JSON 개체에 액세스해야 합니다. 더 많은 웹 서비스에서 공개적으로 JSON API를 노출하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개발자가 임의의 JSON 개체를 deserialize하는 로컬 사용자 정의 형식을 구성하는 것에 실익이 없어질 수도 있습니다. 이 샘플에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개발자가 사용자 정의 형식을 만들지 않고 deserialize된 임의의 JSON 개체로 작업할 수 있도록 해 주는 메커니즘을 제공합니다. 컴파일할 때에는 JSON 개체가 deserialize되는 형식을 알 수 없기 때문에 JSON 개체의 *약한 형식의 serialization* 이라고 합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 예를 들어, 공개 웹 서비스 API는 서비스 사용자에 대한 일부 정보를 설명하는 다음 JSON 개체를 반환합니다.  
  
```json  
{"personal": {"name": "Paul", "age": 23, "height": 1.7, "isSingle": true, "luckyNumbers": [5,17,21]}, "favoriteBands": ["Band ABC", "Band XYZ"]}  
```  
  
 이 개체를 deserialize하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에서 다음 사용자 정의 형식을 구현해야 합니다.  
  
```  
[DataContract]  
 public class MemberProfile  
 {  
     [DataMember]  
     public PersonalInfo personal;  
  
     [DataMember]  
     public string[] favoriteBands;  
 }  
  
 [DataContract]  
 public class PersonalInfo  
 {  
     [DataMember]  
     public string name;  
  
     [DataMember]  
     public int age;  
  
     [DataMember]  
     public double height;  
  
     [DataMember]  
     public bool isSingle;  
  
     [DataMember]  
     public int[] luckyNumbers;  
 }  
```  
  
 이 과정이 부담이 될 수 있으며, 클라이언트에서 두 개 이상의 JSON 개체를 처리해야 하는 경우 특히 그렇습니다.  
  
 이 샘플에서 제공하는 `JsonObject` 형식은 deserialize된 JSON 개체의 약한 형식의 표현을 소개합니다. `JsonObject` 는 JSON 개체와 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 사전 간의 자연 매핑 및 JSON 배열과 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 배열 간의 매핑에 의존합니다. 다음 코드에서는 `JsonObject` 형식을 보여 줍니다.  
  
```  
// Instantiation of JsonObject json omitted  
  
string name = json["root"]["personal"]["name"];  
int age = json["root"]["personal"]["age"];  
double height = json["root"]["personal"]["height"];  
bool isSingle = json["root"]["personal"]["isSingle"];  
int[] luckyNumbers = {  
                                     json["root"]["personal"]["luckyNumbers"][0],  
                                     json["root"]["personal"]["luckyNumbers"][1],  
                                     json["root"]["personal"]["luckyNumbers"][2]   
                                 };  
string[] favoriteBands = {  
                                        json["root"]["favoriteBands"][0],  
                                        json["root"]["favoriteBands"][1]  
                                    };  
```  
  
 컴파일할 때 해당 형식을 선언하지 않고 JSON 개체와 배열을 '찾아볼' 수 있습니다. 최상위 `["root"]` 개체의 요구 사항에 대한 설명은 [Mapping Between JSON and XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md)항목에 설명된 대로 JSON(JavaScript Object Notation) 개체로 작업하는 경우에도 적용됩니다.  
  
> [!NOTE]
>  `JsonObject` 클래스는 예로서만 제공됩니다. 이 클래스는 아직 테스트를 제대로 거치지 않았으며 프로덕션 환경에서는 사용하지 말아야 합니다. 약한 형식의 JSON serialization에서 확실히 암시되는 의미는 `JsonObject`로 작업할 때 형식 안전성이 부족하다는 것입니다.  
  
 `JsonObject` 형식을 사용하려면 클라이언트 작업 계약에서 반환 형식으로 <xref:System.ServiceModel.Channels.Message> 를 사용해야 합니다.  
  
```  
[ServiceContract]  
    interface IClientSideProfileService  
    {  
        // There is no need to write a DataContract for the complex type returned by the service.  
        // The client will use a JsonObject to browse the JSON in the received message.  
  
        [OperationContract]  
        [WebGet(ResponseFormat = WebMessageFormat.Json)]  
        Message GetMemberProfile();  
    }  
```  
  
 그러면 다음 코드에 표시된 것과 같이 `JsonObject` 가 인스턴스화됩니다.  
  
```  
// Code to instantiate IClientSideProfileService channel omitted…  
  
// Make a request to the service and obtain the Json response  
XmlDictionaryReader reader = channel.GetMemberProfile().GetReaderAtBodyContents();  
  
// Go through the Json as though it is a dictionary. There is no need to map it to a .NET CLR type.  
JsonObject json = new JsonObject(reader);  
```  
  
 `JsonObject` 생성자는 <xref:System.Xml.XmlDictionaryReader>메서드를 통해 얻을 수 있는 <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> 를 받습니다. 판독기에는 클라이언트에서 받는 JSON 메시지의 XML 표현이 포함되어 있습니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] 는 [Mapping Between JSON and XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md)항목에 설명된 대로 JSON(JavaScript Object Notation) 개체로 작업하는 경우에도 적용됩니다.  
  
 프로그램에서는 다음이 출력됩니다.  
  
```  
Service listening at http://localhost:8000/.  
To view the JSON output from the sample, navigate to http://localhost:8000/GetMemberProfile  
This is Paul's page. I am 23 years old and I am 1.7 meters tall.  
I am single.  
My lucky numbers are 5, 17, and 21.  
My favorite bands are Band ABC and Band XYZ.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)에 설명된 대로 WeaklyTypedJson.sln 솔루션을 빌드합니다.  
  
3.  솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Ajax\WeaklyTypedJson`  
  
## <a name="see-also"></a>참고 항목
