---
title: "오류 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "인터넷, WebRequest 및 WebResponse 클래스 예외"
  - "Status 속성"
  - "WebExceptions 클래스, WebExceptions 클래스 정보"
  - "Timeout 열거형 멤버"
  - "ConnectFailure 열거형 멤버"
  - "TrustFailure 열거형 멤버"
  - "WebRequest 클래스, 예외"
  - "인터넷을 통해 데이터 요청, 오류 처리"
  - "Success 열거형 멤버"
  - "데이터 수신, 오류"
  - "ProtocolError 열거형 멤버"
  - "인터넷 리소스 다운로드, 오류 처리"
  - "WebResponse 클래스, 예외"
  - "SendFailure 열거형 멤버"
  - "오류[.NET Framework], WebRequest 및 WebResponse 클래스 예외"
  - "데이터 보내기, 오류"
  - "인터넷 요청에 대한 응답, 오류 처리"
  - "NameResolutionFailure 열거형 멤버"
  - "KeepAliveFailure 열거형 멤버"
  - "네트워크 리소스, WebRequest 및 WebResponse 클래스 예외"
  - "RequestCanceled 열거형 멤버"
  - "ReceiveFailure 열거형 멤버"
  - "ServerProtocolViolation 열거형 멤버"
  - "ConnectionClosed 열거형 멤버"
  - "SecureChannelFailure 열거형 멤버"
ms.assetid: 657141cd-5cf5-4fdb-a4b2-4c040eba84b5
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 오류 처리
<xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스 모두 시스템 예외를 throw 합니다 \(같은 <xref:System.ArgumentException>\) 및 웹 관련 예외 \(있는  [WebExceptions](frlrfsystemnetwebexceptionclasstopic) throw는 <xref:System.Net.WebRequest.GetResponse%2A> 메서드\).  
  
 각  **WebException** 포함는 <xref:System.Net.WebException.Status%2A> 값을 포함 하는 속성의 <xref:System.Net.WebExceptionStatus> 열거형입니다.  검토할 수는  **상태** 속성에서 발생 한 오류를 확인 하 고 오류를 해결 하려면 적절 한 단계를 수행 합니다.  
  
 다음 표에서 가능한 값은  **상태** 속성.  
  
|상태|설명|  
|--------|--------|  
|ConnectFailure|전송 수준에서 원격 서비스를 연결할 수 없습니다.|  
|ConnectionClosed|연결이 중간에 끊어졌습니다.|  
|KeepAliveFailure|서버 keep\-alive 헤더 집합에 대 한 연결을 끊었습니다.|  
|NameResolutionFailure|이름 서비스가 호스트 이름을 확인할 수 없습니다.|  
|ProtocolError|서버에서 받은 응답 완료 했지만 프로토콜 수준의 오류가 표시 합니다.|  
|ReceiveFailure|원격 서버에서 전체 응답을 받지 못했습니다.|  
|RequestCanceled|요청이 취소 되었습니다.|  
|SecureChannelFailure|보안 채널 연결에서 오류가 있습니다.|  
|SendFailure|원격 서버에 전체 요청을 보낼 수 없습니다.|  
|ServerProtocolViolation|서버 응답이 유효한 HTTP 응답이 아닙니다.|  
|성공|오류가 발생하지 않았습니다.|  
|제한 시|설정에 대 한 요청이 제한 시간 내 응답을 받았습니다.|  
|TrustFailure|서버 인증의 유효성을 검사할 수 없습니다.|  
|MessageLengthLimitExceeded|서버에 요청을 보내거나 서버에서 응답을 받을 때 지정된 제한 시간을 초과했다는 메시지를 받았습니다.|  
|보류 중|내부 비동기 요청이 보류 중입니다.|  
|PipelineFailure|이 값이.NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.|  
|ProxyNameResolutionFailure|이름 확인자 서비스가 해당 프록시 호스트 이름을 확인하지 못했습니다.|  
|UnknownError|알 수 없는 유형의 예외가 발생했습니다.|  
  
 경우는  **상태** 속성인  **WebExceptionStatus.ProtocolError**a  **WebResponse** 서버의 응답이 들어 있는 사용할 수 있습니다.  이 응답 프로토콜 오류의 실제 원인을 확인할 수 있습니다.  
  
 다음 예제에서는 catch는  **WebException**.  
  
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
  
 사용 하는 응용 프로그램은 <xref:System.Net.Sockets.Socket> 클래스를 throw 하는  [SocketExceptions](frlrfsystemnetsocketssocketexceptionclasstopic) 오류가 발생할 때 Windows 소켓에.  [TCPClient](frlrfsystemnetsocketstcpclientclasstopic),  [TCPListener](frlrfsystemnetsocketstcplistenerclasstopic), 및  [UDPClient](frlrfsystemnetsocketsudpclientclasstopic) 클래스 위에 구축 되는  **소켓** 클래스 및 throw  **SocketExceptions** 도.  
  
 때는  **SocketException** throw 되는  **SocketException** 클래스 집합의 <xref:System.Net.Sockets.SocketException.ErrorCode%2A> 속성에는 마지막 운영 체제 소켓 오류 발생.  소켓 오류 코드에 대 한 자세한 내용은 MSDN에서 Winsock 2.0 API 오류 코드 설명서를 참조 하십시오.  
  
## 참고 항목  
 [예외 처리 기본 사항](../../../docs/standard/exceptions/exception-handling-fundamentals.md)   
 [데이터 요청](../../../docs/framework/network-programming/requesting-data.md)