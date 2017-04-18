---
title: "비동기 요청 수행 | Microsoft Docs"
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
  - "인터넷, 비동기 액세스"
  - "네트워킹"
  - "비동기 요청, 인터넷 리소스"
  - "네트워크 리소스"
  - "WebRequest 클래스, 비동기 액세스"
ms.assetid: 735d3fce-f80c-437f-b02c-5c47f5739674
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 비동기 요청 수행
<xref:System.Net> 클래스 비동기 액세스 인터넷 리소스에 대 한.NET Framework 표준 비동기 프로그래밍 모델을 사용 합니다.  <xref:System.Net.WebRequest.BeginGetResponse%2A> 및 <xref:System.Net.WebRequest.EndGetResponse%2A> 메서드는 <xref:System.Net.WebRequest> 클래스 시작 및 인터넷 리소스에 대 한 비동기 요청을 완료 합니다.  
  
> [!NOTE]
>  동기를 사용 하 여 비동기 콜백 메서드는 심각한 성능 저하를 발생할 수 있습니다를 호출 합니다.  인터넷 요청에 대  **WebRequest** 및 해당 하위 항목을 사용 해야 <xref:System.IO.Stream.BeginRead%2A?displayProperty=fullName> 에서 반환 된 스트림을 읽을 수 있는 <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=fullName> 메서드.  
  
 다음 코드 예제에서는 비동기 호출을 사용 하는  **WebRequest** 클래스입니다.  샘플 명령줄에서 URI를 사용 하 고 리소스의 URI 요청 인터넷에서 수신 되 면 다음 데이터를 콘솔에 인쇄 하는 콘솔 프로그램입니다.  
  
 프로그램 자체 사용 하기 위해 두 개의 클래스 정의  **RequestState** 비동기 호출 간에 데이터를 전달 하는 클래스와  **ClientGetAsync** 비동기 요청을 인터넷 리소스를 구현 하는 클래스입니다.  
  
 **RequestState** 클래스 요청을 처리 하는 비동기 메서드 호출을 통해 요청의 상태를 유지 합니다.  포함  **WebRequest** 및 <xref:System.IO.Stream> 인스턴스가 현재 요청 수와 받은 응답, 현재 인터넷 리소스에서 받은 데이터를 포함 하는 버퍼에서에서 스트림에 포함 하는 <xref:System.Text.StringBuilder> 는 전체 응답을 포함.  A  **RequestState**로 전달 되는  *상태* 매개 변수 경우는 <xref:System.AsyncCallback> 메서드 등록 되어  **WebRequest.BeginGetResponse**.  
  
 **ClientGetAsync** 클래스는 비동기 요청을 인터넷 리소스를 구현 하 고 응답 결과 콘솔에 씁니다.  이 메서드와 속성에는 다음 목록에 포함 됩니다.  
  
-   `allDone` 속성의 인스턴스를 포함 된 <xref:System.Threading.ManualResetEvent> 요청 완료 신호를 전달 하는 클래스.  
  
-   `Main()` 메서드는 명령줄을 읽고 지정 된 인터넷 리소스에 대 한 요청을 시작 합니다.  만든는  **WebRequest**`wreq` 및  **RequestState**`rs`, 호출  **BeginGetResponse** 요청과 다음 호출 처리를 시작 하는 `allDone.WaitOne()`메서드 콜백이 완료 될 때까지 응용 프로그램을 종료할 수 있도록 합니다.    인터넷 리소스에서 응답을 읽은 다음 `Main()` 콘솔 및 응용 프로그램 끝에 씁니다.  
  
-   `showusage()` 메서드는 콘솔에서 예제 명령줄을 기록 합니다.  호출 `Main()` 없는 URI 명령줄에 제공 된 경우.  
  
-   `RespCallBack()` 메서드는 인터넷 요청에 대 한 비동기 콜백 메서드를 구현 합니다.  이  **WebResponse** 인터넷 리소스에서 응답을 포함 하는 인스턴스 응답 스트림을 가져옵니다 하 고 스트림에서 데이터를 비동기적으로 읽기 시작 합니다.  
  
-   `ReadCallBack()` 메서드는 응답 스트림의 읽을 비동기 콜백 메서드를 구현 합니다.  에 인터넷 리소스에서 받은 데이터를 전송는  **ResponseData** 속성에는  **RequestState** 인스턴스가 다른 비동기 읽기 응답 스트림을 더 많은 데이터가 반환 될 때까지 시작 하 고.  모든 데이터를 읽기 후에 `ReadCallBack()` 응답 스트림을 닫고 호출을 `allDone.Set()` 에 전체 응답을 표시 하려면 메서드  **ResponseData**.  
  
    > [!NOTE]
    >  모든 네트워크 스트림이 닫혀있는 것이 중요 합니다.  각 요청 및 응답 스트림을 닫지 않으면 응용 프로그램 서버에 연결에서 실행 하 고 추가 요청을 처리할 수 없습니다.  
  
```csharp  
using System;  
using System.Net;  
using System.Threading;  
using System.Text;  
using System.IO;  
  
// The RequestState class passes data across async calls.  
public class RequestState  
{  
   const int BufferSize = 1024;  
   public StringBuilder RequestData;  
   public byte[] BufferRead;  
   public WebRequest Request;  
   public Stream ResponseStream;  
   // Create Decoder for appropriate enconding type.  
   public Decoder StreamDecode = Encoding.UTF8.GetDecoder();  
  
   public RequestState()  
   {  
      BufferRead = new byte[BufferSize];  
      RequestData = new StringBuilder(String.Empty);  
      Request = null;  
      ResponseStream = null;  
   }       
}  
  
// ClientGetAsync issues the async request.  
class ClientGetAsync   
{  
   public static ManualResetEvent allDone = new ManualResetEvent(false);  
   const int BUFFER_SIZE = 1024;  
  
   public static void Main(string[] args)   
   {  
      if (args.Length < 1)   
      {  
         showusage();  
         return;  
      }  
  
      // Get the URI from the command line.  
      Uri httpSite = new Uri(args[0]);  
  
      // Create the request object.  
      WebRequest wreq = WebRequest.Create(httpSite);  
  
      // Create the state object.  
      RequestState rs = new RequestState();  
  
      // Put the request into the state object so it can be passed around.  
      rs.Request = wreq;  
  
      // Issue the async request.  
      IAsyncResult r = (IAsyncResult) wreq.BeginGetResponse(  
         new AsyncCallback(RespCallback), rs);  
  
      // Wait until the ManualResetEvent is set so that the application   
      // does not exit until after the callback is called.  
      allDone.WaitOne();  
  
      Console.WriteLine(rs.RequestData.ToString());  
   }  
  
   public static void showusage() {  
      Console.WriteLine("Attempts to GET a URL");  
      Console.WriteLine("\r\nUsage:");  
      Console.WriteLine("   ClientGetAsync URL");  
      Console.WriteLine("   Example:");  
      Console.WriteLine("      ClientGetAsync http://www.contoso.com/");  
   }  
  
   private static void RespCallback(IAsyncResult ar)  
   {  
      // Get the RequestState object from the async result.  
      RequestState rs = (RequestState) ar.AsyncState;  
  
      // Get the WebRequest from RequestState.  
      WebRequest req = rs.Request;  
  
      // Call EndGetResponse, which produces the WebResponse object  
      //  that came from the request issued above.  
      WebResponse resp = req.EndGetResponse(ar);           
  
      //  Start reading data from the response stream.  
      Stream ResponseStream = resp.GetResponseStream();  
  
      // Store the response stream in RequestState to read   
      // the stream asynchronously.  
      rs.ResponseStream = ResponseStream;  
  
      //  Pass rs.BufferRead to BeginRead. Read data into rs.BufferRead  
      IAsyncResult iarRead = ResponseStream.BeginRead(rs.BufferRead, 0,   
         BUFFER_SIZE, new AsyncCallback(ReadCallBack), rs);   
   }  
  
   private static void ReadCallBack(IAsyncResult asyncResult)  
   {  
      // Get the RequestState object from AsyncResult.  
      RequestState rs = (RequestState)asyncResult.AsyncState;  
  
      // Retrieve the ResponseStream that was set in RespCallback.   
      Stream responseStream = rs.ResponseStream;  
  
      // Read rs.BufferRead to verify that it contains data.   
      int read = responseStream.EndRead( asyncResult );  
      if (read > 0)  
      {  
         // Prepare a Char array buffer for converting to Unicode.  
         Char[] charBuffer = new Char[BUFFER_SIZE];  
  
         // Convert byte stream to Char array and then to String.  
         // len contains the number of characters converted to Unicode.  
      int len =   
         rs.StreamDecode.GetChars(rs.BufferRead, 0, read, charBuffer, 0);  
  
         String str = new String(charBuffer, 0, len);  
  
         // Append the recently read data to the RequestData stringbuilder  
         // object contained in RequestState.  
         rs.RequestData.Append(  
            Encoding.ASCII.GetString(rs.BufferRead, 0, read));           
  
         // Continue reading data until   
         // responseStream.EndRead returns –1.  
         IAsyncResult ar = responseStream.BeginRead(   
            rs.BufferRead, 0, BUFFER_SIZE,   
            new AsyncCallback(ReadCallBack), rs);  
      }  
      else  
      {  
         if(rs.RequestData.Length>0)  
         {  
            //  Display data to the console.  
            string strContent;                    
            strContent = rs.RequestData.ToString();  
         }  
         // Close down the response stream.  
         responseStream.Close();           
         // Set the ManualResetEvent so the main thread can exit.  
         allDone.Set();                             
      }  
      return;  
   }      
}  
```  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Threading  
Imports System.Text  
Imports System.IO  
  
' The RequestState class passes data across async calls.  
Public Class RequestState  
  
      Public RequestData As New StringBuilder("")  
      Public BufferRead(1024) As Byte  
      Public Request As HttpWebRequest  
      Public ResponseStream As Stream  
      ' Create Decoder for appropriate encoding type.  
      Public StreamDecode As Decoder = Encoding.UTF8.GetDecoder()  
  
      Public Sub New  
         Request = Nothing  
         ResponseStream = Nothing  
      End Sub  
End Class  
  
' ClientGetAsync issues the async request.  
Class ClientGetAsync  
   Shared allDone As New ManualResetEvent(False)  
      Const BUFFER_SIZE As Integer = 1024  
  
    Shared Sub Main()  
        Dim Args As String() = Environment.GetCommandLineArgs()  
  
        If Args.Length < 2 Then  
            ShowUsage()  
            Return  
        End If  
  
      ' Get the URI from the command line.  
        Dim HttpSite As Uri = New Uri(Args(1))  
  
      ' Create the request object.  
        Dim wreq As HttpWebRequest = _  
           CType(WebRequest.Create(HttpSite), HttpWebRequest)  
  
      ' Create the state object.  
      Dim rs As RequestState = New RequestState()  
  
      ' Put the request into the state so it can be passed around.  
      rs.Request = wreq  
  
      ' Issue the async request.  
        Dim r As IAsyncResult = _  
           CType(wreq.BeginGetResponse( _  
           New AsyncCallback(AddressOf RespCallback), rs), IAsyncResult)  
  
      ' Wait until the ManualResetEvent is set so that the application  
      ' does not exit until after the callback is called.  
        allDone.WaitOne()  
    End Sub  
  
    Shared Sub ShowUsage()  
        Console.WriteLine("Attempts to GET a URI")  
        Console.WriteLine()  
        Console.WriteLine("Usage:")  
        Console.WriteLine("ClientGetAsync URI")  
        Console.WriteLine("Examples:")  
        Console.WriteLine("ClientGetAsync http://www.contoso.com/")  
    End Sub  
  
    Shared Sub RespCallback(ar As IAsyncResult)  
       ' Get the RequestState object from the async result.  
       Dim rs As RequestState = CType(ar.AsyncState, RequestState)  
  
       ' Get the HttpWebRequest from RequestState.  
       Dim req As HttpWebRequest= rs.Request  
  
       ' Call EndGetResponse, which returns the HttpWebResponse object  
       ' that came from the request issued above.  
       Dim resp As HttpWebResponse = _  
           CType(req.EndGetResponse(ar), HttpWebResponse)  
  
       ' Start reading data from the respons stream.  
       Dim ResponseStream As Stream = resp.GetResponseStream()  
  
       ' Store the reponse stream in RequestState to read  
       ' the stream asynchronously.  
       rs.ResponseStream = ResponseStream  
  
       ' Pass rs.BufferRead to BeginRead. Read data into rs.BufferRead.  
       Dim iarRead As IAsyncResult = _  
          ResponseStream.BeginRead(rs.BufferRead, 0, BUFFER_SIZE, _  
          New AsyncCallback(AddressOf ReadCallBack), rs)  
    End Sub  
  
   Shared Sub ReadCallBack(asyncResult As IAsyncResult)  
      ' Get the RequestState object from the AsyncResult.  
      Dim rs As RequestState = CType(asyncResult.AsyncState, RequestState)  
  
      ' Retrieve the ResponseStream that was set in RespCallback.  
      Dim responseStream As Stream = rs.ResponseStream  
  
      ' Read rs.BufferRead to verify that it contains data.  
      Dim read As Integer = responseStream.EndRead( asyncResult )  
      If read > 0 Then  
         ' Prepare a Char array buffer for converting to Unicode.  
         Dim charBuffer(1024) As Char  
  
         ' Convert byte stream to Char array and then String.  
         ' len contains the number of characters converted to Unicode.  
         Dim len As Integer = _  
           rs.StreamDecode.GetChars(rs.BufferRead, 0, read, charBuffer, 0)  
         Dim str As String = new String(charBuffer, 0, len)      
  
         ' Append the recently read data to the RequestData stringbuilder   
         ' object contained in RequestState.  
         rs.RequestData.Append( _  
            Encoding.ASCII.GetString(rs.BufferRead, 0, read))  
  
         ' Continue reading data until responseStream.EndRead  
         ' returns –1.  
         Dim ar As IAsyncResult = _  
            responseStream.BeginRead(rs.BufferRead, 0, BUFFER_SIZE, _  
            New AsyncCallback(AddressOf ReadCallBack), rs)  
      Else  
          If rs.RequestData.Length > 1 Then  
            ' Display data to the console.  
            Dim strContent As String  
            strContent = rs.RequestData.ToString()  
            Console.WriteLine(strContent)  
         End If  
  
         ' Close down the response stream.  
         responseStream.Close()  
  
         ' Set the ManualResetEvent so the main thread can exit.  
         allDone.Set()  
      End If  
  
      Return  
   End Sub  
End Class  
```  
  
## 참고 항목  
 [데이터 요청](../../../docs/framework/network-programming/requesting-data.md)