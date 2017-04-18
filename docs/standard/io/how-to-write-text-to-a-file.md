---
title: "방법: 파일에 텍스트 쓰기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "파일에 텍스트 쓰기"
  - "I/O[.NET Framework], 파일에 텍스트 쓰기"
  - "스트림, 파일에 텍스트 쓰기"
  - "데이터 스트림, 파일에 텍스트 쓰기"
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
caps.latest.revision: 29
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 29
---
# 방법: 파일에 텍스트 쓰기
이 항목에서는 .NET Framework 응용 프로그램 또는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱을 위해 파일에 텍스트를 쓸 수 있는 여러 가지 방법을 보여 줍니다. 파일에 텍스트를 쓸 때는 일반적으로 다음 클래스 및 메서드가 사용됩니다.  
  
-   <xref:System.IO.StreamWriter> \- 동기적\(<xref:System.IO.StreamWriter.Write%2A> 또는 <xref:System.IO.TextWriter.WriteLine%2A>\) 또는 비동기적\(<xref:System.IO.StreamWriter.WriteAsync%2A> 및 <xref:System.IO.StreamWriter.WriteLineAsync%2A>\)으로 파일에 쓰는 메서드가 포함되어 있습니다.  
  
-   <xref:System.IO.File> \- .NET Framework 응용 프로그램과 함께 사용됩니다.<xref:System.IO.File.WriteAllLines%2A> 및 <xref:System.IO.File.WriteAllText%2A> 등 파일에 텍스트를 쓰거나 파일에 텍스트를 추가\(<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> 또는 <xref:System.IO.File.AppendText%2A>\)하는 정적 메서드를 제공합니다.  
  
-   [FileIO](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.aspx) \- [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱과 함께 사용됩니다. 파일에 텍스트를 쓰거나\([WriteLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writelinesasync.aspx) 또는 [WriteTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writetextasync.aspx)\) 파일에 텍스트를 추가\([AppendLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendlinesasync.aspx) 또는 [AppendTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendtextasync.aspx)\)하는 비동기 메서드가 포함됩니다.  
  
 수행 중인 작업에 집중할 수 있도록 간단한 샘플이 포함되었습니다. 이러한 이유로 샘플은 최소한의 오류 검사 및 예외 처리\(있는 경우\)를 수행합니다. 실제 응용 프로그램은 일반적으로 더 강력한 오류 검사 및 예외 처리 기능을 제공합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.IO.StreamWriter> 클래스를 사용하여 새 파일에 동기적으로 한 번에 한 줄씩 텍스트를 쓰는 방법을 보여 줍니다. 새 텍스트 파일은 사용자의 내 문서 폴더에 저장됩니다.<xref:System.IO.StreamWriter> 개체는 `using` 문에서 선언되고 인스턴스화되므로 스트림을 자동으로 플러시하고 닫는 <xref:System.IO.StreamWriter.Dispose%2A> 메서드가 호출됩니다.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeline)]
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeline)]  
  
## 예제  
 다음 예제에서는 <xref:System.IO.StreamWriter> 클래스를 사용하여 기존 파일에 텍스트를 추가하는 방법을 보여 줍니다. 이전 예제와 동일한 텍스트 파일을 사용합니다.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#appendtext)]
 [!code-vb[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#appendtext)]  
  
## 예제  
 다음 예제에서는 <xref:System.IO.StreamWriter> 클래스를 사용하여 새 파일에 비동기적으로 텍스트를 쓰는 방법을 보여 줍니다.<xref:System.IO.StreamWriter.WriteAsync%2A> 메서드를 호출하려면 `async` 메서드 내에서 이 메서드를 호출해야 합니다. 새 텍스트 파일은 사용자의 내 문서 폴더에 저장됩니다.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeasync)]
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeasync)]  
  
## 예제  
 다음 예제에서는 <xref:System.IO.File> 클래스를 사용하여 새 파일에 텍스트를 쓰고 동일한 파일에 새 텍스트 줄을 추가하는 방법을 보여 줍니다.<xref:System.IO.File.WriteAllText%2A> 및 <xref:System.IO.File.AppendAllLines%2A> 메서드는 자동으로 파일을 열고 닫습니다.<xref:System.IO.File.WriteAllText%2A> 메서드에 제공한 경로가 이미 있는 경우 파일을 덮어씁니다.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writefile)]
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writefile)]  
  
## 예제  
 다음 예제에서는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱에서 사용자 입력을 텍스트 파일에 비동기적으로 쓰는 방법을 보여 줍니다. 보안상의 이유로 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱에서 파일을 열려면 일반적으로 [FileOpenPicker](http://msdn.microsoft.com/library/windows/apps/windows.storage.pickers.fileopenpicker.aspx) 컨트롤을 사용해야 합니다. 이 예제에서 `FileOpenPicker`는 텍스트 파일을 표시하도록 필터링되었습니다.  
  
```xaml  
<Page  
    x:Class="OpenFileWindowsStore.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:local="using:OpenFileWindowsStore"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    mc:Ignorable="d">  
  
    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">  
        <Button Content="save text to a file" HorizontalAlignment="Left" Margin="103,417,0,0" VerticalAlignment="Top"   
                Width="329" Height="86" FontSize="35" Click="Button_Click"/>  
        <TextBox Name="UserInputTextBox"  FontSize="18" HorizontalAlignment="Left" Margin="106,146,0,0"   
                 TextWrapping="Wrap" Text="Write some text here, and select a file to write it to." VerticalAlignment="Top"   
                 Height="201" Width="558" AcceptsReturn="True"/>  
        <TextBlock Name="StatusTextBox" HorizontalAlignment="Left" Margin="106,570,0,147" TextWrapping="Wrap" Text="Status:"   
                   VerticalAlignment="Center" Height="51" Width="1074" FontSize="18" />  
    </Grid>  
</Page>  
```  
  
 [!code-csharp[OpenFileWindowsStore#Code](../../../samples/snippets/csharp/VS_Snippets_CLR/openfilewindowsstore/cs/mainpage.xaml.cs#code)]
 [!code-vb[OpenFileWindowsStore#Code](../../../samples/snippets/visualbasic/VS_Snippets_CLR/openfilewindowsstore/vb/mainpage.xaml.vb#code)]  
  
## 참고 항목  
 <xref:System.IO.StreamWriter>   
 <xref:System.IO.File.CreateText%2A?displayProperty=fullName>   
 [방법: 디렉터리 및 파일 열거](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)   
 [방법: 새로 만든 데이터 파일 읽기 및 쓰기](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [방법: 로그 파일 열기 및 추가](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [방법: 파일의 텍스트 읽기](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [파일 및 스트림 I\/O](../../../docs/standard/io/index.md)