---
title: '방법: 파일의 텍스트 읽기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0bb37c5beaaa529ea09fa23f31b55a0d6bc6d510
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-text-from-a-file"></a>방법: 파일의 텍스트 읽기
다음 예제에서는 데스크톱 응용 프로그램용 .NET을 사용하여 텍스트 파일에서 텍스트를 동기 또는 비동기적으로 읽는 방법을 보여 줍니다. 두 예제에서는 <xref:System.IO.StreamReader> 클래스의 인스턴스를 만들 때 파일의 상대 또는 절대 경로를 제공합니다. 다음 예제에서는 TestFile.txt라는 파일이 응용 프로그램과 같은 폴더에 있다고 가정합니다.  
  
 Windows 런타임에서는 파일을 읽고 파일에 쓰는 다양한 스트림 형식을 제공하기 때문에 이런 코드 예제는 Windows 스토어 앱을 위한 개발에 적용되지 않습니다. Windows 스토어 앱의 컨텍스트 내에 있는 파일에서 텍스트를 읽는 방법을 보여주는 예제를 보려면 [Quickstart: Reading and writing files](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)(빠른 시작: 파일 읽기 및 쓰기)를 참조하세요. .NET Framework 스트림과 Windows 런타임 스트림 간에 변환하는 방법의 예제는 [방법: .NET Framework 스트림과 Windows 런타임 스트림 간 변환](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)을 참조하세요.  
  
## <a name="example"></a>예  
 첫 번째 예제에서는 콘솔 응용 프로그램 내에서 동기적 읽기 작업을 보여 줍니다. 이 예제에서는 스트림 판독기를 사용하여 텍스트 파일을 열면 내용이 문자열로 복사되고 해당 문자열이 콘솔에 출력됩니다.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a>예  
 두 번째 예제에서는 Windows Presentation Foundation(WPF) 응용 프로그램에서의 비동기 읽기 작업을 보여 줍니다.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [비동기 파일 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [NIB: 방법: 디렉터리 목록 생성 만들기](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [Quickstart: Reading and writing files](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)(빠른 시작: 파일 읽기 및 쓰기)  
 [방법: .NET Framework 스트림과 Windows 런타임 스트림 간 변환](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
 [방법: 새로 만든 데이터 파일 읽기 및 쓰기](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [방법: 로그 파일 열기 및 추가](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [방법: 파일에 텍스트 쓰기](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [방법: 문자열에서 문자 읽기](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [방법: 문자열에 문자 쓰기](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [파일 및 스트림 I/O](../../../docs/standard/io/index.md)
