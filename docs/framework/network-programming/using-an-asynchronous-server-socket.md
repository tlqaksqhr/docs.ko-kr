---
title: "비동기 서버 소켓 사용 | Microsoft Docs"
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
  - "응용 프로그램 프로토콜, 소켓"
  - "데이터 보내기, 소켓"
  - "소켓 클래스, 비동기 서버 소켓"
  - "데이터 요청, 소켓"
  - "소켓, 비동기 서버 소켓"
  - "인터넷에서 데이터 요청, 소켓"
  - "서버 소켓"
  - "데이터 받기, 소켓"
  - "비동기 서버 소켓"
  - "프로토콜, 소켓"
  - "인터넷, 소켓"
ms.assetid: 813489a9-3efd-41b6-a33f-371d55397676
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 비동기 서버 소켓 사용
비동기 서버 소켓 네트워크 서비스 요청을 처리 하는.NET Framework 비동기 프로그래밍 모델을 사용 합니다.  <xref:System.Net.Sockets.Socket> 클래스 뒤에 표준.NET Framework 비동기 명명 패턴입니다. 예를 들어,는 동기 <xref:System.Net.Sockets.Socket.Accept%2A> 메서드는 비동기 해당 <xref:System.Net.Sockets.Socket.BeginAccept%2A> 및 <xref:System.Net.Sockets.Socket.EndAccept%2A> 방법.  
  
 데이터를 받는 종료 콜백 메서드, 연결 요청을 처리 하 고 네트워크에서 데이터를 받을 콜백 메서드는 네트워크에서 연결 요청 수락을 시작 하는 메서드는 비동기 서버 소켓을 해야 합니다.  이러한 모든 방법을 설명 하는이 섹션에 추가 합니다.  
  
 메서드는 네트워크에서 연결 요청을 수락 하려면 다음 예제에서 `StartListening` 초기화는  **소켓** 다음 사용 하는  **BeginAccept** 메서드를 새 연결을 받아들이지 시작 합니다.  소켓에서 새 연결 요청을 받으면 accept 콜백 메서드가 호출 됩니다.  담당자는  **소켓** 인스턴스에 연결 하는 처리를 처리  **소켓** 요청을 처리 하는 스레드를 해제 합니다.  Accept 콜백 메서드를 구현 된 <xref:System.AsyncCallback> 위임. void를 반환 하 고 형식의 단일 매개 변수 사용 <xref:System.IAsyncResult>.  다음 예제는 accept 콜백 메서드의 셸입니다.  
  
```vb  
Sub acceptCallback(ar As IAsyncResult)  
    ' Add the callback code here.  
End Sub 'acceptCallback  
```  
  
```csharp  
void acceptCallback( IAsyncResult ar) {  
    // Add the callback code here.  
}  
```  
  
 **BeginAccept** 메서드에서 사용 하는 두 개의 매개 변수는  **연속화** accept 콜백 메서드 및 상태 정보를 콜백 메서드에 전달 하는 데 사용 되는 개체를 가리키는 대리자입니다.  다음 예제에서는 수신 하는  **소켓** 콜백 메서드를 통해 전달 되는  *상태* 매개 변수.  이 예제는  **연속화** 대리자 및 네트워크에서 연결을 받아들이지 시작 합니다.  
  
```vb  
listener.BeginAccept( _  
    New AsyncCallback(SocketListener.acceptCallback),_  
    listener)  
```  
  
```csharp  
listener.BeginAccept(  
    new AsyncCallback(SocketListener.acceptCallback),   
    listener);  
```  
  
 비동기 소켓 들어오는 연결을 처리 하는 시스템 스레드 풀에서 스레드를 사용 합니다.  스레드 연결을 허용 하기 위해 담당, 들어오는 각 연결을 처리 하도록 다른 스레드를 사용 하 고 다른 스레드는 연결에서 데이터를 받기 위해 담당.  이 따라 스레드를 스레드 풀에서 할당 된 동일한 스레드 수 있습니다.  다음 예에서는 <xref:System.Threading.ManualResetEvent?displayProperty=fullName> 클래스 주 스레드의 실행을 일시 중지 하 고 실행을 계속할 경우 신호.  
  
 다음 예제에서는 로컬 컴퓨터에서 비동기 TCP\/IP 소켓을 생성 하 고 연결을 받아들이지 시작 하는 비동기 메서드를 보여 줍니다.  전역 있다고 가정  **스레드가** 라는 `allDone`, 멤버 라는 클래스의 메서드입니다 `SocketListener`, 및 콜백 메서드를 지정 합니다. `acceptCallback` 정의 됩니다.  
  
```vb  
Public Sub StartListening()  
    Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
    Dim localEP = New IPEndPoint(ipHostInfo.AddressList(0), 11000)  
  
    Console.WriteLine("Local address and port : {0}", localEP.ToString())  
  
    Dim listener As New Socket(localEP.Address.AddressFamily, _  
       SocketType.Stream, ProtocolType.Tcp)  
  
    Try  
        listener.Bind(localEP)  
        listener.Listen(10)  
  
        While True  
            allDone.Reset()  
  
            Console.WriteLine("Waiting for a connection...")  
            listener.BeginAccept(New _  
                AsyncCallback(SocketListener.acceptCallback), _  
                listener)  
  
            allDone.WaitOne()  
        End While  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
    Console.WriteLine("Closing the listener...")  
End Sub 'StartListening  
  
```  
  
```csharp  
public void StartListening() {  
    IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
    IPEndPoint localEP = new IPEndPoint(ipHostInfo.AddressList[0],11000);  
  
    Console.WriteLine("Local address and port : {0}",localEP.ToString());  
  
    Socket listener = new Socket( localEP.Address.AddressFamily,  
        SocketType.Stream, ProtocolType.Tcp );  
  
    try {  
        listener.Bind(localEP);  
        listener.Listen(10);  
  
        while (true) {  
            allDone.Reset();  
  
            Console.WriteLine("Waiting for a connection...");  
            listener.BeginAccept(  
                new AsyncCallback(SocketListener.acceptCallback),   
                listener );  
  
            allDone.WaitOne();  
        }  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
  
    Console.WriteLine( "Closing the listener...");  
}  
```  
  
 Accept 콜백 메서드 \(`acceptCallback` 앞의 예제에서\)의 데이터는 클라이언트에서 읽은 신호 주 응용 프로그램 스레드를 처리 하 고 클라이언트와의 연결을 설정 하 고 비동기 시작 하려면 담당 합니다.  다음 예제에서는 구현 하는 첫 번째 부분입니다의 `acceptCallback` 메서드.  메서드는이 부분의 신호를 주 응용 프로그램 스레드에 처리를 계속 및 클라이언트 연결 합니다.  전역 가정  **스레드가** 라는 `allDone`.  
  
```vb  
Public Sub acceptCallback(ar As IAsyncResult)  
    allDone.Set()  
  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Additional code to read data goes here.  
End Sub 'acceptCallback  
```  
  
```csharp  
public void acceptCallback(IAsyncResult ar) {  
    allDone.Set();  
  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Additional code to read data goes here.    
}  
```  
  
 클라이언트 소켓에서 데이터를 읽는 상태 개체는 비동기 호출 사이의 값을 전달 해야 합니다.  다음 예제에서는 원격 클라이언트로부터 문자열 수신 상태 개체를 구현 합니다.  클라이언트 소켓에서 데이터를 받는 데이터 버퍼에 대 한 필드를 포함 하는 <xref:System.Text.StringBuilder> 클라이언트에서 보낸 데이터 문자열을 만들기 위한.  상태 개체에 이들이 필드 배치 값을 클라이언트 소켓에서 데이터를 읽을 수 있는 여러 호출 간에 유지 될 수 있습니다.  
  
```vb  
Public Class StateObject  
    Public workSocket As Socket = Nothing  
    Public BufferSize As Integer = 1024  
    Public buffer(BufferSize) As Byte  
    Public sb As New StringBuilder()  
End Class 'StateObject  
```  
  
```csharp  
public class StateObject {  
    public Socket workSocket = null;  
    public const int BufferSize = 1024;  
    public byte[] buffer = new byte[BufferSize];  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 섹션의의 `acceptCallback` 클라이언트 소켓에서 데이터를 받기 시작 하는 메서드는 인스턴스를 먼저 초기화는 `StateObject` 클래스와 호출의 <xref:System.Net.Sockets.Socket.BeginReceive%2A> 메서드는 클라이언트 소켓에서 데이터를 비동기적으로 읽기 시작 합니다.  
  
 다음 예제는 완전 `acceptCallback` 메서드.  전역 있다고 가정  **스레드가** 라는 `allDone,` 는 `StateObject` 클래스를 정의 하 고는 `readCallback` 라는 클래스에 메서드를 정의 `SocketListener`.  
  
```vb  
Public Shared Sub acceptCallback(ar As IAsyncResult)  
    ' Get the socket that handles the client request.  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Signal the main thread to continue.  
    allDone.Set()  
  
    ' Create the state object.  
    Dim state As New StateObject()  
    state.workSocket = handler  
    handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
        AddressOf AsynchronousSocketListener.readCallback, state)  
End Sub 'acceptCallback  
  
```  
  
```csharp  
public static void acceptCallback(IAsyncResult ar) {  
    // Get the socket that handles the client request.  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Signal the main thread to continue.  
    allDone.Set();  
  
    // Create the state object.  
    StateObject state = new StateObject();  
    state.workSocket = handler;  
    handler.BeginReceive( state.buffer, 0, StateObject.BufferSize, 0,  
        new AsyncCallback(AsynchronousSocketListener.readCallback), state);  
}  
```  
  
 비동기 소켓 서버를 구현 해야 하는 마지막 메서드는 클라이언트에서 보낸 데이터를 반환 하는 읽기 콜백 메서드가입니다.  Accept 콜백 메서드를 다음과 같이 읽기 콜백 메서드입니다는  **연속화** 위임 합니다.  이 메서드는 클라이언트 소켓에서 하나 이상의 바이트를 데이터 버퍼로 읽습니다 고 다음 호출을  **BeginReceive** 메서드는 클라이언트에서 보낸 데이터를 다시 때까지 완료 됩니다.  전체 메시지는 클라이언트에서 읽은 문자열이 콘솔에 표시 됩니다 하 고 연결 하는 클라이언트 처리 서버 소켓이 닫힙니다.  
  
 다음 샘플 구현 된 `readCallback` 메서드.  이 가정은 `StateObject` 클래스에서 정의 됩니다.  
  
```vb  
Public Shared Sub readCallback(ar As IAsyncResult)  
    Dim state As StateObject = CType(ar.AsyncState, StateObject)  
    Dim handler As Socket = state.workSocket  
  
    ' Read data from the client socket.   
    Dim read As Integer = handler.EndReceive(ar)  
  
    ' Data was read from the client socket.  
    If read > 0 Then  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, read))  
        handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf readCallback, state)  
    Else  
        If state.sb.Length > 1 Then  
            ' All the data has been read from the client;  
            ' display it on the console.  
            Dim content As String = state.sb.ToString()  
            Console.WriteLine("Read {0} bytes from socket." + _  
                ControlChars.Cr + " Data : {1}", content.Length, content)  
        End If  
    End If  
End Sub 'readCallback  
  
```  
  
```csharp  
public static void readCallback(IAsyncResult ar) {  
    StateObject state = (StateObject) ar.AsyncState;  
    Socket handler = state.WorkSocket;  
  
    // Read data from the client socket.  
    int read = handler.EndReceive(ar);  
  
    // Data was read from the client socket.  
    if (read > 0) {  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,read));  
        handler.BeginReceive(state.buffer,0,StateObject.BufferSize, 0,  
            new AsyncCallback(readCallback), state);  
    } else {  
        if (state.sb.Length > 1) {  
            // All the data has been read from the client;  
            // display it on the console.  
            string content = state.sb.ToString();  
            Console.WriteLine("Read {0} bytes from socket.\n Data : {1}",  
               content.Length, content);  
        }  
        handler.Close();  
    }  
}  
```  
  
## 참고 항목  
 [동기 서버 소켓 사용](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)   
 [비동기 서버 소켓 예제](../../../docs/framework/network-programming/asynchronous-server-socket-example.md)   
 [Threading](../../../docs/standard/threading/index.md)   
 [소켓으로 수신](../../../docs/framework/network-programming/listening-with-sockets.md)