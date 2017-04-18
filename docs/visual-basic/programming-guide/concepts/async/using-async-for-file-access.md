---
title: "파일 액세스 (Visual Basic)에 Async 사용 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c989305f-08e3-4687-95c3-948465cda202
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e0e548989b1d2c32b9faf5ce0dd90ae371dfc028
ms.lasthandoff: 03/13/2017

---
# <a name="using-async-for-file-access-visual-basic"></a>파일 액세스에 Async 사용(Visual Basic)
파일에 액세스 하는 비동기 기능을 사용할 수 있습니다. 비동기 기능을 사용하면 콜백을 사용하거나 여러 메서드 또는 람다 식에 코드를 분할하지 않고도 비동기 메서드를 호출할 수 있습니다. 동기 코드를 비동기로 만들려면 있습니다 방금 동기 메서드 대신 비동기 메서드를 호출 하 고 몇 가지 키워드를 코드에 추가 합니다.  
  
 비동기 파일 액세스 호출을 추가 하기 위한 다음과 같은 이유로 고려할 수 있습니다.  
  
-   비동기 이용 하면 UI 응용 프로그램 응답성 UI 스레드 작업을 시작 하는 다른 작업을 수행할 수 있습니다. UI 스레드는 코드를 실행 해야 합니다 (예: 50 개 이상의 밀리초) 시간이 오래 걸리는 경우 UI는 I/O 완료 되 고 다시 키보드를 처리 하 고 마우스 입력 및 다른 이벤트 수 UI 스레드가 될 때까지 중지 될 수 있습니다.  
  
-   비동기는 스레드에 대 한 필요를 줄여 ASP.NET의 확장성 및 기타 서버 기반 응용 프로그램을 향상 시킵니다. 응용 프로그램 응답 당 전용된 스레드를 사용 하는 천 요청을 동시에 처리 되는 경우는 천 스레드가 필요 합니다. 종종 비동기 작업 대기 하는 동안 스레드를 사용 하도록 않아도 됩니다. 기존 I/O 완료 스레드를 잠시 사용할 끝입니다.  
  
-   현재 조건 아래에서 파일 액세스 작업의 대기 시간이 매우 낮을 수 있지만 대기 시간이 나중에 크게 향상 될 수 있습니다. 예를 들어 파일에는 서버는 전 세계에 이동할 수 있습니다.  
  
-   추가 된 비동기 기능을 사용 하 여 오버 헤드 작습니다.  
  
-   비동기 작업은 동시에 쉽게 실행할 수 있습니다.  
  
## <a name="running-the-examples"></a>예제 실행  
 이 항목의 예제를 실행 하려면 만들 수는 **WPF 응용 프로그램** 또는 **Windows Forms 응용 프로그램** 다음 추가 **단추**합니다. 단추의 `Click` 이벤트를 각 예제에서 첫 번째 방법에 대 한 호출을 추가 합니다.  
  
 다음 예제에서는 다음과 같습니다 `Imports` 문입니다.  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a>FileStream 클래스 사용  
 이 항목에서는 예제는 <xref:System.IO.FileStream>옵션을 사용 하면 운영 체제 수준에서 발생 하는 비동기 I/O를가지고 있는 클래스입니다.</xref:System.IO.FileStream> 이 옵션을 사용 하 여 대부분의 경우에서 스레드 풀 스레드를 차단 방지할 수 있습니다. 이 옵션을 사용 하려면 지정 된 `useAsync=true` 또는 `options=FileOptions.Asynchronous` 생성자 호출의 인수입니다.  
  
 <xref:System.IO.StreamReader> <xref:System.IO.StreamWriter>파일 경로 지정 하 여 직접 찾아서</xref:System.IO.StreamWriter> 를 열 경우</xref:System.IO.StreamReader> 함께이 옵션을 사용할 수 없습니다. 그러나 사용자가 제공 하는 경우이 옵션을 사용할 수는는 <xref:System.IO.Stream>하는 <xref:System.IO.FileStream>클래스 열.</xref:System.IO.FileStream> </xref:System.IO.Stream> Note는 비동기 호출 되므로 속도가 빨라집니다 UI 응용 프로그램에서 스레드 풀 스레드가 차단 되는 경우에 대기 하는 동안 UI 스레드가 차단 되지 않습니다.  
  
## <a name="writing-text"></a>텍스트 쓰기  
 다음 예제에서는 파일에 텍스트를 씁니다. Await 문은 각, 메서드가 즉시 종료 됩니다. 파일 I/O 완료 되 면 메서드는 await 문 뒤에 오는 문에서 다시 시작 합니다. Async 한정자 await 문을 사용 하는 메서드의 정의에 있는 참고 합니다.  
  
```vb  
Public Async Sub ProcessWrite()  
    Dim filePath = "temp2.txt"  
    Dim text = "Hello World" & ControlChars.CrLf  
  
    Await WriteTextAsync(filePath, text)  
End Sub  
  
Private Async Function WriteTextAsync(filePath As String, text As String) As Task  
    Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Append, FileAccess.Write, FileShare.None,  
        bufferSize:=4096, useAsync:=True)  
  
        Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
    End Using  
End Function  
```  
  
 원래 예제에 문 `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, 다음 두 개의 문이 축약 된 것입니다.  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 첫 번째 문에서 작업을 반환 않았으며 파일 처리를 시작 합니다. Await와 두 번째 문은 메서드를 즉시 종료 하 고 다른 작업을 반환 합니다. 나중에 처리 하는 파일에는 다음이 완료 되 면 실행 await 뒤에 오는 문으로 반환 됩니다. 자세한 내용은 참조 [비동기 프로그램 (Visual Basic)의 제어 흐름](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)합니다.  
  
## <a name="reading-text"></a>텍스트 읽기  
 다음 예제에서는 파일에서 텍스트를 읽습니다. 텍스트 버퍼링 되며,이 경우에 <xref:System.Text.StringBuilder>.</xref:System.Text.StringBuilder> 에 배치 와 달리 앞의 예제에서 await의 계산 값을 생성 합니다. <xref:System.IO.Stream.ReadAsync%2A>메서드가 반환 되는 <xref:System.Threading.Tasks.Task> \< <xref:System.Int32>> await의 평가 생성 하므로 `Int32` 값 (`numRead`)은 작업이 끝난 후.</xref:System.Int32> </xref:System.Threading.Tasks.Task> </xref:System.IO.Stream.ReadAsync%2A> 자세한 내용은 참조 [비동기 반환 형식 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)합니다.  
  
```vb  
Public Async Sub ProcessRead()  
    Dim filePath = "temp2.txt"  
  
    If File.Exists(filePath) = False Then  
        Debug.WriteLine("file not found: " & filePath)  
    Else  
        Try  
            Dim text As String = Await ReadTextAsync(filePath)  
            Debug.WriteLine(text)  
        Catch ex As Exception  
            Debug.WriteLine(ex.Message)  
        End Try  
    End If  
End Sub  
  
Private Async Function ReadTextAsync(filePath As String) As Task(Of String)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Open, FileAccess.Read, FileShare.Read,  
        bufferSize:=4096, useAsync:=True)  
  
        Dim sb As New StringBuilder  
  
        Dim buffer As Byte() = New Byte(&H1000) {}  
        Dim numRead As Integer  
        numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        While numRead <> 0  
            Dim text As String = Encoding.Unicode.GetString(buffer, 0, numRead)  
            sb.Append(text)  
  
            numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        End While  
  
        Return sb.ToString  
    End Using  
End Function  
```  
  
## <a name="parallel-asynchronous-io"></a>병렬 비동기 I/O  
 다음 예제에서는 10 개의 텍스트 파일을 작성 하 여 병렬 처리를 보여 줍니다. 각 파일에는 <xref:System.IO.Stream.WriteAsync%2A>메서드는 다음 작업 목록에 추가 되는 작업을 반환 합니다.</xref:System.IO.Stream.WriteAsync%2A> `Await Task.WhenAll(tasks)` 문을 메서드를 종료 하 고 모든 작업에 대 한 파일 처리 되 면 메서드 내에서 다시 시작을 완료 합니다.  
  
 모든 닫습니다 <xref:System.IO.FileStream>인스턴스에 `Finally` 는 작업이 완료 된 후 차단.</xref:System.IO.FileStream> 각 경우 `FileStream` 에서 대신 만든는 `Imports` 문는 `FileStream` 작업이 완료 되기 전에의 삭제할 수 있습니다.  
  
 모든 성능 개선 효과 사용 하 여 병렬 처리 및 비동기 처리 하지에서 거의 완전히 인지 note 합니다. 비동기의 장점은 여러 스레드를 묶어 두지 않기 및 사용자 인터페이스 스레드 하도록 묶어 두지 않기입니다.  
  
```vb  
Public Async Sub ProcessWriteMult()  
    Dim folder = "tempfolder\"  
    Dim tasks As New List(Of Task)  
    Dim sourceStreams As New List(Of FileStream)  
  
    Try  
        For index = 1 To 10  
            Dim text = "In file " & index.ToString & ControlChars.CrLf  
  
            Dim fileName = "thefile" & index.ToString("00") & ".txt"  
            Dim filePath = folder & fileName  
  
            Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
            Dim sourceStream As New FileStream(filePath,  
                FileMode.Append, FileAccess.Write, FileShare.None,  
                bufferSize:=4096, useAsync:=True)  
  
            Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
            sourceStreams.Add(sourceStream)  
  
            tasks.Add(theTask)  
        Next  
  
        Await Task.WhenAll(tasks)  
    Finally  
        For Each sourceStream As FileStream In sourceStreams  
            sourceStream.Close()  
        Next  
    End Try  
End Sub  
```  
  
 사용 하는 경우는 <xref:System.IO.Stream.WriteAsync%2A>및 <xref:System.IO.Stream.ReadAsync%2A>메서드를 지정할 수 있습니다는 <xref:System.Threading.CancellationToken>, 작업 중간 스트림을 취소 하는 데 사용할 수 있는.</xref:System.Threading.CancellationToken> </xref:System.IO.Stream.ReadAsync%2A> </xref:System.IO.Stream.WriteAsync%2A> 자세한 내용은 참조 [미세 조정 Your 비동기 응용 프로그램 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) 및 [관리 되는 스레드의 취소](http://msdn.microsoft.com/library/eea11fe5-d8b0-4314-bb5d-8a58166fb1c3)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [비동기 반환 형식 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)   
 [비동기 프로그램 (Visual Basic)의 제어 흐름](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)
