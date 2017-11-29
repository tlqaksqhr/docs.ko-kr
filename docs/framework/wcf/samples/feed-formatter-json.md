---
title: "피드 포맷터(JSON)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9c0b295-55e7-48ea-b308-ba51c7d31143
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d6e1a2fe05d041d28d897e8effab3dfddb98845
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="feed-formatter-json"></a>피드 포맷터(JSON)
이 샘플에서는 사용자 지정 <xref:System.ServiceModel.Syndication.SyndicationFeed> 및 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>를 사용하여 JSON(JavaScript Object Notation) 형식으로 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 클래스의 인스턴스를 serialize하는 방법을 보여 줍니다.  
  
## <a name="architecture-of-the-sample"></a>샘플 아키텍처  
 이 샘플에서는 `JsonFeedFormatter`에서 상속되는 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>라는 클래스를 구현합니다. `JsonFeedFormatter` 클래스는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용하여 JSON 형식으로 데이터를 읽고 씁니다. 내부적으로 포맷터는 `JsonSyndicationFeed`와 `JsonSyndicationItem`이라는 데이터 계약 형식의 사용자 지정 집합을 사용하여 serializer에 의해 생성되는 JSON 데이터의 형식을 제어합니다. 이러한 구현 정보는 최종 사용자에게 표시되지 않으므로 표준 <xref:System.ServiceModel.Syndication.SyndicationFeed> 및 <xref:System.ServiceModel.Syndication.SyndicationItem> 클래스를 호출할 수 있습니다.  
  
## <a name="writing-json-feeds"></a>JSON 피드 쓰기  
 다음 샘플 코드와 같이 이 샘플에 구현된 `JsonFeedFormatter`를 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>와 함께 사용하여 JSON 피드를 쓸 수 있습니다.  
  
```  
//Basic feed with sample data  
SyndicationFeed feed = new SyndicationFeed("Custom JSON feed", "A Syndication extensibility sample", null);  
feed.LastUpdatedTime = DateTime.Now;  
feed.Items = from s in new string[] { "hello", "world" }  
select new SyndicationItem()  
{  
    Summary = SyndicationContent.CreatePlaintextContent(s)  
};  
  
//Write the feed out to a MemoryStream in JSON format  
DataContractJsonSerializer writeSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));  
writeSerializer.WriteObject(stream, new JsonFeedFormatter(feed));  
```  
  
## <a name="reading-a-json-feed"></a>JSON 필드 읽기  
 다음 코드와 같이<xref:System.ServiceModel.Syndication.SyndicationFeed>를 사용하여 JSON 형식의 데이터 스트림에서 `JsonFeedFormatter`를 가져올 수 있습니다.  
  
 `//Read in the feed using the DataContractJsonSerializer`  
  
 `DataContractJsonSerializer readSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));`  
  
 `JsonFeedFormatter formatter = readSerializer.ReadObject(stream) as JsonFeedFormatter;`  
  
 `SyndicationFeed feedRead = formatter.Feed;`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\JsonFeeds`  
  
## <a name="see-also"></a>참고 항목
