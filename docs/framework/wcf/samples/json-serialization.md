---
title: JSON serialization
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c4e7e15fdbe01a6d91658f4771ac72a0024e0ed
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="json-serialization"></a><span data-ttu-id="25887-102">JSON serialization</span><span class="sxs-lookup"><span data-stu-id="25887-102">JSON Serialization</span></span>
<span data-ttu-id="25887-103">이 샘플에서는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용하여 JavaScript Object Notation(JSON) 형식으로 데이터를 serialize 및 deserialize하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25887-103">This sample demonstrates how to use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> to serialize and deserialize data in the JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="25887-104">이 serialization 엔진에서는 JSON 데이터를 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식의 인스턴스로 변환하고 다시 JSON 데이터로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="25887-104">This serialization engine converts JSON data into instances of [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types and back into JSON data.</span></span> <span data-ttu-id="25887-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>는 <xref:System.Runtime.Serialization.DataContractSerializer>와 동일한 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="25887-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supports the same types as <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="25887-106">JSON 데이터 형식은 AJAX(Asynchronous JavaScript and XML) 스타일 웹 응용 프로그램을 작성하는 경우에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="25887-106">The JSON data format is especially useful when writing Asynchronous JavaScript and XML (AJAX)-style Web applications.</span></span> <span data-ttu-id="25887-107">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 AJAX 지원은 ScriptManager 컨트롤을 통해 ASP.NET AJAX와 함께 사용하도록 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="25887-107">AJAX support in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is optimized for use with ASP.NET AJAX through the ScriptManager control.</span></span> <span data-ttu-id="25887-108">사용 하는 방법에 대 한 예제 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ASP.NET AJAX와 함께 참조는 [AJAX 샘플과](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)합니다.</span><span class="sxs-lookup"><span data-stu-id="25887-108">For examples of how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] with ASP.NET AJAX, see the [AJAX Samples](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25887-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25887-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="25887-110">샘플에서는 `Person` 데이터 계약을 사용하여 serialization 및 deserialization을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25887-110">The sample uses a `Person` data contract to demonstrate serialization and deserialization.</span></span>  

```csharp
[DataContract]
class Person
{
    [DataMember]
    internal string name;

    [DataMember]
    internal int age;
}
```

 <span data-ttu-id="25887-111">`Person` 형식의 인스턴스를 JSON으로 serialize하려면 먼저 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 만들고 `WriteObject` 메서드를 사용하여 스트림에 JSON 데이터를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="25887-111">To serialize an instance of the `Person` type to JSON, create the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> first and use the `WriteObject` method to write JSON data to a stream.</span></span>  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 <span data-ttu-id="25887-112">메모리 스트림에는 유효한 JSON 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25887-112">The memory stream contains valid JSON data.</span></span>
  
```json  
{"age":42,"name":"John"}  
```  
  
 <span data-ttu-id="25887-113">샘플에서는 JSON 데이터에서 개체로의 deserialization을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25887-113">The sample demonstrates deserializing from JSON data into an object.</span></span> <span data-ttu-id="25887-114">그 후에 스트림을 되감고 `ReadObject`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="25887-114">You then rewind the stream and call `ReadObject`.</span></span>  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 <span data-ttu-id="25887-115">`p2` 개체를 확인하면 JSON 데이터가 올바르게 deserialize된 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25887-115">Examining the `p2` object reveals that the JSON data has been deserialized correctly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="25887-116">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25887-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="25887-117">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="25887-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="25887-118">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="25887-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="25887-119">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25887-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="25887-120">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="25887-120">To set up, build and run the sample</span></span>  
  
1.  <span data-ttu-id="25887-121">에 설명 된 대로 JsonSerialization.sln 솔루션을 구축 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25887-121">Build the solution JsonSerialization.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="25887-122">결과 콘솔 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="25887-122">Run the resulting console application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25887-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25887-123">See Also</span></span>
