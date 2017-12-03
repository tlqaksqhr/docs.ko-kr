---
title: "방법: WCF 웹 HTTP 프로그래밍 모델을 사용하여 임의의 데이터를 반환하는 서비스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0283955a-b4ae-458d-ad9e-6fbb6f529e3d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e1d808d4daf91b5ff89b05cab8359c90090f293
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-service-that-returns-arbitrary-data-using-the-wcf-web-http-programming-model"></a><span data-ttu-id="91ef9-102">방법: WCF 웹 HTTP 프로그래밍 모델을 사용하여 임의의 데이터를 반환하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="91ef9-102">How to: Create a Service That Returns Arbitrary Data Using The WCF Web HTTP Programming Model</span></span>
<span data-ttu-id="91ef9-103">서비스 작업에서 데이터가 반환되는 방법을 개발자가 완전히 제어해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-103">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="91ef9-104">경우 이것이 서비스 작업을 데이터 형식에서 지원 되지 않습니다를 반환 해야 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-104">This is the case when a service operation must return data in a format not supported by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="91ef9-105">이 항목에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WEB HTTP 프로그래밍 모델을 사용하여 이러한 서비스를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-105">This topic discusses using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WEB HTTP Programming Model to create such a service.</span></span> <span data-ttu-id="91ef9-106">이 서비스에는 스트림을 반환하는 하나의 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-106">This service has one operation that returns a stream.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="91ef9-107">서비스 계약을 구현하려면</span><span class="sxs-lookup"><span data-stu-id="91ef9-107">To implement the service contract</span></span>  
  
1.  <span data-ttu-id="91ef9-108">서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-108">Define the service contract.</span></span> <span data-ttu-id="91ef9-109">이 계약은 이름이 `IImageServer`이며 `GetImage`을 반환하는 <xref:System.IO.Stream>라는 하나의 메서드를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-109">The contract is called `IImageServer` and has one method called `GetImage` that returns a <xref:System.IO.Stream>.</span></span>  
  
    ```  
    [ServiceContract]  
        public interface IImageServer  
        {  
            [WebGet]  
            Stream GetImage(int width, int height);  
        }  
    ```  
  
     <span data-ttu-id="91ef9-110">이 메서드가 <xref:System.IO.Stream>을 반환하므로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 서비스 작업에서 반환되는 바이트를 해당 작업이 완전히 제어하며 이 작업이 반환 데이터에 형식을 적용하지 않는다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-110">Because the method returns a <xref:System.IO.Stream>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assumes that the operation has complete control over the bytes that are returned from the service operation and it applies no formatting to the data that is returned.</span></span>  
  
2.  <span data-ttu-id="91ef9-111">서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-111">Implement the service contract.</span></span> <span data-ttu-id="91ef9-112">이 계약에는 하나의 작업(`GetImage`)만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-112">The contract has only one operation (`GetImage`).</span></span> <span data-ttu-id="91ef9-113">이 메서드는 비트맵을 생성하여 <xref:System.IO.MemoryStream>에 .jpg 형식으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-113">This method generates a bitmap and then save it to a <xref:System.IO.MemoryStream> in .jpg format.</span></span> <span data-ttu-id="91ef9-114">그런 다음 이 작업은 해당 스트림을 호출자에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-114">The operation then returns that stream to the caller.</span></span>  
  
    ```  
    public class Service : IImageServer  
       {  
           public Stream GetImage(int width, int height)  
           {  
               Bitmap bitmap = new Bitmap(width, height);  
               for (int i = 0; i < bitmap.Width; i++)  
               {  
                   for (int j = 0; j < bitmap.Height; j++)  
                   {  
                       bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);  
                   }  
               }  
               MemoryStream ms = new MemoryStream();  
               bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);  
               ms.Position = 0;  
               WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";  
               return ms;  
           }  
       }  
    ```  
  
     <span data-ttu-id="91ef9-115">밑에서 두 번째에 있는 코드 줄 `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`를 보십시오.</span><span class="sxs-lookup"><span data-stu-id="91ef9-115">Notice the second to last line of code: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span></span>  
  
     <span data-ttu-id="91ef9-116">콘텐츠 형식 헤더를 설정 `"image/jpeg"`합니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-116">This sets the content type header to `"image/jpeg"`.</span></span> <span data-ttu-id="91ef9-117">이 샘플에서는 .jpg 파일을 반환하는 방법을 보여 주지만 코드를 수정하여 필요한 모든 종류의 데이터를 원하는 형식으로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-117">Although this sample shows how to return a .jpg file, it can be modified to return any type of data that is required, in any format.</span></span> <span data-ttu-id="91ef9-118">이 작업은 데이터를 검색 또는 생성한 다음 스트림에 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-118">The operation must retrieve or generate the data and then write it to a stream.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="91ef9-119">서비스를 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="91ef9-119">To host the service</span></span>  
  
1.  <span data-ttu-id="91ef9-120">서비스를 호스트할 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-120">Create a console application to host the service.</span></span>  
  
    ```  
    class Program  
    {  
        static void Main(string[] args)  
        {  
        }   
    }  
    ```  
  
2.  <span data-ttu-id="91ef9-121">`Main` 메서드 내에 서비스의 기본 주소를 저장할 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-121">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3.  <span data-ttu-id="91ef9-122">서비스 클래스 및 기본 주소를 지정하는 서비스에 대한 <xref:System.ServiceModel.ServiceHost> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-122">Create a <xref:System.ServiceModel.ServiceHost> instance for the service specifying the service class and the base address.</span></span>  
  
    ```  
    ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
    ```  
  
4.  <span data-ttu-id="91ef9-123"><xref:System.ServiceModel.WebHttpBinding> 및 <xref:System.ServiceModel.Description.WebHttpBehavior>를 사용하여 끝점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-123">Add an endpoint using the <xref:System.ServiceModel.WebHttpBinding> and the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```  
    host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5.  <span data-ttu-id="91ef9-124">서비스 호스트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-124">Open the service host.</span></span>  
  
    ```  
    host.Open()  
    ```  
  
6.  <span data-ttu-id="91ef9-125">사용자가 Enter 키를 눌러 서비스를 종료할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-125">Wait until the user presses ENTER to terminate the service.</span></span>  
  
    ```  
    Console.WriteLine("Service is running");  
    Console.Write("Press ENTER to close the host");  
    Console.ReadLine();  
    host.Close();  
    ```  
  
### <a name="to-call-the-raw-service-using-internet-explorer"></a><span data-ttu-id="91ef9-126">Internet Explorer를 사용하여 원시 서비스를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="91ef9-126">To call the raw service using Internet Explorer</span></span>  
  
1.  <span data-ttu-id="91ef9-127">서비스를 실행하면 다음과 같은 서비스 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-127">Run the service, you should see the following output from the service.</span></span> `Service is running Press ENTER to close the host`  
  
2.  <span data-ttu-id="91ef9-128">Internet Explorer를 열고 `http://localhost:8000/Service/GetImage?width=50&height=40`을 입력하면 파란 대각선이 중앙을 통과하는 노란 사각형이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-128">Open Internet Explorer and type in `http://localhost:8000/Service/GetImage?width=50&height=40` you should see a yellow rectangle with a blue diagonal line through the center.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91ef9-129">예제</span><span class="sxs-lookup"><span data-stu-id="91ef9-129">Example</span></span>  
 <span data-ttu-id="91ef9-130">다음은 이 항목에 해당되는 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-130">The following is a complete listing of the code for this topic.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Drawing;  
  
namespace RawImageService  
{  
    // Define the service contract  
    [ServiceContract]  
    public interface IImageServer  
    {  
        [WebGet]  
        Stream GetImage(int width, int height);  
    }  
  
    // implement the service contract  
    public class Service : IImageServer  
    {  
        public Stream GetImage(int width, int height)  
        {  
            // Although this method returns a jpeg, it can be  
            // modified to return any data you want within the stream  
            Bitmap bitmap = new Bitmap(width, height);  
            for (int i = 0; i < bitmap.Width; i++)  
            {  
                for (int j = 0; j < bitmap.Height; j++)  
                {  
                    bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);  
                }  
            }  
            MemoryStream ms = new MemoryStream();  
            bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);  
            ms.Position = 0;  
            WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";  
            return ms;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Service is running");  
            Console.Write("Press ENTER to close the host");  
            Console.ReadLine();  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="91ef9-131">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="91ef9-131">Compiling the Code</span></span>  
  
-   <span data-ttu-id="91ef9-132">샘플 코드를 컴파일할 때 System.ServiceModel.dll 및 System.ServiceModel.Web.dll을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="91ef9-132">When compiling the sample code reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ef9-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91ef9-133">See Also</span></span>  
 [<span data-ttu-id="91ef9-134">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="91ef9-134">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
