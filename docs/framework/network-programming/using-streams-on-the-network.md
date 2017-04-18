---
title: "네트워크에서 스트림 사용 | Microsoft Docs"
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
  - "인터넷에서 데이터 요청, 스트림"
  - "네트워킹"
  - "인터넷 요청에 응답, 스트림"
  - "네트워크 리소스, 스트림 기능"
  - "데이터 받기, 스트림 기능"
  - "네트워크 리소스"
  - "데이터 보내기, 스트림 기능"
  - "인터넷 리소스 다운로드, 스트림"
  - "스트림, 기능"
  - "인터넷, 스트림"
  - "스트림"
ms.assetid: 02b05fba-7235-45ce-94e5-060436ee0875
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 네트워크에서 스트림 사용
네트워크 리소스는.NET Framework 스트림으로 표현 됩니다.  .NET Framework 스트림 일반적으로 취급 하 여, 다음과 같은 기능을 제공 합니다.  
  
-   웹 데이터를 송수신 하는 일반적인 방법입니다.  어떤 실제 내용을 파일\-HTML, XML 또는 다른\-응용 프로그램을 사용 <xref:System.IO.Stream.Write%2A?displayProperty=fullName> 및 <xref:System.IO.Stream.Read%2A?displayProperty=fullName> 데이터를 주고받을 수 있습니다.  
  
-   스트림을 통해.NET Framework의 호환성입니다.  스트림 전체를 처리 하는 풍부한 인프라에 있는.NET Framework 사용 합니다.  예를 들어, XML 데이터를 읽는 응용 프로그램을 수정할 수는 <xref:System.IO.FileStream> 에서 데이터를 읽을 수는 <xref:System.Net.Sockets.NetworkStream> 대신으로 스트림을 초기화 하는 몇 줄의 코드로 변경.  주요 차이점 사이  **NetworkStream** 클래스와 다른 스트림 되는  **NetworkStream** 를 찾을 수 없기는 <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> 속성은 항상 반환  **false**, 및 <xref:System.Net.Sockets.NetworkStream.Seek%2A> 및 <xref:System.Net.Sockets.NetworkStream.Position%2A> 메서드가 throw는 <xref:System.NotSupportedException>.  
  
-   이 데이터의 처리에 도착합니다.  강제로 응용 프로그램을 다운로드 하는 전체 데이터 집합에 대 한 대기 하지 않고 네트워크에서 들어오면 스트림 데이터 액세스를 제공 합니다.  
  
 <xref:System.Net.Sockets> 네임 스페이스를 포함 한  **NetworkStream** 구현 하는 클래스는 <xref:System.IO.Stream> 클래스 네트워크 리소스를 사용할.  클래스에 <xref:System.Net.Sockets> 네임 스페이스 사용을  **NetworkStream** 스트림을 나타내는 클래스.  
  
 반환 된 스트림을 사용 하 여 네트워크에 데이터를 보내기 위해 호출 <xref:System.Net.WebRequest.GetRequestStream%2A> 에 <xref:System.Net.WebRequest>.  **WebRequest** ; 서버에 보낼 요청 헤더 호출 하 여 네트워크 리소스에 데이터를 보낼 수 있습니다 다음은 <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A>, 또는 <xref:System.IO.Stream.Write%2A> 메서드는 반환 된 스트림.  HTTP와 같은 일부 프로토콜에서는 데이터를 보내기 전에 프로토콜 관련 속성을 설정 하려면 필요할 수 있습니다.  다음 코드 예제에서는 데이터를 보내는 HTTP 관련 속성을 설정 하는 방법을 보여 줍니다.  이 가정 변수 `sendData` 보낼 데이터를 포함 하 고 변수 `sendLength` 보낼 데이터의 바이트 수입니다.  
  
```csharp  
HttpWebRequest request =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
request.Method = "POST";  
request.ContentLength = sendLength;  
try  
{  
   Stream sendStream = request.GetRequestStream();  
   sendStream.Write(sendData,0,sendLength);  
   sendStream.Close();  
}  
catch  
{  
   // Handle errors . . .  
}  
  
```  
  
```vb  
Dim request As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
request.Method = "POST"  
request.ContentLength = sendLength  
Try  
   Dim sendStream As Stream = request.GetRequestStream()  
   sendStream.Write(sendData, 0, sendLength)  
   sendStream.Close()  
Catch  
   ' Handle errors . . .  
End Try  
```  
  
 네트워크에서 데이터를 받으려면 호출 <xref:System.Net.WebResponse.GetResponseStream%2A> 에 <xref:System.Net.WebResponse>.  다음 데이터 네트워크 리소스에서 호출 하 여 읽을 수 있는 <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A>, 또는 <xref:System.IO.Stream.Read%2A> 메서드는 반환 된 스트림.  
  
 네트워크 리소스에서 스트림을 사용 하는 경우 다음 사항에 유의 하십시오.  
  
-   **CanSeek** 속성은 항상 반환  **false** 때문에  **NetworkStream** 클래스 스트림 내의 위치를 변경할 수 없습니다.  **검색** 및  **위치** 메서드가 throw 한  **NotSupportedException**.  
  
-   사용 하는 경우  **WebRequest** 및  **WebResponse**, 스트림 인스턴스를 호출 하 여 만든  **GetResponseStream** 읽기 전용 이며 스트림 인스턴스를 호출 하 여 만든  **GetRequestStream** 쓰기 전용입니다.  
  
-   사용 된 <xref:System.IO.StreamReader> 인코딩을 간편 하 게 하는 클래스입니다.  다음 코드 예제에서는 사용 하는  **StreamReader** ASCII로 인코딩된 스트림에서 읽을 수 있는  **WebResponse**  \(이 예제에서는 요청을 만드는 표시 되지 않습니다\).  
  
-   호출을  **GetResponse** 네트워크 리소스를 사용할 수 없는 경우를 차단할 수 있습니다.  비동기 요청을 사용 하 여 고려해 야 할의 <xref:System.Net.WebRequest.BeginGetResponse%2A> 및 <xref:System.Net.WebRequest.EndGetResponse%2A> 방법.  
  
-   호출을  **GetRequestStream** 서버에 연결을 만드는 동안 차단할 수 있습니다.  스트림에 대 한 비동기 요청을 사용 하 여 고려해 야 할의 <xref:System.Net.WebRequest.BeginGetRequestStream%2A> 및 <xref:System.Net.WebRequest.EndGetRequestStream%2A> 방법.  
  
```csharp  
// Create a response object.  
WebResponse response = request.GetResponse();  
// Get a readable stream from the server.  
StreamReader sr =   
   new StreamReader(response.GetResponseStream(), Encoding.ASCII);  
// Use the stream. Remember when you are through with the stream to close it.  
sr.Close();  
```  
  
```vb  
' Create a response object.  
Dim response As WebResponse = request.GetResponse()  
' Get a readable stream from the server.  
Dim sr As _   
   New StreamReader(response.GetResponseStream(), Encoding.ASCII)  
' Use the stream. Remember when you are through with the stream to close it.  
sr.Close()  
```  
  
## 참고 항목  
 [방법: WebRequest 클래스를 사용하여 데이터 요청](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)   
 [데이터 요청](../../../docs/framework/network-programming/requesting-data.md)