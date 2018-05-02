---
title: '방법: 파일에 텍스트 쓰기'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- writing text to files
- I/O [.NET Framework], writing text to files
- streams, writing text to files
- data streams, writing text to files
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
caps.latest.revision: 29
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 926dfe1ea254fdb6460c835f58721f54609ddc90
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-write-text-to-a-file"></a><span data-ttu-id="cb125-102">방법: 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="cb125-102">How to: Write Text to a File</span></span>
<span data-ttu-id="cb125-103">이 항목에서는 .NET Framework 응용 프로그램 또는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱을 위해 파일에 텍스트를 쓸 수 있는 여러 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-103">This topic shows different ways you can write text to a file for .NET Framework applications or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="cb125-104">파일에 텍스트를 쓸 때는 일반적으로 다음 클래스 및 메서드가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-104">The following classes and methods are typically used to write text to a file:</span></span>  
  
-   <span data-ttu-id="cb125-105"><xref:System.IO.StreamWriter> - 동기적(<xref:System.IO.StreamWriter.Write%2A> 또는 <xref:System.IO.TextWriter.WriteLine%2A>) 또는 비동기적(<xref:System.IO.StreamWriter.WriteAsync%2A> 및 <xref:System.IO.StreamWriter.WriteLineAsync%2A>)으로 파일에 쓰는 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-105"><xref:System.IO.StreamWriter> - it contains methods to write to a file synchronously (<xref:System.IO.StreamWriter.Write%2A> or <xref:System.IO.TextWriter.WriteLine%2A>) or asynchronously (<xref:System.IO.StreamWriter.WriteAsync%2A> and <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span></span>  
  
-   <span data-ttu-id="cb125-106"><xref:System.IO.File> - .NET Framework 응용 프로그램과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-106"><xref:System.IO.File> – to be used with .NET Framework applications.</span></span> <span data-ttu-id="cb125-107"><xref:System.IO.File.WriteAllLines%2A> 및 <xref:System.IO.File.WriteAllText%2A>등 파일에 텍스트를 쓰거나 파일에 텍스트를 추가(<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> 또는 <xref:System.IO.File.AppendText%2A>)하는 정적 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-107">It provides static methods to write text to a file such as <xref:System.IO.File.WriteAllLines%2A> and <xref:System.IO.File.WriteAllText%2A>, or to append text to a file (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> or <xref:System.IO.File.AppendText%2A>).</span></span>  
  
-   <span data-ttu-id="cb125-108">[FileIO](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.aspx) - [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-108">[FileIO](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.aspx) - to be used with [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="cb125-109">파일에 텍스트를 쓰거나([WriteLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writelinesasync.aspx) 또는 [WriteTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writetextasync.aspx)) 파일에 텍스트를 추가([AppendLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendlinesasync.aspx) 또는 [AppendTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendtextasync.aspx))하는 비동기 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-109">It contains asynchronous methods to write text to a file ([WriteLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writelinesasync.aspx) or [WriteTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writetextasync.aspx)) or to append text to a file ([AppendLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendlinesasync.aspx) or [AppendTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendtextasync.aspx)).</span></span>  

- <span data-ttu-id="cb125-110"><xref:System.IO.Path> - 파일이나 디렉터리 경로 정보가 포함된 문자열에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-110"><xref:System.IO.Path> - to be used on strings that contain file or directory path information.</span></span> <span data-ttu-id="cb125-111">파일이나 디렉터리 경로를 빌드하려면 문자열의 연결을 허용하는 <xref:System.IO.Path.Combine%2A> 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-111">It contains the <xref:System.IO.Path.Combine%2A> method, which allows concatenation of strings to build a file or directory path.</span></span>


 <span data-ttu-id="cb125-112">수행 중인 작업에 집중할 수 있도록 간단한 샘플이 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-112">The samples have been kept simple in order to focus on the task being performed.</span></span> <span data-ttu-id="cb125-113">이러한 이유로 샘플은 최소한의 오류 검사 및 예외 처리(있는 경우)를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-113">For this reason, the samples perform minimal error checking and exception handling, if any.</span></span> <span data-ttu-id="cb125-114">실제 응용 프로그램은 일반적으로 더 강력한 오류 검사 및 예외 처리 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-114">A real-world application generally provides more robust error checking and exception handling.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb125-115">예</span><span class="sxs-lookup"><span data-stu-id="cb125-115">Example</span></span>  
 <span data-ttu-id="cb125-116">다음 예제에서는 <xref:System.IO.StreamWriter> 클래스를 사용하여 새 파일에 동기적으로 한 번에 한 줄씩 텍스트를 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-116">The following example shows how to synchronously write text to a new file using the <xref:System.IO.StreamWriter> class, one line at a time.</span></span> <span data-ttu-id="cb125-117">새 텍스트 파일은 사용자의 내 문서 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-117">The new text file is saved to the user's My Documents folder.</span></span> <span data-ttu-id="cb125-118"><xref:System.IO.StreamWriter> 개체는 `using` 문에서 선언되고 인스턴스화되므로 스트림을 자동으로 플러시하고 닫는 <xref:System.IO.StreamWriter.Dispose%2A> 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-118">Because the <xref:System.IO.StreamWriter> object is declared and instantiated in a `using` statement, the <xref:System.IO.StreamWriter.Dispose%2A> method is invoked which automatically flushes and closes the stream.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeline)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeline)]  
  
## <a name="example"></a><span data-ttu-id="cb125-119">예</span><span class="sxs-lookup"><span data-stu-id="cb125-119">Example</span></span>  
 <span data-ttu-id="cb125-120">다음 예제에서는 <xref:System.IO.StreamWriter> 클래스를 사용하여 기존 파일에 텍스트를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-120">The following example shows how to append text to an existing file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="cb125-121">이전 예제와 동일한 텍스트 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-121">It uses the same text file from the previous example.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#appendtext)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#appendtext)]     
  
## <a name="example"></a><span data-ttu-id="cb125-122">예</span><span class="sxs-lookup"><span data-stu-id="cb125-122">Example</span></span>  
 <span data-ttu-id="cb125-123">다음 예제에서는 <xref:System.IO.StreamWriter> 클래스를 사용하여 새 파일에 비동기적으로 텍스트를 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-123">The following example shows how to asynchronously write text to a new file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="cb125-124"><xref:System.IO.StreamWriter.WriteAsync%2A> 메서드를 호출하려면 `async` 메서드 내에서 이 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-124">In order to invoke the <xref:System.IO.StreamWriter.WriteAsync%2A> method, the method call needs to be within an `async` method.</span></span> <span data-ttu-id="cb125-125">새 텍스트 파일은 사용자의 내 문서 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-125">The new text file is saved to the user's My Documents folder.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeasync)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeasync)]  
  
## <a name="example"></a><span data-ttu-id="cb125-126">예</span><span class="sxs-lookup"><span data-stu-id="cb125-126">Example</span></span>  
 <span data-ttu-id="cb125-127">다음 예제에서는 <xref:System.IO.File> 클래스를 사용하여 새 파일에 텍스트를 쓰고 동일한 파일에 새 텍스트 줄을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-127">The following example shows how to write text to a new file and append new lines of text to the same file using the <xref:System.IO.File> class.</span></span> <span data-ttu-id="cb125-128"><xref:System.IO.File.WriteAllText%2A> 및 <xref:System.IO.File.AppendAllLines%2A> 메서드는 자동으로 파일을 열고 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-128">The <xref:System.IO.File.WriteAllText%2A> and <xref:System.IO.File.AppendAllLines%2A> methods open and close the file automatically.</span></span> <span data-ttu-id="cb125-129"><xref:System.IO.File.WriteAllText%2A> 메서드에 제공한 경로가 이미 있는 경우 파일을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-129">If the path you provide to the <xref:System.IO.File.WriteAllText%2A> method already exists, the file will be overwritten.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writefile)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writefile)]  
  
## <a name="example"></a><span data-ttu-id="cb125-130">예</span><span class="sxs-lookup"><span data-stu-id="cb125-130">Example</span></span>  
 <span data-ttu-id="cb125-131">다음 예제에서는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱에서 사용자 입력을 텍스트 파일에 비동기적으로 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-131">The following example shows how to asynchronously write user input to a text file in a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.</span></span> <span data-ttu-id="cb125-132">보안상의 이유로 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱에서 파일을 열려면 일반적으로 [FileOpenPicker](http://msdn.microsoft.com/library/windows/apps/windows.storage.pickers.fileopenpicker.aspx) 컨트롤을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-132">Because of security considerations, opening a file from a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app typically requires the use of a [FileOpenPicker](http://msdn.microsoft.com/library/windows/apps/windows.storage.pickers.fileopenpicker.aspx) control.</span></span> <span data-ttu-id="cb125-133">이 예제에서 `FileOpenPicker` 는 텍스트 파일을 표시하도록 필터링되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cb125-133">In this example, the `FileOpenPicker` is filtered to show text files.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cb125-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb125-134">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <xref:System.IO.Path>  
 <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="cb125-135">방법: 디렉터리 및 파일 열거</span><span class="sxs-lookup"><span data-stu-id="cb125-135">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="cb125-136">방법: 새로 만든 데이터 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="cb125-136">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="cb125-137">방법: 로그 파일 열기 및 추가</span><span class="sxs-lookup"><span data-stu-id="cb125-137">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="cb125-138">방법: 파일의 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="cb125-138">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="cb125-139">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="cb125-139">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
