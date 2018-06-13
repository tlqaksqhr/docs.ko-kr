---
title: '방법: WebRequest 클래스를 사용하여 데이터 보내기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a40ab63e0fbac4227d74999c8c83f02e3c9e4b4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394659"
---
# <a name="how-to-send-data-using-the-webrequest-class"></a><span data-ttu-id="55ee8-102">방법: WebRequest 클래스를 사용하여 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="55ee8-102">How to: Send Data Using the WebRequest Class</span></span>
<span data-ttu-id="55ee8-103">다음 프로시저에서는 서버에 데이터를 보내는 데 사용되는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-103">The following procedure describes the steps used to send data to a server.</span></span> <span data-ttu-id="55ee8-104">이 프로시저는 일반적으로 웹 페이지에 데이터를 게시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-104">This procedure is commonly used to post data to a Web page.</span></span>  
  
### <a name="to-send-data-to-a-host-server"></a><span data-ttu-id="55ee8-105">호스트에 데이터를 보내려면</span><span class="sxs-lookup"><span data-stu-id="55ee8-105">To send data to a host server</span></span>  
  
1.  <span data-ttu-id="55ee8-106">스크립트 또는 ASP.NET 페이지와 같이 데이터를 허용하는 리소스의 URI를 통해 <xref:System.Net.WebRequest.Create%2A>를 호출하여 <xref:System.Net.WebRequest> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A> with the URI of the resource that accepts data, for example, a script or ASP.NET page.</span></span>  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="55ee8-107">.NET Framework에서는 “http:”, “https:”, “ftp:” 및 “file:”으로 시작하는 URI에 대해 **WebRequest** 및 **WebResponse**에서 파생된 프로토콜별 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-107">The .NET Framework provides protocol-specific classes derived from **WebRequest** and **WebResponse** for URIs that begin with "http:", "https:'', "ftp:", and "file:".</span></span> <span data-ttu-id="55ee8-108">다른 프로토콜을 사용하는 리소스에 액세스하려면 **WebRequest** 및 **WebResponse**에서 파생되는 프로토콜별 클래스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-108">To access resources using other protocols, you must implement protocol-specific classes that derive from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="55ee8-109">자세한 내용은 [플러그형 프로토콜 프로그래밍](../../../docs/framework/network-programming/programming-pluggable-protocols.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55ee8-109">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) .</span></span>  
  
2.  <span data-ttu-id="55ee8-110">**WebRequest**에서 필요한 속성 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-110">Set any property values that you need in the **WebRequest**.</span></span> <span data-ttu-id="55ee8-111">예를 들어 인증을 사용하도록 설정하려면 **Credentials** 속성을 <xref:System.Net.NetworkCredential> 클래스의 인스턴스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-111">For example, to enable authentication, set the **Credentials** property to an instance of the <xref:System.Net.NetworkCredential> class.</span></span>  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     <span data-ttu-id="55ee8-112">대부분의 경우 데이터를 보내는 데는 **WebRequest** 인스턴스 자체로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-112">In most cases, the **WebRequest** instance itself is sufficient to send data.</span></span> <span data-ttu-id="55ee8-113">그러나 프로토콜별 속성을 설정해야 할 경우 **WebRequest**를 프로토콜별 형식으로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-113">However, if you need to set protocol-specific properties, you must cast the **WebRequest** to the protocol-specific type.</span></span> <span data-ttu-id="55ee8-114">예를 들어 <xref:System.Net.HttpWebRequest>의 HTTP 관련 속성에 액세스하려면 **WebRequest**를 **HttpWebRequest** 참조로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-114">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebRequest>, cast the **WebRequest** to an **HttpWebRequest** reference.</span></span> <span data-ttu-id="55ee8-115">다음 코드 예제에서는 HTTP 관련 <xref:System.Net.HttpWebRequest.UserAgent%2A> 속성을 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-115">The following code example shows how to set the HTTP-specific <xref:System.Net.HttpWebRequest.UserAgent%2A> property.</span></span>  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  <span data-ttu-id="55ee8-116">요청을 통해 데이터를 보내도록 허용하는 프로토콜 메서드를 지정합니다(예: HTTP **POST** 메서드).</span><span class="sxs-lookup"><span data-stu-id="55ee8-116">Specify a protocol method that permits data to be sent with a request, such as the HTTP **POST** method.</span></span>  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  <span data-ttu-id="55ee8-117">**ContentLength** 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-117">Set the **ContentLength** property.</span></span>  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  <span data-ttu-id="55ee8-118">**ContentType** 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-118">Set the **ContentType** property to an appropriate value.</span></span>  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  <span data-ttu-id="55ee8-119"><xref:System.Net.WebRequest.GetRequestStream%2A> 메서드를 호출하여 요청 데이터를 포함하는 스트림을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-119">Get the stream that holds request data by calling the <xref:System.Net.WebRequest.GetRequestStream%2A> method.</span></span>  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  <span data-ttu-id="55ee8-120">이 메서드에서 반환된 <xref:System.IO.Stream> 개체에 데이터를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-120">Write the data to the <xref:System.IO.Stream> object returned by this method.</span></span>  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  <span data-ttu-id="55ee8-121">**Stream.Close** 메서드를 호출하여 요청 스트림을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-121">Close the request stream by calling the **Stream.Close** method.</span></span>  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. <span data-ttu-id="55ee8-122"><xref:System.Net.WebRequest.GetResponse%2A>를 호출하여 요청을 서버에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-122">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A>.</span></span> <span data-ttu-id="55ee8-123">이 메서드는 서버 응답을 포함하는 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-123">This method returns an object containing the server's response.</span></span> <span data-ttu-id="55ee8-124">반환된 <xref:System.Net.WebResponse> 개체의 형식은 요청 URI 구성표에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-124">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span>  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="55ee8-125"><xref:System.Net.WebResponse> 개체가 필요 없게 되면 <xref:System.Net.WebResponse.Close%2A> 메서드를 호출하여 개체를 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-125">After you are finished with a <xref:System.Net.WebResponse> object, you must close it by calling the <xref:System.Net.WebResponse.Close%2A> method.</span></span> <span data-ttu-id="55ee8-126">또는 응답 개체에서 응답 스트림을 이미 가져온 경우 <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> 메서드를 호출하여 스트림을 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-126">Alternatively, if you have gotten the response stream from the response object, you can close the stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="55ee8-127">응답이나 스트림을 닫지 않으면 응용 프로그램이 서버에 대한 연결을 모두 사용하여 추가 요청을 처리하지 못하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-127">If you do not close the response or the stream, your application can run out of connections to the server and become unable to process additional requests.</span></span>  
  
10. <span data-ttu-id="55ee8-128">**WebResponse**의 속성에 액세스하거나 **WebResponse**를 프로토콜별 인스턴스로 캐스팅하여 프로토콜별 속성을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-128">You can access the properties of the **WebResponse** or cast the **WebResponse** to a protocol-specific instance to read protocol-specific properties.</span></span> <span data-ttu-id="55ee8-129">예를 들어 <xref:System.Net.HttpWebResponse>의 HTTP 관련 속성에 액세스하려면 **WebResponse**를 **HttpWebResponse** 참조로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-129">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast the **WebResponse** to an **HttpWebResponse** reference.</span></span>  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. <span data-ttu-id="55ee8-130">서버에서 전송된 응답 데이터를 포함하는 스트림을 가져오려면 **WebResponse**의 <xref:System.Net.WebResponse.GetResponseStream%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-130">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A> method of the **WebResponse**.</span></span>  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. <span data-ttu-id="55ee8-131">응답에서 데이터를 읽은 후 **Stream.Close** 메서드를 사용하여 응답 스트림을 닫거나 **WebResponse.Close** 메서드를 사용하여 응답을 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-131">After reading the data from the response, you must either close the response stream using the **Stream.Close** method or close the response using the **WebResponse.Close** method.</span></span> <span data-ttu-id="55ee8-132">응답 스트림 및 **WebResponse**에서 둘 다 **Close** 메서드를 호출할 필요가 없지만 호출해도 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55ee8-132">It is not necessary to call the **Close** method on both the response stream and the **WebResponse**, but doing so is not harmful.</span></span>  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="55ee8-133">예</span><span class="sxs-lookup"><span data-stu-id="55ee8-133">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestPostExample  
    {  
        public static void Main ()  
        {  
            // Create a request using a URL that can receive a post.   
            WebRequest request = WebRequest.Create ("http://www.contoso.com/PostAccepter.aspx ");  
            // Set the Method property of the request to POST.  
            request.Method = "POST";  
            // Create POST data and convert it to a byte array.  
            string postData = "This is a test that posts this string to a Web server.";  
            byte[] byteArray = Encoding.UTF8.GetBytes (postData);  
            // Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded";  
            // Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length;  
            // Get the request stream.  
            Stream dataStream = request.GetRequestStream ();  
            // Write the data to the request stream.  
            dataStream.Write (byteArray, 0, byteArray.Length);  
            // Close the Stream object.  
            dataStream.Close ();  
            // Get the response.  
            WebResponse response = request.GetResponse ();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream ();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader (dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd ();  
            // Display the content.  
            Console.WriteLine (responseFromServer);  
            // Clean up the streams.  
            reader.Close ();  
            dataStream.Close ();  
            response.Close ();  
        }  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Net  
Imports System.Text  
Namespace Examples.System.Net  
    Public Class WebRequestPostExample  
  
        Public Shared Sub Main()  
            ' Create a request using a URL that can receive a post.   
            Dim request As WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx ")  
            ' Set the Method property of the request to POST.  
            request.Method = "POST"  
            ' Create POST data and convert it to a byte array.  
            Dim postData As String = "This is a test that posts this string to a Web server."  
            Dim byteArray As Byte() = Encoding.UTF8.GetBytes(postData)  
            ' Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded"  
            ' Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length  
            ' Get the request stream.  
            Dim dataStream As Stream = request.GetRequestStream()  
            ' Write the data to the request stream.  
            dataStream.Write(byteArray, 0, byteArray.Length)  
            ' Close the Stream object.  
            dataStream.Close()  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams.  
            reader.Close()  
            dataStream.Close()  
            response.Close()  
        End Sub  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="55ee8-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55ee8-134">See Also</span></span>  
 [<span data-ttu-id="55ee8-135">인터넷 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="55ee8-135">Creating Internet Requests</span></span>](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [<span data-ttu-id="55ee8-136">네트워크에서 스트림 사용</span><span class="sxs-lookup"><span data-stu-id="55ee8-136">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [<span data-ttu-id="55ee8-137">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="55ee8-137">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="55ee8-138">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="55ee8-138">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)  
 [<span data-ttu-id="55ee8-139">방법: WebRequest 클래스를 사용하여 데이터 요청</span><span class="sxs-lookup"><span data-stu-id="55ee8-139">How to: Request Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)
