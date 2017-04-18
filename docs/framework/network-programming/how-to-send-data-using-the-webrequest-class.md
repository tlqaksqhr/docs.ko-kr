---
title: "방법: WebRequest 클래스를 사용하여 데이터 보내기 | Microsoft Docs"
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
  - "WebRequest 클래스, 호스트로 데이터 보내기"
  - "호스트로 데이터 보내기, WebRequest 클래스 사용"
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 방법: WebRequest 클래스를 사용하여 데이터 보내기
서버에 데이터를 보내는 데 필요한 단계를 다음 절차를 따르십시오.  이 절차는 웹 페이지에 데이터를 게시할 수 주로 사용 됩니다.  
  
### 호스트 서버에 데이터를 보낼 수  
  
1.  만들기는 <xref:System.Net.WebRequest> 인스턴스를 호출 하 여 <xref:System.Net.WebRequest.Create%2A> 예를 들어, 데이터를 받아들이는 리소스 스크립트 또는 ASP.NET 페이지의 URI를 사용 합니다.  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
  
    ```  
  
    > [!NOTE]
    >  .NET Framework 파생 된 프로토콜별 클래스가 제공  **WebRequest** 및  **WebResponse** 로 시작 하는 Uri에 대 한 "http:", "https:", "ftp:", 및 "파일:".  다른 프로토콜을 사용 하 여 리소스에 액세스 하려면 프로토콜 관련 클래스를 파생 구현  **WebRequest** 및  **WebResponse**.  자세한 내용은 [플러그형 프로토콜 프로그래밍](../../../docs/framework/network-programming/programming-pluggable-protocols.md)을 참조하십시오.  
  
2.  설정에 필요한 모든 속성 값은  **WebRequest**.  예를 들어, 인증을 설정 하려면 설정의  **자격 증명** 인스턴스에 속성의 <xref:System.Net.NetworkCredential> 클래스.  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
  
    ```  
  
     대부분의 경우에  **WebRequest** 인스턴스를 자체 데이터를 보낼 수 있는 충분 한입니다.  하지만 프로토콜 관련 속성을 설정 하는 경우를 캐스팅 해야는  **WebRequest** 프로토콜 관련 형식입니다.  예를 들어, 액세스 HTTP 관련 속성에 <xref:System.Net.HttpWebRequest>, 캐스팅는  **WebRequest** 에  **HttpWebRequest**  참조.  다음 코드 예제에서는 HTTP 관련 설정 하는 방법을 보여 줍니다. <xref:System.Net.HttpWebRequest.UserAgent%2A> 속성.  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  같은 HTTP 요청과 함께 보낼 데이터를 허용 하는 프로토콜 메서드를 지정 합니다.  **POST** 메서드.  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  설정 된  **ContentLength** 속성.  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  설정 된  **ContentType** 속성에 적절 한 값입니다.  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  보류를 호출 하 여 데이터 요청 스트림 가져오기는 <xref:System.Net.WebRequest.GetRequestStream%2A> 메서드.  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  데이터를 쓸는 <xref:System.IO.Stream> 이 메서드에서 반환 하는 개체입니다.  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  호출 하 여 요청 스트림을 닫아야는  **Stream.Close** 메서드.  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. 호출 하 여 서버에 요청을 보낼 <xref:System.Net.WebRequest.GetResponse%2A>.  이 메서드는 서버의 응답을 포함 하는 개체를 반환 합니다.  반환 되는 <xref:System.Net.WebResponse> 은 요청 URI의 체계에서 개체의 형식을 결정 합니다.  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
  
    ```  
  
    > [!NOTE]
    >  마친 후에 <xref:System.Net.WebResponse> 개체를 닫아야이 호출 하 여이 <xref:System.Net.WebResponse.Close%2A> 메서드.  응답 스트림을 응답 개체 로부터 있습니다 또는 스트림 호출 하 여 닫을 수 있습니다는 <xref:System.IO.Stream.Close%2A?displayProperty=fullName> 메서드.  응답 또는 스트림을 닫지 않으면 응용 프로그램 서버에 연결에서 실행 하 고 추가 요청을 처리할 수 없게 수 있습니다.  
  
10. 속성에 액세스할 수 있습니다는  **WebResponse** 또는 캐스팅는  **WebResponse** 프로토콜 특정 인스턴스에 프로토콜 관련 속성을 읽을 수 있습니다.  예를 들어, 액세스 HTTP 관련 속성에 <xref:System.Net.HttpWebResponse>, 캐스팅는  **WebResponse** 에  **HttpWebResponse** 참조.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. 호출 서버에서 보낸 응답 데이터를 포함 하는 스트림을 가져올 수 있는 <xref:System.Net.WebResponse.GetResponseStream%2A> 메서드는  **WebResponse**.  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. 응답에서 데이터를 읽은 후에 사용 하 여 응답 스트림을 닫아야 합니다의  **Stream.Close** 메서드 또는 닫기 사용 하 여 응답을  **WebResponse.Close** 메서드.  호출할 필요가 없는  **닫기** 메서드는 응답 스트림 및  **WebResponse**, 있지만 이렇게 하면 유해한 이므로 아닙니다.  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
  
    ```  
  
## 예제  
  
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
  
## 참고 항목  
 [인터넷 요청 만들기](../../../docs/framework/network-programming/creating-internet-requests.md)   
 [네트워크에서 스트림 사용](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [프록시를 통해 인터넷 액세스](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [데이터 요청](../../../docs/framework/network-programming/requesting-data.md)   
 [방법: WebRequest 클래스를 사용하여 데이터 요청](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)