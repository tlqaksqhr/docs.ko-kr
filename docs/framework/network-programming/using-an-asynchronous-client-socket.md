---
title: "비동기 클라이언트 소켓 사용 | Microsoft Docs"
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
  - "데이터 요청, 소켓"
  - "비동기 클라이언트 소켓"
  - "소켓 클래스, 비동기 클라이언트 소켓"
  - "인터넷에서 데이터 요청, 소켓"
  - "소켓, 비동기 클라이언트 소켓"
  - "데이터 받기, 소켓"
  - "프로토콜, 소켓"
  - "인터넷, 소켓"
  - "클라이언트 소켓"
ms.assetid: fd85bc88-e06c-467d-a30d-9fd7cffcfca1
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 비동기 클라이언트 소켓 사용
비동기 클라이언트 소켓은 네트워크 작업이 완료를 기다리는 동안 응용 프로그램을 일시 중단 하지 않는.  대신, 응용 프로그램이 원본 스레드에서 실행 하면서 하나의 스레드에서 네트워크 연결을 처리 하는 표준.NET Framework 비동기 프로그래밍 모델을 사용 합니다.  비동기 소켓은 네트워크 사용량이 만들거나 해당 네트워크 작업을 계속 하기 전에 완료 하려면 기다릴 수 없습니다 응용 프로그램에 적합 합니다.  
  
 <xref:System.Net.Sockets.Socket> 클래스의 비동기 메서드;.NET Framework 명명 패턴 나옵니다 예를 들어,는 동기 <xref:System.Net.Sockets.Socket.Receive%2A> 메서드는 비동기 해당 <xref:System.Net.Sockets.Socket.BeginReceive%2A> 및 <xref:System.Net.Sockets.Socket.EndReceive%2A> 방법.  
  
 비동기 작업 연산의 결과 반환 하는 콜백 메서드가 필요 합니다.  다음 콜백 메서드가 응용 프로그램 결과 알아야 할 경우입니다.  이 절의 예제 코드를 사용 하 여 네트워크 장치 연결을 완료할 콜백 메서드, 데이터를 보내고, 보내기 완료 콜백 메서드를 시작 하는 방법 및 데이터 받기를 끝낼 콜백 메서드 및 데이터를 받기 시작 하는 방법에 연결을 시작 하는 방법 보여 줍니다.  
  
 비동기 소켓 네트워크 연결 프로세스 시스템 스레드 풀의 여러 스레드를 사용합니다.  한 스레드가 보내거나 받을 데이터의 시작에 대 한 책임입니다. 다른 스레드에서 네트워크 장치에 연결을 완료 하 고 주고받을 데이터.  다음 예제에서의 인스턴스는 <xref:System.Threading.ManualResetEvent?displayProperty=fullName> 클래스 실행을 계속할 경우 신호 및 주 스레드 실행을 일시 중단 하는 데 사용 됩니다.  
  
 비동기 소켓은 네트워크 장치에 연결 하려면 다음 예제에서는 `Connect` 초기화 메서드는  **소켓** 호출 하는  [시작](frlrfsystemnetsocketssocketclassconnecttopic) 메서드를 전달 하는 네트워크 장치, connect 콜백 메서드 및 상태 개체를 나타내는 원격 끝점 \(클라이언트  **소켓**\), 비동기 호출 사이의 상태 정보를 전달 하도록 사용 됩니다.  구현 예제는 `Connect` 메서드는 지정 된 연결을  **소켓** 지정 된 끝점입니다.  전역 가정  **스레드가** 라는 `connectDone`.  
  
```vb  
Public Shared Sub Connect(remoteEP As EndPoint, client As Socket)  
    client.BeginConnect(remoteEP, _  
       AddressOf ConnectCallback, client)  
  
    connectDone.WaitOne()  
End Sub 'Connect  
```  
  
```csharp  
public static void Connect(EndPoint remoteEP, Socket client) {  
    client.BeginConnect(remoteEP,   
        new AsyncCallback(ConnectCallback), client );  
  
   connectDone.WaitOne();  
}  
```  
  
 Connect 콜백 메서드 `ConnectCallback` 구현 된 <xref:System.AsyncCallback> 위임 합니다.  원격 장치에서 사용할 수 있으며 연결을 설정 하 여 완료 된 응용 프로그램 스레드가 다음 신호 때 원격 장치에 연결 된  **스레드가**`connectDone`.   다음 구현 코드는 `ConnectCallback` 메서드.  
  
```vb  
Private Shared Sub ConnectCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete the connection.  
        client.EndConnect(ar)  
  
        Console.WriteLine("Socket connected to {0}", _  
            client.RemoteEndPoint.ToString())  
  
        ' Signal that the connection has been made.  
        connectDone.Set()  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'ConnectCallback  
  
```  
  
```csharp  
private static void ConnectCallback(IAsyncResult ar) {  
    try {  
        // Retrieve the socket from the state object.  
        Socket client = (Socket) ar.AsyncState;  
  
        // Complete the connection.  
        client.EndConnect(ar);  
  
        Console.WriteLine("Socket connected to {0}",  
            client.RemoteEndPoint.ToString());  
  
        // Signal that the connection has been made.  
        connectDone.Set();  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 메서드 예제 `Send` 지정 된 문자열 데이터를 ASCII 형식으로 인코딩하고에서 지정 된 소켓을 나타내는 네트워크 장치에 비동기식으로 보냅니다.  다음 예제에서는 구현 된 `Send` 메서드.  
  
```vb  
Private Shared Sub Send(client As Socket, data As [String])  
    ' Convert the string data to byte data using ASCII encoding.  
    Dim byteData As Byte() = Encoding.ASCII.GetBytes(data)  
  
    ' Begin sending the data to the remote device.  
    client.BeginSend(byteData, 0, byteData.Length, SocketFlags.None, _  
        AddressOf SendCallback, client)  
End Sub 'Send  
  
```  
  
```csharp  
private static void Send(Socket client, String data) {  
    // Convert the string data to byte data using ASCII encoding.  
    byte[] byteData = Encoding.ASCII.GetBytes(data);  
  
    // Begin sending the data to the remote device.  
    client.BeginSend(byteData, 0, byteData.Length, SocketFlags.None,  
        new AsyncCallback(SendCallback), client);  
}  
```  
  
 Send 메서드를 콜백 `SendCallback` 구현 된 <xref:System.AsyncCallback> 위임.  네트워크 장치에서 받을 준비가 되 면 데이터를 보냅니다.  구현은 다음 예제는 `SendCallback` 메서드.  전역 가정  **스레드가** 라는 `sendDone`.  
  
```vb  
Private Shared Sub SendCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete sending the data to the remote device.  
        Dim bytesSent As Integer = client.EndSend(ar)  
        Console.WriteLine("Sent {0} bytes to server.", bytesSent)  
  
        ' Signal that all bytes have been sent.  
        sendDone.Set()  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'SendCallback  
  
```  
  
```csharp  
private static void SendCallback(IAsyncResult ar) {  
    try {  
        // Retrieve the socket from the state object.  
        Socket client = (Socket) ar.AsyncState;  
  
        // Complete sending the data to the remote device.  
        int bytesSent = client.EndSend(ar);  
        Console.WriteLine("Sent {0} bytes to server.", bytesSent);  
  
        // Signal that all bytes have been sent.  
        sendDone.Set();  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 클라이언트 소켓에서 데이터를 읽는 상태 개체는 비동기 호출 사이의 값을 전달 해야 합니다.  다음 클래스는 클라이언트 소켓에서 데이터를 수신에 예제 상태 개체입니다.  클라이언트 소켓에서 수신된 된 데이터에 대 한 버퍼에 대 한 필드를 포함 하는 <xref:System.Text.StringBuilder> 들어오는 데이터 문자열을 보유할 합니다.  상태 개체에 이들이 필드 배치 값을 클라이언트 소켓에서 데이터를 읽을 수 있는 여러 호출 간에 유지 될 수 있습니다.  
  
```vb  
Public Class StateObject  
    ' Client socket.  
    Public workSocket As Socket = Nothing   
    ' Size of receive buffer.  
    Public BufferSize As Integer = 256  
    ' Receive buffer.  
    Public buffer(256) As Byte   
    ' Received data string.  
    Public sb As New StringBuilder()  
End Class 'StateObject  
  
```  
  
```csharp  
public class StateObject {  
    // Client socket.  
    public Socket workSocket = null;  
    // Size of receive buffer.  
    public const int BufferSize = 256;  
    // Receive buffer.  
    public byte[] buffer = new byte[BufferSize];  
    // Received data string.  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 예 `Receive` 상태 개체를 설정 하 고 다음 호출 하는 메서드는  **BeginReceive** 메서드는 클라이언트 소켓에서 데이터를 비동기적으로 읽기.  다음 예제에서는 구현 된 `Receive` 메서드.  
  
```vb  
Private Shared Sub Receive(client As Socket)  
    Try  
        ' Create the state object.  
        Dim state As New StateObject()  
        state.workSocket = client  
  
        ' Begin receiving the data from the remote device.  
        client.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf ReceiveCallback, state)  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'Receive  
  
```  
  
```csharp  
private static void Receive(Socket client) {  
    try {  
        // Create the state object.  
        StateObject state = new StateObject();  
        state.workSocket = client;  
  
        // Begin receiving the data from the remote device.  
        client.BeginReceive( state.buffer, 0, StateObject.BufferSize, 0,  
            new AsyncCallback(ReceiveCallback), state);  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 수신 하는 콜백 메서드 `ReceiveCallback` 구현 된  **연속화** 위임 합니다.  네트워크 장치에서 데이터를 수신 하 고 메시지 문자열을 빌드합니다.  바이트 데이터 네트워크에서 데이터 버퍼로 읽고 다음 호출에서  **BeginReceive** 메서드는 클라이언트에서 보낸 데이터를 다시 때까지 완료 됩니다.  클라이언트에서 모든 데이터를 읽고 후 `ReceiveCallback` 데이터를 설정 하 여 완료 된 응용 프로그램 스레드에 신호를  **스레드가** `sendDone`.  
  
 다음 예제 코드에서 구현 된 `ReceiveCallback` 메서드.  이 가정 이라는 전역 문자열 `response` 는 받은 문자열 및 전역 보관  **스레드가** 라는 `receiveDone`.  서버 네트워크 세션을 정상적으로 종료할 수를 클라이언트 소켓을 종료 해야 합니다.  
  
```vb  
Private Shared Sub ReceiveCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the state object and the client socket   
        ' from the asynchronous state object.  
        Dim state As StateObject = CType(ar.AsyncState, StateObject)  
        Dim client As Socket = state.workSocket  
  
        ' Read data from the remote device.  
        Dim bytesRead As Integer = client.EndReceive(ar)  
  
        If bytesRead > 0 Then  
            ' There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, _  
                bytesRead))  
  
            '  Get the rest of the data.  
            client.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
                AddressOf ReceiveCallback, state)  
        Else  
            ' All the data has arrived; put it in response.  
            If state.sb.Length > 1 Then  
                response = state.sb.ToString()  
            End If  
            ' Signal that all bytes have been received.  
            receiveDone.Set()  
        End If  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'ReceiveCallback  
  
```  
  
```csharp  
private static void ReceiveCallback( IAsyncResult ar ) {  
    try {  
        // Retrieve the state object and the client socket   
        // from the asynchronous state object.  
        StateObject state = (StateObject) ar.AsyncState;  
        Socket client = state.workSocket;  
        // Read data from the remote device.  
        int bytesRead = client.EndReceive(ar);  
        if (bytesRead > 0) {  
            // There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,bytesRead));  
                //  Get the rest of the data.  
            client.BeginReceive(state.buffer,0,StateObject.BufferSize,0,  
                new AsyncCallback(ReceiveCallback), state);  
        } else {  
            // All the data has arrived; put it in response.  
            if (state.sb.Length > 1) {  
                response = state.sb.ToString();  
            }  
            // Signal that all bytes have been received.  
            receiveDone.Set();  
        }  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
## 참고 항목  
 [동기 클라이언트 소켓 사용](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)   
 [소켓으로 수신](../../../docs/framework/network-programming/listening-with-sockets.md)   
 [비동기 클라이언트 소켓 예제](../../../docs/framework/network-programming/asynchronous-client-socket-example.md)