---
title: 스트리밍 피드 샘플
ms.date: 03/30/2017
ms.assetid: 1f1228c0-daaa-45f0-b93e-c4a158113744
ms.openlocfilehash: 2c420bad9ad96107f56b5435efa6fffd6941cdaa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33505539"
---
# <a name="streaming-feeds-sample"></a><span data-ttu-id="01aca-102">스트리밍 피드 샘플</span><span class="sxs-lookup"><span data-stu-id="01aca-102">Streaming Feeds Sample</span></span>
<span data-ttu-id="01aca-103">이 샘플에서는 많은 수의 항목이 포함된 배포 피드를 관리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-103">This sample demonstrates how to manage syndication feeds that contain large numbers of items.</span></span> <span data-ttu-id="01aca-104">서버에서 이 샘플은 항목을 네트워크 스트림에 쓰기 바로 전까지 피드 내에 개별 <xref:System.ServiceModel.Syndication.SyndicationItem> 개체를 만드는 동작을 지연시키는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-104">On the server, the sample demonstrates how to delay the creation of individual <xref:System.ServiceModel.Syndication.SyndicationItem> objects within the feed until immediately before the item is written to the network stream.</span></span>  
  
 <span data-ttu-id="01aca-105">클라이언트에서 이 샘플은 사용자 지정 배포 피드 포맷터를 사용하여 읽고 있는 피드가 메모리에 완전히 버퍼링되지 않도록 네트워크 스트림에서 개별 항목을 읽을 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-105">On the client, the sample shows how a custom syndication feed formatter can be used to read individual items from the network stream so that the feed being read is never fully buffered into memory.</span></span>  
  
 <span data-ttu-id="01aca-106">배포 API의 스트리밍 기능을 가장 잘 보여 주기 위해 이 샘플에서는 서버가 매우 많은 수의 항목이 포함된 피드를 노출하는 경우와 같이 실제로 드문 시나리오를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-106">To best demonstrate the streaming capability of the syndication API, this sample uses a somewhat unlikely scenario in which the server exposes a feed that contains an infinite number of items.</span></span> <span data-ttu-id="01aca-107">이 경우 서버는 클라이언트가 피드에서 지정된 수의 항목(기본값: 10개)을 읽었다고 확인할 때까지 계속해서 피드에 새 항목을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-107">In this case, the server continues generating new items into the feed until it determines that the client has read a specified number of items from the feed (by default, 10).</span></span> <span data-ttu-id="01aca-108">단순성을 위해 클라이언트와 서버는 모두 동일한 프로세스로 구현되며 공유 `ItemCounter` 개체를 사용하여 클라이언트가 생성한 항목의 수를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-108">For simplicity, both the client and the server are implemented in the same process and use a shared `ItemCounter` object to keep track of how many items the client has produced.</span></span> <span data-ttu-id="01aca-109">`ItemCounter` 형식은 샘플 시나리오를 간단히 종료할 목적으로만 사용되며 설명하려는 패턴의 핵심 요소는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-109">The `ItemCounter` type exists only for the purpose of allowing the sample scenario to terminate cleanly, and is not a core element of the pattern being demonstrated.</span></span>  
  
 <span data-ttu-id="01aca-110">Visual C#의 사용를 시연할 반복기 (사용 하는 `yield``return` 키워드 구문).</span><span class="sxs-lookup"><span data-stu-id="01aca-110">The demonstration makes use of Visual C# iterators (using the `yield``return` keyword construct).</span></span> <span data-ttu-id="01aca-111">반복기에 대 한 자세한 내용은 MSDN의 "반복기 사용" 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="01aca-111">For more information about iterators, see the "Using Iterators" topic on MSDN.</span></span>  
  
## <a name="service"></a><span data-ttu-id="01aca-112">서비스</span><span class="sxs-lookup"><span data-stu-id="01aca-112">Service</span></span>  
 <span data-ttu-id="01aca-113">이 서비스는 다음 코드에서와 같이 하나의 작업으로 구성된 기본 <xref:System.ServiceModel.Web.WebGetAttribute> 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-113">The service implements a basic <xref:System.ServiceModel.Web.WebGetAttribute> contract that consists of one operation, as shown in the following code.</span></span>  
  
```  
[ServiceContract]  
interface IStreamingFeedService  
{  
    [WebGet]  
    [OperationContract]  
    Atom10FeedFormatter StreamedFeed();  
}  
```  
  
 <span data-ttu-id="01aca-114">이 서비스는 다음 코드에서와 같이 `ItemGenerator` 클래스에서 반복기를 사용하여 <xref:System.ServiceModel.Syndication.SyndicationItem> 인스턴스의 무한 스트림을 만드는 방식으로 이 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-114">The service implements this contract by using an `ItemGenerator` class to create a potentially infinite stream of <xref:System.ServiceModel.Syndication.SyndicationItem> instances using an iterator, as shown in the following code.</span></span>  
  
```  
class ItemGenerator  
{  
    public IEnumerable<SyndicationItem> GenerateItems()  
    {  
        while (counter.GetCount() < maxItemsRead)  
        {  
            itemsReturned++;  
            yield return CreateNextItem();  
        }  
  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="01aca-115">서비스 구현에서 피드를 만들면 버퍼링된 항목 컬렉션 대신 `ItemGenerator.GenerateItems()`의 출력이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-115">When the service implementation creates the feed, the output of `ItemGenerator.GenerateItems()` is used instead of a buffered collection of items.</span></span>  
  
```  
public Atom10FeedFormatter StreamedFeed()  
{  
    SyndicationFeed feed = new SyndicationFeed("Streamed feed", "Feed to test streaming", null);  
    //Generate an infinite stream of items. Both the client and the service share  
    //a reference to the ItemCounter, which allows the sample to terminate  
    //execution after the client has read 10 items from the stream  
    ItemGenerator itemGenerator = new ItemGenerator(this.counter, 10);  
  
    feed.Items = itemGenerator.GenerateItems();  
    return feed.GetAtom10Formatter();  
}  
```  
  
 <span data-ttu-id="01aca-116">결과적으로 항목 스트림은 메모리에 완전히 버퍼링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-116">As a result, the item stream is never fully buffered into memory.</span></span> <span data-ttu-id="01aca-117">에 중단점을 설정 하 여이 동작을 확인할 수는 `yield``return` 문 내부에 `ItemGenerator.GenerateItems()` 메서드와 서비스의 결과 반환한 후 처음으로이 중단점이 발생 하는 것을 확인는 `StreamedFeed()` 메서드.</span><span class="sxs-lookup"><span data-stu-id="01aca-117">You can observe this behavior by setting a breakpoint on the `yield``return` statement inside of the `ItemGenerator.GenerateItems()` method and noting that this breakpoint is encountered for the first time after the service has returned the result of the `StreamedFeed()` method.</span></span>  
  
## <a name="client"></a><span data-ttu-id="01aca-118">클라이언트</span><span class="sxs-lookup"><span data-stu-id="01aca-118">Client</span></span>  
 <span data-ttu-id="01aca-119">이 샘플의 클라이언트는 피드에 있는 개별 항목을 메모리에 버퍼링하는 대신 이 항목의 구체화를 지연시키는 사용자 지정 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> 구현을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-119">The client in this sample uses a custom <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> implementation that delays the materialization of individual items in the feed instead of buffering them into memory.</span></span> <span data-ttu-id="01aca-120">사용자 지정 `StreamedAtom10FeedFormatter` 인스턴스는 다음과 같이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-120">The custom `StreamedAtom10FeedFormatter` instance is used as follows.</span></span>  
  
```  
XmlReader reader = XmlReader.Create("http://localhost:8000/Service/Feeds/StreamedFeed");  
StreamedAtom10FeedFormatter formatter = new StreamedAtom10FeedFormatter(counter);  
  
SyndicationFeed feed = formatter.ReadFrom(reader);  
```  
  
 <span data-ttu-id="01aca-121">일반적으로 네트워크에서 피드의 전체 콘텐츠를 읽고 메모리에 버퍼링할 때까지는 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29>에 대한 호출이 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-121">Normally, a call to <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> does not return until the entire contents of the feed have been read from the network and buffered into memory.</span></span> <span data-ttu-id="01aca-122">반면 `StreamedAtom10FeedFormatter` 개체는 다음 코드에서와 같이 <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29>를 재정의하고 버퍼링된 컬렉션 대신 반복기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-122">However, the `StreamedAtom10FeedFormatter` object overrides <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> to return an iterator instead of a buffered collection, as shown in the following code.</span></span>  
  
```  
protected override IEnumerable<SyndicationItem> ReadItems(XmlReader reader, SyndicationFeed feed, out bool areAllItemsRead)  
{  
    areAllItemsRead = false;  
    return DelayReadItems(reader, feed);  
}  
  
private IEnumerable<SyndicationItem> DelayReadItems(XmlReader reader, SyndicationFeed feed)  
{  
    while (reader.IsStartElement("entry", "http://www.w3.org/2005/Atom"))  
    {  
        yield return this.ReadItem(reader, feed);  
    }  
  
    reader.ReadEndElement();  
}  
```  
  
 <span data-ttu-id="01aca-123">따라서 `ReadItems()`의 결과를 이동하는 클라이언트 응용 프로그램에서 사용 준비를 마칠 때까지는 네트워크에서 각 항목을 읽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-123">As a result, each item is not read from the network until the client application traversing the results of `ReadItems()` is ready to use it.</span></span> <span data-ttu-id="01aca-124">에 중단점을 설정 하 여이 동작을 확인할 수는 `yield``return` 문 내부에 `StreamedAtom10FeedFormatter.DelayReadItems()` 를 호출한 후 처음으로이 중단점이 발생 하는 검색 및 `ReadFrom()` 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-124">You can observe this behavior by setting a breakpoint on the `yield``return` statement inside of `StreamedAtom10FeedFormatter.DelayReadItems()` and noticing that this breakpoint is encountered for the first time after the call to `ReadFrom()` completes.</span></span>  
  
 <span data-ttu-id="01aca-125">다음 지침에서는 샘플을 빌드하고 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-125">The following instructions show how to build and run the sample.</span></span> <span data-ttu-id="01aca-126">클라이언트에서 10개의 항목을 읽고 나면 서버에서 항목 생성을 중지하지만 출력에는 클라이언트에서 10개 항목보다 훨씬 많은 항목을 읽는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-126">Note that although the server stops generating items after the client has read 10 items, the output shows that the client reads significantly more than 10 items.</span></span> <span data-ttu-id="01aca-127">이는 샘플에서 사용되는 네트워킹 바인딩에서 데이터를 4KB 단위의 세그먼트로 전송하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-127">This is because the networking binding used by the sample transmits data in four-kilobyte (KB) segments.</span></span> <span data-ttu-id="01aca-128">따라서 클라이언트는 한 항목을 읽을 기회가 생기기도 전에 4KB의 항목 데이터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-128">As such, the client receives 4KB of item data before it has the opportunity to read even one item.</span></span> <span data-ttu-id="01aca-129">이는 정상적인 동작입니다. 스트리밍된 HTTP 데이터를 적절한 크기의 세그먼트로 보내면 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-129">This is normal behavior (sending streamed HTTP data in reasonably-sized segments increases performance).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="01aca-130">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="01aca-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="01aca-131">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="01aca-132">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="01aca-133">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="01aca-134">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-134">The samples may already be installed on your computer.</span></span> <span data-ttu-id="01aca-135">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="01aca-135">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="01aca-136">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="01aca-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="01aca-137">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01aca-137">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StreamingFeeds`  
  
## <a name="see-also"></a><span data-ttu-id="01aca-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01aca-138">See Also</span></span>  
 [<span data-ttu-id="01aca-139">독립형 진단 피드</span><span class="sxs-lookup"><span data-stu-id="01aca-139">Stand-Alone Diagnostics Feed</span></span>](../../../../docs/framework/wcf/samples/stand-alone-diagnostics-feed-sample.md)
