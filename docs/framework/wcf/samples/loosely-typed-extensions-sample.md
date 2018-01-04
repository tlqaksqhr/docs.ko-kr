---
title: "느슨한 형 확장명 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56ce265b-8163-4b85-98e7-7692a12c4357
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e8861138f7763f413f06983bbfba5f6e0ec3c8b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="loosely-typed-extensions-sample"></a><span data-ttu-id="57b6e-102">느슨한 형 확장명 샘플</span><span class="sxs-lookup"><span data-stu-id="57b6e-102">Loosely-Typed Extensions Sample</span></span>
<span data-ttu-id="57b6e-103">배포 개체 모델은 확장 데이터, 즉 배포 피드의 XML 표현에는 있지만 <xref:System.ServiceModel.Syndication.SyndicationFeed> 및 <xref:System.ServiceModel.Syndication.SyndicationItem>과 같은 클래스에서 명시적으로 노출되지 않는 정보로 작업할 수 있도록 풍부한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-103">The Syndication object model provides rich support for working with extension data—information that is present in a syndication feed's XML representation but not explicitly exposed by classes such as <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem>.</span></span> <span data-ttu-id="57b6e-104">이 샘플에서는 확장명 데이터로 작업하는 기본적인 기술을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-104">This sample illustrates the basic techniques for working with extension data.</span></span>  
  
 <span data-ttu-id="57b6e-105">이 샘플에서는 예를 들기 위해 <xref:System.ServiceModel.Syndication.SyndicationFeed> 클래스를 사용하지만</span><span class="sxs-lookup"><span data-stu-id="57b6e-105">The sample uses the <xref:System.ServiceModel.Syndication.SyndicationFeed> class for the purposes of the example.</span></span> <span data-ttu-id="57b6e-106">이 샘플에 나온 패턴은 확장명 데이터를 지원하는 다음과 같은 모든 배포 클래스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-106">However, the patterns demonstrated in this sample can be used with all of the Syndication classes that support extension data:</span></span>  
  
 <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
 <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
 <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
 <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
## <a name="sample-xml"></a><span data-ttu-id="57b6e-107">샘플 XML</span><span class="sxs-lookup"><span data-stu-id="57b6e-107">Sample XML</span></span>  
 <span data-ttu-id="57b6e-108">참고로 이 샘플에 사용된 XML 문서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-108">For reference, the following XML document is used in this sample.</span></span>  
  
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
  
 <span data-ttu-id="57b6e-109">이 문서에는 다음과 같은 확장 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-109">This document contains the following pieces of extension data:</span></span>  
  
-   <span data-ttu-id="57b6e-110">`myAttribute` 요소의 `<feed>` 특성</span><span class="sxs-lookup"><span data-stu-id="57b6e-110">The `myAttribute` attribute of the `<feed>` element.</span></span>  
  
-   <span data-ttu-id="57b6e-111">`<simpleString>` 요소</span><span class="sxs-lookup"><span data-stu-id="57b6e-111">`<simpleString>` element.</span></span>  
  
-   <span data-ttu-id="57b6e-112">`<DataContractExtension>` 요소</span><span class="sxs-lookup"><span data-stu-id="57b6e-112">`<DataContractExtension>` element.</span></span>  
  
-   <span data-ttu-id="57b6e-113">`<XmlSerializerExtension>` 요소</span><span class="sxs-lookup"><span data-stu-id="57b6e-113">`<XmlSerializerExtension>` element.</span></span>  
  
-   <span data-ttu-id="57b6e-114">`<xElementExtension>` 요소</span><span class="sxs-lookup"><span data-stu-id="57b6e-114">`<xElementExtension>` element.</span></span>  
  
## <a name="writing-extension-data"></a><span data-ttu-id="57b6e-115">확장명 데이터 쓰기</span><span class="sxs-lookup"><span data-stu-id="57b6e-115">Writing Extension Data</span></span>  
 <span data-ttu-id="57b6e-116">특성 확장은 다음 샘플 코드에서와 같이 <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> 컬렉션에 항목을 추가하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-116">Attribute extensions are created by adding entries to the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection as shown in the following sample code.</span></span>  
  
```  
//Attribute extensions are stored in a dictionary indexed by   
// XmlQualifiedName  
feed.AttributeExtensions.Add(new XmlQualifiedName("myAttribute", ""), "someValue");  
```  
  
 <span data-ttu-id="57b6e-117">요소 확장은 <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> 컬렉션에 항목을 추가하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-117">Element extensions are created by adding entries to the <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> collection.</span></span> <span data-ttu-id="57b6e-118">이러한 확장은 문자열, .NET Framework 개체의 XML serialization 또는 직접 코딩한 XML 노드와 같은 기본값이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-118">These extensions can by basic values such as strings, XML serializations of .NET Framework objects, or XML nodes coded by hand.</span></span>  
  
 <span data-ttu-id="57b6e-119">다음 샘플 코드는 `simpleString`이라는 확장 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-119">The following sample code creates an extension element named `simpleString`.</span></span>  
  
```  
feed.ElementExtensions.Add("simpleString", "", "hello, world!");  
```  
  
 <span data-ttu-id="57b6e-120">이 요소에 대 한 XML 네임 스페이스는 빈 네임 스페이스 ("") 및 해당 값은 "hello, world!" 문자열을 포함 하는 텍스트 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-120">The XML namespace for this element is the empty namespace ("") and its value is a text node that contains the string "hello, world!".</span></span>  
  
 <span data-ttu-id="57b6e-121">여러 개의 중첩 요소로 구성된 복합 요소 확장을 만드는 한 가지 방법은 다음 예제에 나온 것처럼 serialization을 위한 .NET Framework API를 사용하는 것입니다. <xref:System.Runtime.Serialization.DataContractSerializer>와 <xref:System.Xml.Serialization.XmlSerializer>가 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-121">One way to create complex element extensions that consist of many nested elements is to use the .NET Framework APIs for serialization (both the <xref:System.Runtime.Serialization.DataContractSerializer> and the <xref:System.Xml.Serialization.XmlSerializer> are supported) as shown in the following examples.</span></span>  
  
```  
feed.ElementExtensions.Add( new DataContractExtension() { Key = "X", Value = 4 } );  
feed.ElementExtensions.Add( new XmlSerializerExtension { Key = "Y", Value = 8 }, new XmlSerializer( typeof( XmlSerializerExtension ) ) );  
```  
  
 <span data-ttu-id="57b6e-122">이 예제에서 `DataContractExtension` 및 `XmlSerializerExtension`은 serializer와 함께 사용하도록 작성된 사용자 지정 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-122">In this example, the `DataContractExtension` and `XmlSerializerExtension` are custom types written for use with a serializer.</span></span>  
  
 <span data-ttu-id="57b6e-123">또한 <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> 클래스를 사용하여 <xref:System.Xml.XmlReader> 인스턴스에서 요소 확장을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-123">The <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> class can also be used to create element extensions from an <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="57b6e-124">이 경우에는 다음 샘플 코드에서와 같이 <xref:System.Xml.Linq.XElement>와 같은 XML 처리 API와 손쉽게 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-124">This allows for easy integration with XML processing APIs such as <xref:System.Xml.Linq.XElement> as shown in the following sample code.</span></span>  
  
```  
feed.ElementExtensions.Add(new XElement("xElementExtension",  
        new XElement("Key", new XAttribute("attr1", "someValue"), "Z"),  
        new XElement("Value", new XAttribute("attr1", "someValue"),   
        "15")).CreateReader());  
```  
  
## <a name="reading-extension-data"></a><span data-ttu-id="57b6e-125">확장 데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="57b6e-125">Reading Extension Data</span></span>  
 <span data-ttu-id="57b6e-126">특성 확장의 값은 다음 샘플 코드에서와 같이 <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> 컬렉션에서 <xref:System.Xml.XmlQualifiedName>으로 특성을 조회하여 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-126">The values for attribute extensions can be obtained by looking up the attribute in the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection by its <xref:System.Xml.XmlQualifiedName> as shown in the following sample code.</span></span>  
  
```  
Console.WriteLine( feed.AttributeExtensions[ new XmlQualifiedName( "myAttribute", "" )]);  
```  
  
 <span data-ttu-id="57b6e-127">요소 확장에는 `ReadElementExtensions<T>` 메서드를 사용하여 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-127">Element extensions are accessed using the `ReadElementExtensions<T>` method.</span></span>  
  
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
  
 <span data-ttu-id="57b6e-128">`XmlReader` 메서드를 사용하여 개별 요소 확장의 <xref:System.ServiceModel.Syndication.SyndicationElementExtension.GetReader>를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-128">It is also possible to obtain an `XmlReader` at individual element extensions by using the <xref:System.ServiceModel.Syndication.SyndicationElementExtension.GetReader> method.</span></span>  
  
```  
foreach (SyndicationElementExtension extension in feed2.ElementExtensions.Where<SyndicationElementExtension>(x => x.OuterName == "xElementExtension"))  
{  
    XNode xelement = XElement.ReadFrom(extension.GetReader());  
    Console.WriteLine(xelement.ToString());  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="57b6e-129">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="57b6e-129">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="57b6e-130">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="57b6e-131">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="57b6e-132">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-132">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="57b6e-133">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-133">The samples may already be installed on your machine.</span></span> <span data-ttu-id="57b6e-134">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="57b6e-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="57b6e-135">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="57b6e-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="57b6e-136">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b6e-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\LooselyTypedExtensions`  
  
## <a name="see-also"></a><span data-ttu-id="57b6e-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57b6e-137">See Also</span></span>  
 [<span data-ttu-id="57b6e-138">강력한 형식 확장명</span><span class="sxs-lookup"><span data-stu-id="57b6e-138">Strongly-Typed Extensions</span></span>](../../../../docs/framework/wcf/samples/strongly-typed-extensions-sample.md)  
 [<span data-ttu-id="57b6e-139">WCF 배포</span><span class="sxs-lookup"><span data-stu-id="57b6e-139">WCF Syndication</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
