---
title: 오류 처리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, WebRequest and WebResponse classes exceptions
- Status property
- WebExceptions class, about WebExceptions class
- Timeout enumeration member
- ConnectFailure enumeration member
- TrustFailure enumeration member
- WebRequest class, exceptions
- requesting data from Internet, error handling
- Success enumeration member
- receiving data, errors
- ProtocolError enumeration member
- downloading Internet resources, error handling
- WebResponse class, exceptions
- SendFailure enumeration member
- errors [.NET Framework], WebRequest and WebResponse classes exceptions
- sending data, errors
- response to Internet request, error handling
- NameResolutionFailure enumeration member
- KeepAliveFailure enumeration member
- network resources, WebRequest and WebResponse classes exceptions
- RequestCanceled enumeration member
- ReceiveFailure enumeration member
- ServerProtocolViolation enumeration member
- ConnectionClosed enumeration member
- SecureChannelFailure enumeration member
ms.assetid: 657141cd-5cf5-4fdb-a4b2-4c040eba84b5
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 8020a92345ba85a99c0b46b2d4247d677defd054
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397925"
---
# <a name="handling-errors"></a><span data-ttu-id="0d80c-102">오류 처리</span><span class="sxs-lookup"><span data-stu-id="0d80c-102">Handling Errors</span></span>
<span data-ttu-id="0d80c-103"><xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스는 시스템 예외(예: <xref:System.ArgumentException>) 및 웹 관련 예외(<xref:System.Net.WebRequest.GetResponse%2A> 메서드에서 throw된 <xref:System.Net.WebException>)를 둘 다 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-103">The <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes throw both system exceptions (such as <xref:System.ArgumentException>) and Web-specific exceptions (which are <xref:System.Net.WebException> thrown by the <xref:System.Net.WebRequest.GetResponse%2A> method).</span></span>  
  
 <span data-ttu-id="0d80c-104">각 **WebException**에는 <xref:System.Net.WebExceptionStatus> 열거형의 값을 포함하는 <xref:System.Net.WebException.Status%2A> 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-104">Each **WebException** includes a <xref:System.Net.WebException.Status%2A> property that contains a value from the <xref:System.Net.WebExceptionStatus> enumeration.</span></span> <span data-ttu-id="0d80c-105">**Status** 속성을 검사하여 발생한 오류를 확인하고 적절한 단계를 수행하여 오류를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-105">You can examine the **Status** property to determine the error that occurred and take the proper steps to resolve the error.</span></span>  
  
 <span data-ttu-id="0d80c-106">다음 표에서는 **Status** 속성의 가능한 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-106">The following table describes the possible values for the **Status** property.</span></span>  
  
|<span data-ttu-id="0d80c-107">상태</span><span class="sxs-lookup"><span data-stu-id="0d80c-107">Status</span></span>|<span data-ttu-id="0d80c-108">설명</span><span class="sxs-lookup"><span data-stu-id="0d80c-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0d80c-109">ConnectFailure</span><span class="sxs-lookup"><span data-stu-id="0d80c-109">ConnectFailure</span></span>|<span data-ttu-id="0d80c-110">원격 서비스가 전송 수준에서 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-110">The remote service could not be contacted at the transport level.</span></span>|  
|<span data-ttu-id="0d80c-111">ConnectionClosed</span><span class="sxs-lookup"><span data-stu-id="0d80c-111">ConnectionClosed</span></span>|<span data-ttu-id="0d80c-112">연결이 조기에 닫혔습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-112">The connection was closed prematurely.</span></span>|  
|<span data-ttu-id="0d80c-113">KeepAliveFailure</span><span class="sxs-lookup"><span data-stu-id="0d80c-113">KeepAliveFailure</span></span>|<span data-ttu-id="0d80c-114">서버가 연결 유지 헤더 집합을 통해 설정된 연결을 닫았습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-114">The server closed a connection made with the Keep-alive header set.</span></span>|  
|<span data-ttu-id="0d80c-115">NameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="0d80c-115">NameResolutionFailure</span></span>|<span data-ttu-id="0d80c-116">이름 서비스가 호스트 이름을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-116">The name service could not resolve the host name.</span></span>|  
|<span data-ttu-id="0d80c-117">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="0d80c-117">ProtocolError</span></span>|<span data-ttu-id="0d80c-118">서버에서 받은 응답이 완료되었으나 프로토콜 수준에서 오류를 나타냈습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-118">The response received from the server was complete but indicated an error at the protocol level.</span></span>|  
|<span data-ttu-id="0d80c-119">ReceiveFailure</span><span class="sxs-lookup"><span data-stu-id="0d80c-119">ReceiveFailure</span></span>|<span data-ttu-id="0d80c-120">전체 응답이 원격 서버에서 수신되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-120">A complete response was not received from the remote server.</span></span>|  
|<span data-ttu-id="0d80c-121">RequestCanceled</span><span class="sxs-lookup"><span data-stu-id="0d80c-121">RequestCanceled</span></span>|<span data-ttu-id="0d80c-122">요청이 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-122">The request was canceled.</span></span>|  
|<span data-ttu-id="0d80c-123">SecureChannelFailure</span><span class="sxs-lookup"><span data-stu-id="0d80c-123">SecureChannelFailure</span></span>|<span data-ttu-id="0d80c-124">보안 채널 링크에서 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-124">An error occurred in a secure channel link.</span></span>|  
|<span data-ttu-id="0d80c-125">SendFailure</span><span class="sxs-lookup"><span data-stu-id="0d80c-125">SendFailure</span></span>|<span data-ttu-id="0d80c-126">전체 요청을 원격 서버로 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-126">A complete request could not be sent to the remote server.</span></span>|  
|<span data-ttu-id="0d80c-127">ServerProtocolViolation</span><span class="sxs-lookup"><span data-stu-id="0d80c-127">ServerProtocolViolation</span></span>|<span data-ttu-id="0d80c-128">서버 응답이 유효한 HTTP 응답이 아니었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-128">The server response was not a valid HTTP response.</span></span>|  
|<span data-ttu-id="0d80c-129">성공</span><span class="sxs-lookup"><span data-stu-id="0d80c-129">Success</span></span>|<span data-ttu-id="0d80c-130">오류가 발생하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-130">No error was encountered.</span></span>|  
|<span data-ttu-id="0d80c-131">시간 제한</span><span class="sxs-lookup"><span data-stu-id="0d80c-131">Timeout</span></span>|<span data-ttu-id="0d80c-132">요청에 대해 설정된 시간 제한 내에 응답이 수신되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-132">No response was received within the time-out set for the request.</span></span>|  
|<span data-ttu-id="0d80c-133">TrustFailure</span><span class="sxs-lookup"><span data-stu-id="0d80c-133">TrustFailure</span></span>|<span data-ttu-id="0d80c-134">서버 인증서를 유효성 검사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-134">A server certificate could not be validated.</span></span>|  
|<span data-ttu-id="0d80c-135">MessageLengthLimitExceeded</span><span class="sxs-lookup"><span data-stu-id="0d80c-135">MessageLengthLimitExceeded</span></span>|<span data-ttu-id="0d80c-136">요청을 보내거나 서버에서 응답을 받을 때 지정된 제한을 초과한 메시지를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-136">A message was received that exceeded the specified limit when sending a request or receiving a response from the server.</span></span>|  
|<span data-ttu-id="0d80c-137">보류 중</span><span class="sxs-lookup"><span data-stu-id="0d80c-137">Pending</span></span>|<span data-ttu-id="0d80c-138">내부 비동기 요청이 보류 중입니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-138">An internal asynchronous request is pending.</span></span>|  
|<span data-ttu-id="0d80c-139">PipelineFailure</span><span class="sxs-lookup"><span data-stu-id="0d80c-139">PipelineFailure</span></span>|<span data-ttu-id="0d80c-140">이 값은 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-140">This value supports the .NET Framework infrastructure and is not intended to be used directly in your code.</span></span>|  
|<span data-ttu-id="0d80c-141">ProxyNameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="0d80c-141">ProxyNameResolutionFailure</span></span>|<span data-ttu-id="0d80c-142">이름 확인자 서비스가 프록시 호스트 이름을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-142">The name resolver service could not resolve the proxy host name.</span></span>|  
|<span data-ttu-id="0d80c-143">UnknownError</span><span class="sxs-lookup"><span data-stu-id="0d80c-143">UnknownError</span></span>|<span data-ttu-id="0d80c-144">알 수 없는 형식의 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-144">An exception of unknown type has occurred.</span></span>|  
  
 <span data-ttu-id="0d80c-145">**Status** 속성이 **WebExceptionStatus.ProtocolError**이면 서버의 응답이 포함된 **WebResponse**를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-145">When the **Status** property is **WebExceptionStatus.ProtocolError**, a **WebResponse** that contains the response from the server is available.</span></span> <span data-ttu-id="0d80c-146">이 응답을 검사하여 프로토콜 오류의 실제 소스를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-146">You can examine this response to determine the actual source of the protocol error.</span></span>  
  
 <span data-ttu-id="0d80c-147">다음 예제에서는 **WebException**을 catch하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-147">The following example shows how to catch a **WebException**.</span></span>  
  
```csharp  
try   
{  
    // Create a request instance.  
    WebRequest myRequest =   
    WebRequest.Create("http://www.contoso.com");  
    // Get the response.  
    WebResponse myResponse = myRequest.GetResponse();  
    //Get a readable stream from the server.   
    Stream sr = myResponse.GetResponseStream();  
  
    //Read from the stream and write any data to the console.  
    bytesread = sr.Read( myBuffer, 0, length);  
    while( bytesread > 0 )   
    {  
        for (int i=0; i<bytesread; i++) {  
            Console.Write( "{0}", myBuffer[i]);  
        }  
        Console.WriteLine();  
        bytesread = sr.Read( myBuffer, 0, length);  
    }  
    sr.Close();  
    myResponse.Close();  
}  
catch (WebException webExcp)   
{  
    // If you reach this point, an exception has been caught.  
    Console.WriteLine("A WebException has been caught.");  
    // Write out the WebException message.  
    Console.WriteLine(webExcp.ToString());  
    // Get the WebException status code.  
    WebExceptionStatus status =  webExcp.Status;  
    // If status is WebExceptionStatus.ProtocolError,   
    //   there has been a protocol error and a WebResponse   
    //   should exist. Display the protocol error.  
    if (status == WebExceptionStatus.ProtocolError) {  
        Console.Write("The server returned protocol error ");  
        // Get HttpWebResponse so that you can check the HTTP status code.  
        HttpWebResponse httpResponse = (HttpWebResponse)webExcp.Response;  
        Console.WriteLine((int)httpResponse.StatusCode + " - "  
           + httpResponse.StatusCode);  
    }  
}  
catch (Exception e)   
{  
    // Code to catch other exceptions goes here.  
}  
```  
  
```vb  
Try  
    ' Create a request instance.  
    Dim myRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
    ' Get the response.  
    Dim myResponse As WebResponse = myRequest.GetResponse()  
    'Get a readable stream from the server.   
    Dim sr As Stream = myResponse.GetResponseStream()  
  
    Dim i As Integer      
    'Read from the stream and write any data to the console.  
    bytesread = sr.Read(myBuffer, 0, length)  
    While bytesread > 0  
        For i = 0 To bytesread - 1  
            Console.Write("{0}", myBuffer(i))  
        Next i  
        Console.WriteLine()  
        bytesread = sr.Read(myBuffer, 0, length)  
    End While  
    sr.Close()  
    myResponse.Close()  
Catch webExcp As WebException  
    ' If you reach this point, an exception has been caught.  
    Console.WriteLine("A WebException has been caught.")  
    ' Write out the WebException message.  
    Console.WriteLine(webExcp.ToString())  
    ' Get the WebException status code.  
    Dim status As WebExceptionStatus = webExcp.Status  
    ' If status is WebExceptionStatus.ProtocolError,   
    '   there has been a protocol error and a WebResponse   
    '   should exist. Display the protocol error.  
    If status = WebExceptionStatus.ProtocolError Then  
        Console.Write("The server returned protocol error ")  
        ' Get HttpWebResponse so that you can check the HTTP status code.  
        Dim httpResponse As HttpWebResponse = _  
           CType(webExcp.Response, HttpWebResponse)  
        Console.WriteLine(CInt(httpResponse.StatusCode).ToString() & _  
           " - " & httpResponse.StatusCode.ToString())  
    End If  
Catch e As Exception  
    ' Code to catch other exceptions goes here.  
End Try  
```  
  
 <span data-ttu-id="0d80c-148"><xref:System.Net.Sockets.Socket> 클래스를 사용하는 응용 프로그램은 Windows 소켓에서 오류가 발생할 경우 <xref:System.Net.Sockets.SocketException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-148">Applications that use the <xref:System.Net.Sockets.Socket> class throw <xref:System.Net.Sockets.SocketException> when errors occur on the Windows socket.</span></span> <span data-ttu-id="0d80c-149"><xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> 및 <xref:System.Net.Sockets.UdpClient> 클래스는 **Socket** 클래스의 맨 위에 빌드되고 **SocketExceptions**도 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-149">The <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes are built on top of the **Socket** class and throw **SocketExceptions** as well.</span></span>  
  
 <span data-ttu-id="0d80c-150">**SocketException**이 throw되면 **SocketException** 클래스는 마지막으로 발생한 운영 체제 소켓 오류로 <xref:System.Net.Sockets.SocketException.ErrorCode%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d80c-150">When a **SocketException** is thrown, the **SocketException** class sets the <xref:System.Net.Sockets.SocketException.ErrorCode%2A> property to the last operating system socket error that occurred.</span></span> <span data-ttu-id="0d80c-151">소켓 오류 코드에 대한 자세한 내용은 MSDN에서 Winsock 2.0 API 오류 코드 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d80c-151">For more information about socket error codes, see the Winsock 2.0 API error code documentation in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d80c-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d80c-152">See Also</span></span>  
 [<span data-ttu-id="0d80c-153">예외 처리 기본 사항</span><span class="sxs-lookup"><span data-stu-id="0d80c-153">Exception Handling Fundamentals</span></span>](../../../docs/standard/exceptions/exception-handling-fundamentals.md)  
 [<span data-ttu-id="0d80c-154">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="0d80c-154">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
