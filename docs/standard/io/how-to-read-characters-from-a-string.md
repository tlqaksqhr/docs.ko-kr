---
title: '방법: 문자열에서 문자 읽기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2e128f1011b6daa5c0e8b62252c8adc3175586c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572777"
---
# <a name="how-to-read-characters-from-a-string"></a>방법: 문자열에서 문자 읽기
다음 코드 예제는 문자열에서 동기적 및 비동기적으로 문자를 읽는 방법을 보여줍니다.  
  
## <a name="example"></a>예  
 이 예제에서는 문자열에서 동기적으로 13자를 읽고, 배열에 저장하고, 해당 문자를 표시합니다. 그런 다음, 문자열의 나머지 문자를 읽고, 6번째 요소에서 시작하는 배열에 저장하고, 배열의 내용을 표시합니다.  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example"></a>예  
 다음 예제는 <xref:System.Windows.Controls.TextBox> 컨트롤에서 모든 문자를 비동기적으로 읽고 배열에 저장합니다. 그런 다음 별도의 줄에 각 문자 또는 공백 문자를 비동기적으로 쓰고 이어서 <xref:System.Windows.Controls.TextBlock> 컨트롤에 대한 줄 바꿈이 발생합니다.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.StringReader>  
 <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
 [비동기 파일 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [NIB: 방법: 디렉터리 목록 생성 만들기](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [방법: 새로 만든 데이터 파일 읽기 및 쓰기](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [방법: 로그 파일 열기 및 추가](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [방법: 파일의 텍스트 읽기](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [방법: 파일에 텍스트 쓰기](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [방법: 문자열에 문자 쓰기](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [파일 및 스트림 I/O](../../../docs/standard/io/index.md)
