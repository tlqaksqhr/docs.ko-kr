---
title: OperationContextScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11c11108-8eb4-4d49-95a0-83285a812262
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f636fe5bc79c18634f2239bc403c5189531737b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="operationcontextscope"></a><span data-ttu-id="9e35a-102">OperationContextScope</span><span class="sxs-lookup"><span data-stu-id="9e35a-102">OperationContextScope</span></span>
<span data-ttu-id="9e35a-103">OperationContextScope 샘플에서는 헤더를 사용하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 호출에 추가 정보를 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-103">The OperationContextScope sample demonstrates how to send extra information on a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] call using headers.</span></span> <span data-ttu-id="9e35a-104">이 샘플에서는 서버와 클라이언트 모두가 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-104">In this sample, both the server and client are console applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e35a-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="9e35a-106">샘플에서는 클라이언트가 <xref:System.ServiceModel.Channels.MessageHeader>를 사용하여 <xref:System.ServiceModel.OperationContextScope>로 추가 정보를 보낼 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-106">The sample demonstrates how a client can send additional information as a <xref:System.ServiceModel.Channels.MessageHeader> using <xref:System.ServiceModel.OperationContextScope>.</span></span> <span data-ttu-id="9e35a-107"><xref:System.ServiceModel.OperationContextScope> 개체는 채널로 범위를 지정하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-107">An <xref:System.ServiceModel.OperationContextScope> object is created by scoping it to a channel.</span></span> <span data-ttu-id="9e35a-108">원격 서비스로 해석해야 하는 헤더는 <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> 컬렉션에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-108">Headers that must be translated to the remote service can be added to the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="9e35a-109">이 컬렉션에 추가된 헤더는 서비스에서 <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>에 액세스하여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-109">Headers added to this collection can be retrieved on the service by accessing <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span></span> <span data-ttu-id="9e35a-110">호출은 여러 채널에 대해 수행되며, 클라이언트에 추가된 헤더는 <xref:System.ServiceModel.OperationContextScope>를 만드는 데 사용된 채널에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-110">Its calls are made on multiple channels and then the headers added to the client only apply to the channel that was used to create the <xref:System.ServiceModel.OperationContextScope>.</span></span>  
  
## <a name="messageheaderreader"></a><span data-ttu-id="9e35a-111">MessageHeaderReader</span><span class="sxs-lookup"><span data-stu-id="9e35a-111">MessageHeaderReader</span></span>  
 <span data-ttu-id="9e35a-112">클라이언트에서 메시지를 받은 후 <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> 컬렉션에서 헤더 조회를 시도하는 샘플 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-112">This is the sample service that receives a message from the client and tries to look up the header in the <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="9e35a-113">클라이언트에서는 전송한 GUID를 헤더에 전달하고 서비스에서는 사용자 지정 헤더를 검색하며, 있는 경우 클라이언트에서 인수로 전달한 GUID와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-113">The client passes the GUID that it sent in the header and the service retrieves the custom header and, if present, compares it with the GUID passed as the argument by the client.</span></span>  
  
```  
public bool RetrieveHeader(string guid)  
{  
     MessageHeaders messageHeaderCollection =   
             OperationContext.Current.IncomingMessageHeaders;  
     String guidHeader = null;  
  
     Console.WriteLine("Trying to check if IncomingMessageHeader " +  
               " collection contains header with value {0}", guid);  
     if (messageHeaderCollection.FindHeader(  
                       CustomHeader.HeaderName,   
                       CustomHeader.HeaderNamespace) != -1)  
     {  
          guidHeader = messageHeaderCollection.GetHeader<String>(  
           CustomHeader.HeaderName, CustomHeader.HeaderNamespace);  
     }  
     else  
     {  
          Console.WriteLine("No header was found");  
     }  
     if (guidHeader != null)  
     {  
          Console.WriteLine("Found header with value {0}. "+   
         "Does it match with GUID sent as parameter: {1}",   
          guidHeader, guidHeader.Equals(guid));  
      }  
  
      Console.WriteLine();  
      //Return true if header is present and equals the guid sent by  
      // client as argument  
      return (guidHeader != null && guidHeader.Equals(guid));  
}  
```  
  
## <a name="messageheaderclient"></a><span data-ttu-id="9e35a-114">MessageHeaderClient</span><span class="sxs-lookup"><span data-stu-id="9e35a-114">MessageHeaderClient</span></span>  
 <span data-ttu-id="9e35a-115">이에 의해 생성 된 프록시를 사용 하는 클라이언트 구현 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 원격 서비스와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-115">This is the client implementation that uses the proxy generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to communicate with the remote service.</span></span> <span data-ttu-id="9e35a-116">여기서는 먼저 `MessageHeaderReaderClient`의 프록시 개체 두 개를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-116">It first creates two proxy objects of `MessageHeaderReaderClient`.</span></span>  
  
```  
//Create two clients to the remote service.  
MessageHeaderReaderClient client1 = new MessageHeaderReaderClient();  
MessageHeaderReaderClient client2 = new MessageHeaderReaderClient();  
```  
  
 <span data-ttu-id="9e35a-117">그러면 클라이언트에서 OperationContextScope를 만들고 범위를 `client1`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-117">Client then creates an OperationContextScope and scopes it to `client1`.</span></span> <span data-ttu-id="9e35a-118">여기서는 <xref:System.ServiceModel.Channels.MessageHeader>를 <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A>에 추가하고 두 클라이언트 모두에 대해 한 번의 호출을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-118">It adds a <xref:System.ServiceModel.Channels.MessageHeader> to <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> and invokes one call on both clients.</span></span> <span data-ttu-id="9e35a-119">헤더에 대해서만 전송 됩니다 되도록 `client1` 아닌 `client2` 반환 값을 확인 하 여는 `RetrieveHeader` 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-119">It ensures that the header is sent only on `client1` and not on `client2` by checking the return value from the `RetrieveHeader` call.</span></span>  
  
```  
using (new OperationContextScope(client1.InnerChannel))  
{  
    //Create a new GUID that is sent as the header.  
    String guid = Guid.NewGuid().ToString();  
  
    //Create a MessageHeader for the GUID we just created.  
    MessageHeader customHeader = MessageHeader.CreateHeader(CustomHeader.HeaderName, CustomHeader.HeaderNamespace, guid);  
  
    //Add the header to the OutgoingMessageHeader collection.  
    OperationContext.Current.OutgoingMessageHeaders.Add(customHeader);  
  
    //Now call RetreieveHeader on both the proxies. Since the OperationContextScope is tied to   
    //client1's InnerChannel, the header should only be added to calls made on that client.  
    //Calls made on client2 should not be sending the header across even though the call  
    //is made in the same OperationContextScope.  
    Console.WriteLine("Using client1 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: True", client1.RetrieveHeader(guid));  
  
    Console.WriteLine();  
    Console.WriteLine("Using client2 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: False", client2.RetrieveHeader(guid));  
}  
```  
  
 <span data-ttu-id="9e35a-120">이 샘플은 자체 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-120">This sample is self-hosted.</span></span> <span data-ttu-id="9e35a-121">샘플을 실행한 결과 다음 샘플 출력이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-121">The following sample output from running the sample is provided:</span></span>  
  
```  
Prompt> Service.exe  
The service is ready.  
Press <ENTER> to terminate service.  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
Found header with value 2239da67-546f-42d4-89dc-8eb3c06215d8. Does it match with GUID sent as parameter: True  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
No header was found  
  
Prompt>Client.exe  
Using client1 to send message  
Did server retrieve the header? : Actual: True, Expected: True  
  
Using client2 to send message  
Did server retrieve the header? : Actual: False, Expected: False  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9e35a-122">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="9e35a-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9e35a-123">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="9e35a-124">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="9e35a-125">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9e35a-126">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9e35a-127">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="9e35a-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9e35a-128">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="9e35a-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9e35a-129">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35a-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\OperationContextScope`  
  
## <a name="see-also"></a><span data-ttu-id="9e35a-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e35a-130">See Also</span></span>
