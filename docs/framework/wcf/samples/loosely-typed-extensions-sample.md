---
title: 느슨한 형 확장명 샘플
ms.date: 03/30/2017
ms.assetid: 56ce265b-8163-4b85-98e7-7692a12c4357
ms.openlocfilehash: 9ad00c1e76d14b32cb28216cfdbb1a01f82a70cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33504439"
---
# <a name="loosely-typed-extensions-sample"></a>느슨한 형 확장명 샘플
배포 개체 모델은 확장 데이터, 즉 배포 피드의 XML 표현에는 있지만 <xref:System.ServiceModel.Syndication.SyndicationFeed> 및 <xref:System.ServiceModel.Syndication.SyndicationItem>과 같은 클래스에서 명시적으로 노출되지 않는 정보로 작업할 수 있도록 풍부한 지원을 제공합니다. 이 샘플에서는 확장명 데이터로 작업하는 기본적인 기술을 보여 줍니다.  
  
 이 샘플에서는 예를 들기 위해 <xref:System.ServiceModel.Syndication.SyndicationFeed> 클래스를 사용하지만 이 샘플에 나온 패턴은 확장명 데이터를 지원하는 다음과 같은 모든 배포 클래스에서 사용할 수 있습니다.  
  
 <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
 <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
 <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
 <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
## <a name="sample-xml"></a>샘플 XML  
 참고로 이 샘플에 사용된 XML 문서는 다음과 같습니다.  
  
```xml  
<?xml version="1.0" encoding="IBM437"?>  
<feed myAttribute="someValue" xmlns="http://www.w3.org/2005/Atom">  
  <title type="text"></title>  
  <id>uuid:8f60c7b3-a3c0-4de7-a642-2165d77ce3c1;id=1</id>  
  <updated>2007-09-07T22:15:34Z</updated>  
  <simpleString xmlns="">hello, world!</simpleString>  
  <simpleString xmlns="">another simple string</simpleString>  
  <DataContractExtension xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.d  
atacontract.org/2004/07/Microsoft.Syndication.Samples">  
    <Key>X</Key>  
    <Value>4</Value>  
  </DataContractExtension>  
  <XmlSerializerExtension xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://ww  
w.w3.org/2001/XMLSchema" xmlns="">  
    <Key>Y</Key>  
    <Value>8</Value>  
  </XmlSerializerExtension>  
  <xElementExtension xmlns="">  
    <Key attr1="someValue">Z</Key>  
    <Value attr1="someValue">15</Value>  
  </xElementExtension>  
</feed>  
```  
  
 이 문서에는 다음과 같은 확장 데이터가 포함되어 있습니다.  
  
-   `myAttribute` 요소의 `<feed>` 특성  
  
-   `<simpleString>` 요소  
  
-   `<DataContractExtension>` 요소  
  
-   `<XmlSerializerExtension>` 요소  
  
-   `<xElementExtension>` 요소  
  
## <a name="writing-extension-data"></a>확장명 데이터 쓰기  
 특성 확장은 다음 샘플 코드에서와 같이 <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> 컬렉션에 항목을 추가하여 만듭니다.  
  
```  
//Attribute extensions are stored in a dictionary indexed by   
// XmlQualifiedName  
feed.AttributeExtensions.Add(new XmlQualifiedName("myAttribute", ""), "someValue");  
```  
  
 요소 확장은 <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> 컬렉션에 항목을 추가하여 만듭니다. 이러한 확장은 문자열, .NET Framework 개체의 XML serialization 또는 직접 코딩한 XML 노드와 같은 기본값이 될 수 있습니다.  
  
 다음 샘플 코드는 `simpleString`이라는 확장 요소를 만듭니다.  
  
```  
feed.ElementExtensions.Add("simpleString", "", "hello, world!");  
```  
  
 이 요소에 대 한 XML 네임 스페이스는 빈 네임 스페이스 ("") 및 해당 값은 "hello, world!" 문자열을 포함 하는 텍스트 노드입니다.  
  
 여러 개의 중첩 요소로 구성된 복합 요소 확장을 만드는 한 가지 방법은 다음 예제에 나온 것처럼 serialization을 위한 .NET Framework API를 사용하는 것입니다. <xref:System.Runtime.Serialization.DataContractSerializer>와 <xref:System.Xml.Serialization.XmlSerializer>가 모두 지원됩니다.  
  
```  
feed.ElementExtensions.Add( new DataContractExtension() { Key = "X", Value = 4 } );  
feed.ElementExtensions.Add( new XmlSerializerExtension { Key = "Y", Value = 8 }, new XmlSerializer( typeof( XmlSerializerExtension ) ) );  
```  
  
 이 예제에서 `DataContractExtension` 및 `XmlSerializerExtension`은 serializer와 함께 사용하도록 작성된 사용자 지정 형식입니다.  
  
 또한 <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> 클래스를 사용하여 <xref:System.Xml.XmlReader> 인스턴스에서 요소 확장을 만들 수도 있습니다. 이 경우에는 다음 샘플 코드에서와 같이 <xref:System.Xml.Linq.XElement>와 같은 XML 처리 API와 손쉽게 통합할 수 있습니다.  
  
```  
feed.ElementExtensions.Add(new XElement("xElementExtension",  
        new XElement("Key", new XAttribute("attr1", "someValue"), "Z"),  
        new XElement("Value", new XAttribute("attr1", "someValue"),   
        "15")).CreateReader());  
```  
  
## <a name="reading-extension-data"></a>확장 데이터 읽기  
 특성 확장의 값은 다음 샘플 코드에서와 같이 <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> 컬렉션에서 <xref:System.Xml.XmlQualifiedName>으로 특성을 조회하여 가져올 수 있습니다.  
  
```  
Console.WriteLine( feed.AttributeExtensions[ new XmlQualifiedName( "myAttribute", "" )]);  
```  
  
 요소 확장에는 `ReadElementExtensions<T>` 메서드를 사용하여 액세스합니다.  
  
```  
foreach( string s in feed2.ElementExtensions.ReadElementExtensions<string>("simpleString", ""))  
{  
    Console.WriteLine(s);  
}  
  
foreach (DataContractExtension dce in feed2.ElementExtensions.ReadElementExtensions<DataContractExtension>("DataContractExtension",  
"http://schemas.datacontract.org/2004/07/SyndicationExtensions"))  
{  
    Console.WriteLine(dce.ToString());  
}  
  
foreach (XmlSerializerExtension xse in feed2.ElementExtensions.ReadElementExtensions<XmlSerializerExtension>("XmlSerializerExtension", "", new XmlSerializer(typeof(XmlSerializerExtension))))  
{  
    Console.WriteLine(xse.ToString());  
}  
```  
  
 `XmlReader` 메서드를 사용하여 개별 요소 확장의 <xref:System.ServiceModel.Syndication.SyndicationElementExtension.GetReader>를 가져올 수도 있습니다.  
  
```  
foreach (SyndicationElementExtension extension in feed2.ElementExtensions.Where<SyndicationElementExtension>(x => x.OuterName == "xElementExtension"))  
{  
    XNode xelement = XElement.ReadFrom(extension.GetReader());  
    Console.WriteLine(xelement.ToString());  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\LooselyTypedExtensions`  
  
## <a name="see-also"></a>참고 항목  
 [강력한 형식 확장명](../../../../docs/framework/wcf/samples/strongly-typed-extensions-sample.md)  
 [WCF 배포](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
