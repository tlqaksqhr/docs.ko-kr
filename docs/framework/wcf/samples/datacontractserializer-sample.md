---
title: "DataContractSerializer 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: XML Formatter
ms.assetid: e0a2fe89-3534-48c8-aa3c-819862224571
caps.latest.revision: "37"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99ef79ee9e17074989bcf5a2d4e586dc790373c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="datacontractserializer-sample"></a><span data-ttu-id="38944-102">DataContractSerializer 샘플</span><span class="sxs-lookup"><span data-stu-id="38944-102">DataContractSerializer Sample</span></span>
<span data-ttu-id="38944-103">DataContractSerializer 샘플은 데이터 계약 클래스에 대한 일반 serialization 및 deserialization 서비스를 수행하는 <xref:System.Runtime.Serialization.DataContractSerializer>를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="38944-103">The DataContractSerializer sample demonstrates the <xref:System.Runtime.Serialization.DataContractSerializer>, which performs general serialization and deserialization services for the data contract classes.</span></span> <span data-ttu-id="38944-104">이 샘플에서는 만듭니다는 `Record` 개체, 메모리 스트림으로 serialize 및 deserialize는 메모리 스트림을 다시 다른 `Record` 개체의 사용 방법을 설명 하기는 <xref:System.Runtime.Serialization.DataContractSerializer>합니다.</span><span class="sxs-lookup"><span data-stu-id="38944-104">The sample creates a `Record` object, serializes it to a memory stream and deserializes the memory stream back to another `Record` object to demonstrate the use of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="38944-105">그런 다음 이진 작성기로 `Record` 개체를 deserialize하여 이진 작성기가 serialization에 미치는 영향을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="38944-105">The sample then serializes the `Record` object using a binary writer to demonstrate how the writer affects serialization.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38944-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38944-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="38944-107">`Record`에 대한 데이터 계약이 다음 샘플 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38944-107">The data contract for `Record` is shown in the following sample code.</span></span>  
  
```  
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
internal class Record  
{  
    private double n1;  
    private double n2;  
    private string operation;  
    private double result;  
  
    internal Record(double n1, double n2, string operation, double result)  
    {  
        this.n1 = n1;  
        this.n2 = n2;  
        this.operation = operation;  
        this.result = result;  
    }  
  
    [DataMember]  
    internal double OperandNumberOne  
    {  
        get { return n1; }  
        set { n1 = value; }  
    }  
  
    [DataMember]  
    internal double OperandNumberTwo  
    {  
        get { return n2; }  
        set { n2 = value; }  
    }  
  
    [DataMember]  
    internal string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [DataMember]  
    internal double Result  
    {  
        get { return result; }  
        set { result = value; }  
    }  
  
    public override string ToString()  
    {  
        return string.Format("Record: {0} {1} {2} = {3}", n1,  
            operation, n2, result);  
    }  
}  
```  
  
 <span data-ttu-id="38944-108">샘플 코드는 `Record`이라는 `record1` 개체를 만든 다음 해당 개체를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="38944-108">The sample code creates a `Record` object named `record1` then displays the object.</span></span>  
  
```  
Record record1 = new Record(1, 2, "+", 3);  
Console.WriteLine("Original record: {0}", record1.ToString());  
```  
  
 <span data-ttu-id="38944-109">이 샘플에서는 <xref:System.Runtime.Serialization.DataContractSerializer>를 사용하여 `record1`을 메모리 스트림으로 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="38944-109">The sample then uses the <xref:System.Runtime.Serialization.DataContractSerializer> to serialize `record1` into a memory stream.</span></span>  
  
```  
MemoryStream stream1 = new MemoryStream();  
  
//Serialize the Record object to a memory stream using DataContractSerializer.  
DataContractSerializer serializer = new DataContractSerializer(typeof(Record));  
serializer.WriteObject(stream1, record1);  
```  
  
 <span data-ttu-id="38944-110">그런 다음 샘플에서는 <xref:System.Runtime.Serialization.DataContractSerializer>를 사용하여 메모리 스트림을 다시 새 `Record` 개체로 deserialize하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="38944-110">Next, the sample uses the <xref:System.Runtime.Serialization.DataContractSerializer> to deserialize the memory stream back into a new `Record` object and displays it.</span></span>  
  
```  
stream1.Position = 0;  
  
//Deserialize the Record object back into a new record object.  
Record record2 = (Record)serializer.ReadObject(stream1);  
  
Console.WriteLine("Deserialized record: {0}", record2.ToString());  
```  
  
 <span data-ttu-id="38944-111">기본적으로 `DataContractSerializer`는 XML의 텍스트 표현을 사용하여 개체를 스트림으로 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="38944-111">By default, the `DataContractSerializer` encodes objects into a stream using a textual representation of XML.</span></span> <span data-ttu-id="38944-112">그러나 다른 작성기를 전달하여 XML의 인코딩에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38944-112">However, you can influence the encoding of the XML by passing in a different writer.</span></span> <span data-ttu-id="38944-113">이 샘플에서는 <xref:System.Xml.XmlDictionaryWriter.CreateBinaryWriter%2A>를 호출하여 이진 작성기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38944-113">The sample creates a binary writer by calling <xref:System.Xml.XmlDictionaryWriter.CreateBinaryWriter%2A>.</span></span> <span data-ttu-id="38944-114">그런 다음 <xref:System.Runtime.Serialization.DataContractSerializer.WriteObjectContent%2A>를 호출할 때 작성기와 레코드 개체를 serializer에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="38944-114">It then passes the writer and the record object to the serializer when it calls <xref:System.Runtime.Serialization.DataContractSerializer.WriteObjectContent%2A>.</span></span> <span data-ttu-id="38944-115">마지막으로 작성기를 플러시하고 스트림 길이를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="38944-115">Finally, the sample flushes the writer and reports on the length of the streams.</span></span>  
  
```  
MemoryStream stream2 = new MemoryStream();  
  
XmlDictionaryWriter binaryDictionaryWriter = XmlDictionaryWriter.CreateBinaryWriter(stream2);  
serializer.WriteObject(binaryDictionaryWriter, record1);  
binaryDictionaryWriter.Flush();  
  
//report the length of the streams  
Console.WriteLine("Text Stream is {0} bytes long", stream1.Length);  
Console.WriteLine("Binary Stream is {0} bytes long", stream2.Length);  
```  
  
 <span data-ttu-id="38944-116">샘플을 실행하면 원래 레코드와 deserialize된 레코드가 표시된 다음 텍스트 인코딩과 이진 인코딩의 길이를 비교한 내용이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="38944-116">When you run the sample, the original record and the deserialized record are displayed, followed by the comparison between the length of the text encoding and the binary encoding.</span></span> <span data-ttu-id="38944-117">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="38944-117">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Original record: Record: 1 + 2 = 3  
Deserialized record: Record: 1 + 2 = 3  
Text Stream is 233 bytes long  
Binary Stream is 156 bytes long  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="38944-118">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="38944-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="38944-119">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="38944-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="38944-120">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="38944-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="38944-121">샘플을 실행하려면 client\bin\client.exe를 입력하여 명령 프롬프트에서 클라이언트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="38944-121">To run the sample, start the client from the command prompt by typing client\bin\client.exe.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="38944-122">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38944-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="38944-123">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="38944-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="38944-124">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="38944-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="38944-125">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38944-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractSerializer`  
  
## <a name="see-also"></a><span data-ttu-id="38944-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38944-126">See Also</span></span>
