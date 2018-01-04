---
title: "방법: WCF REST 프로그래밍 모델을 사용하여 임의의 데이터를 허용하는 서비스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e566c15a-b600-4e4a-be3a-4af43e767dae
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 170149f5a6c495b3f22b9fd30f79ecdda87789b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-service-that-accepts-arbitrary-data-using-the-wcf-rest-programming-model"></a><span data-ttu-id="91926-102">방법: WCF REST 프로그래밍 모델을 사용하여 임의의 데이터를 허용하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="91926-102">How to: Create a Service That Accepts Arbitrary Data using the WCF REST Programming Model</span></span>
<span data-ttu-id="91926-103">서비스 작업에서 데이터가 반환되는 방법을 개발자가 완전히 제어해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91926-103">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="91926-104">서비스 작업이 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 지원되지 않는 형식으로 데이터를 반환해야 하는 경우가 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="91926-104">This is the case when a service operation must return data in a format not supported by[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="91926-105">이 항목에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST 프로그래밍 모델을 사용하여 임의의 데이터를 받는 서비스를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-105">This topic discusses using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST Programming Model to create a service that receives arbitrary data.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="91926-106">서비스 계약을 구현하려면</span><span class="sxs-lookup"><span data-stu-id="91926-106">To implement the service contract</span></span>  
  
1.  <span data-ttu-id="91926-107">서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-107">Define the service contract.</span></span> <span data-ttu-id="91926-108">임의의 데이터를 받는 작업에는 <xref:System.IO.Stream> 형식의 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-108">The operation that receives the arbitrary data must have a parameter of type <xref:System.IO.Stream>.</span></span> <span data-ttu-id="91926-109">또한 이 매개 변수는 요청 본문에서 전달된 유일한 매개 변수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-109">In addition, this parameter must be the only parameter passed in the body of the request.</span></span> <span data-ttu-id="91926-110">다음 예제에서 설명하는 작업은 파일 이름 매개 변수도 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-110">The operation described in this example also takes a filename parameter.</span></span> <span data-ttu-id="91926-111">이 매개 변수는 요청 URL 내에서 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="91926-111">This parameter is passed within the URL of the request.</span></span> <span data-ttu-id="91926-112"><xref:System.UriTemplate>에서 <xref:System.ServiceModel.Web.WebInvokeAttribute>을 지정하여 URI 내에서 매개 변수가 전달되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91926-112">You can specify that a parameter is passed within the URL by specifying a <xref:System.UriTemplate> in the <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span></span> <span data-ttu-id="91926-113">URI를 호출 하는 데 사용 하는이 경우에서이 메서드는 "UploadFile/Some-filename"에서 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91926-113">In this case the URI used to call this method ends in "UploadFile/Some-Filename".</span></span> <span data-ttu-id="91926-114">URI 템플릿의 "{filename}" 일부 작업을 호출 하는 데 사용 하는 URI 내에서 작업에 대 한 filename 매개 변수가 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-114">The "{filename}" portion of the URI template specifies that the filename parameter for the operation is passed within the URI used to call the operation.</span></span>  
  
    ```csharp  
     [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    ```  
  
2.  <span data-ttu-id="91926-115">서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-115">Implement the service contract.</span></span> <span data-ttu-id="91926-116">계약에는 스트림의 임의의 데이터 파일을 받는 `UploadFile`메서드만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91926-116">The contract has only one method, `UploadFile` that receives a file of arbitrary data in a stream.</span></span> <span data-ttu-id="91926-117">작업은 읽은 바이트 수를 계산하는 스트림을 읽고 나서 파일 이름과 읽은 바이트 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-117">The operation reads the stream counting the number of bytes read and then displays the filename and the number of bytes read.</span></span>  
  
    ```csharp  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
    ```  
  
### <a name="to-host-the-service"></a><span data-ttu-id="91926-118">서비스를 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="91926-118">To host the service</span></span>  
  
1.  <span data-ttu-id="91926-119">서비스를 호스트할 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91926-119">Create a console application to host the service.</span></span>  
  
    ```csharp  
    class Program  
    {  
       static void Main(string[] args)  
       {  
       }  
    }  
    ```  
  
2.  <span data-ttu-id="91926-120">`Main` 메서드 내에 서비스의 기본 주소를 저장할 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91926-120">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```csharp  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3.  <span data-ttu-id="91926-121">서비스 클래스 및 기본 주소를 지정하는 서비스에 대한 <xref:System.ServiceModel.ServiceHost> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91926-121">Create a <xref:System.ServiceModel.ServiceHost> instance for the service that specifies the service class and the base address.</span></span>  
  
    ```csharp  
    ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
    ```  
  
4.  <span data-ttu-id="91926-122"><xref:System.ServiceModel.WebHttpBinding>및 <xref:System.ServiceModel.Description.WebHttpBehavior>계약을 지정하는 끝점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-122">Add an endpoint that specifies the contract, <xref:System.ServiceModel.WebHttpBinding>, and <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5.  <span data-ttu-id="91926-123">서비스 호스트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="91926-123">Open the service host.</span></span> <span data-ttu-id="91926-124">이제 서비스에서 요청을 받을 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="91926-124">The service is now ready to receive requests.</span></span>  
  
    ```csharp  
    host.Open();  
    Console.WriteLine("Host opened");  
    ```  
  
### <a name="to-call-the-service-programmatically"></a><span data-ttu-id="91926-125">서비스를 프로그래밍 방식으로 호출하려면</span><span class="sxs-lookup"><span data-stu-id="91926-125">To call the service programmatically</span></span>  
  
1.  <span data-ttu-id="91926-126">서비스를 호출하는 데 사용되는 URI를 사용하여 <xref:System.Net.HttpWebRequest>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91926-126">Create a <xref:System.Net.HttpWebRequest> with the URI used to call the service.</span></span> <span data-ttu-id="91926-127">이 코드에서 기본 주소는 `"/UploadFile/Text"`와 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="91926-127">In this code, the base address is combined with `"/UploadFile/Text"`.</span></span> <span data-ttu-id="91926-128">URI의 `"UploadFile"` 부분은 호출할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-128">The `"UploadFile"` portion of the URI specifies the operation to call.</span></span> <span data-ttu-id="91926-129">URI의 `"Test.txt"` 부분은 `UploadFile` 작업에 전달할 파일 이름 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-129">The `"Test.txt"` portion of the URI specifies the filename parameter to pass to the `UploadFile` operation.</span></span> <span data-ttu-id="91926-130">이러한 항목 모두 작업 계약에 적용된 <xref:System.UriTemplate>에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="91926-130">Both of these items map to the <xref:System.UriTemplate> applied to the operation contract.</span></span>  
  
    ```csharp  
    HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
    ```  
  
2.  <span data-ttu-id="91926-131"><xref:System.Net.HttpWebRequest.Method%2A>의 <xref:System.Net.HttpWebRequest> 속성을 `POST`로 설정하고 <xref:System.Net.HttpWebRequest.ContentType%2A> 속성을 `"text/plain"`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-131">Set the <xref:System.Net.HttpWebRequest.Method%2A> property of the <xref:System.Net.HttpWebRequest> to `POST` and the <xref:System.Net.HttpWebRequest.ContentType%2A> property to `"text/plain"`.</span></span> <span data-ttu-id="91926-132">이렇게 하면 코드가 데이터를 보내고 있으며 데이터가 일반 텍스트 형식이라는 사실을 서비스에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="91926-132">This tells the service that the code is sending data and that data is in plain text.</span></span>  
  
    ```csharp  
    req.Method = "POST";  
    req.ContentType = "text/plain";  
    ```  
  
3.  <span data-ttu-id="91926-133"><xref:System.Net.HttpWebRequest.GetRequestStream%2A>을 호출하여 요청 스트림을 가져오고, 읽을 데이터를 만들고, 해당 데이터를 요청 스트림에 작성하고, 스트림을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="91926-133">Call <xref:System.Net.HttpWebRequest.GetRequestStream%2A> to get the request stream, create the data to send, write that data to the request stream, and close the stream.</span></span>  
  
    ```csharp  
    Stream reqStream = req.GetRequestStream();  
    byte[] fileToSend = new byte[12345];  
    for (int i = 0; i < fileToSend.Length; i++)  
       {  
           fileToSend[i] = (byte)('a' + (i % 26));  
       }  
    reqStream.Write(fileToSend, 0, fileToSend.Length);  
    reqStream.Close();  
    ```  
  
4.  <span data-ttu-id="91926-134"><xref:System.Net.HttpWebRequest.GetResponse%2A>를 호출하여 서비스에서 요청을 가져오고 응답 데이터를 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-134">Get the response from the service by calling <xref:System.Net.HttpWebRequest.GetResponse%2A> and display the response data to the console.</span></span>  
  
    ```csharp  
    HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
    Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
    ```  
  
5.  <span data-ttu-id="91926-135">서비스 호스트를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="91926-135">Close the service host.</span></span>  
  
    ```csharp  
    host.Close();  
    ```  
  
## <a name="example"></a><span data-ttu-id="91926-136">예</span><span class="sxs-lookup"><span data-stu-id="91926-136">Example</span></span>  
 <span data-ttu-id="91926-137">다음은 이 예제에 해당되는 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="91926-137">The following is a complete listing of the code for this example.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Net;  
  
namespace ReceiveRawData  
{  
    [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Host opened");  
  
            HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
            req.Method = "POST";  
            req.ContentType = "text/plain";  
            Stream reqStream = req.GetRequestStream();  
            byte[] fileToSend = new byte[12345];  
            for (int i = 0; i < fileToSend.Length; i++)  
            {  
                fileToSend[i] = (byte)('a' + (i % 26));  
            }  
            reqStream.Write(fileToSend, 0, fileToSend.Length);  
            reqStream.Close();  
            HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
            Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="91926-138">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="91926-138">Compiling the Code</span></span>  
  
-   <span data-ttu-id="91926-139">코드를 컴파일할 때 System.ServiceModel.dll 및 System.ServiceModel.Web.dll을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="91926-139">When compiling the code reference System.ServiceModel.dll and System.ServiceModel.Web.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91926-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91926-140">See Also</span></span>  
 [<span data-ttu-id="91926-141">UriTemplate 및 UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="91926-141">UriTemplate and UriTemplateTable</span></span>](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)  
 [<span data-ttu-id="91926-142">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="91926-142">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="91926-143">WCF 웹 HTTP 프로그래밍 모델 개요</span><span class="sxs-lookup"><span data-stu-id="91926-143">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)
