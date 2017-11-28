---
title: "방법: 문자열에 문자 쓰기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET Framework], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 336a7fec5e64cc0c45566631c73928e0c1d40a5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-characters-to-a-string"></a>방법: 문자열에 문자 쓰기
다음 코드 예제는 문자 배열에서 문자열로 문자를 동기적 및 비동기적으로 씁니다.  
  
## <a name="example"></a>예제  
 다음 예제는 배열에서 문자열로 5자를 동기적으로 씁니다.  
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example"></a>예제  
 다음 예제는 <xref:System.Windows.Controls.TextBox> 컨트롤에서 모든 문자를 비동기적으로 읽고 배열에 저장합니다. 그런 다음 별도의 줄에 각 문자 또는 공백 문자를 비동기적으로 쓰고 이어서 <xref:System.Windows.Controls.TextBlock> 컨트롤에 대한 줄 바꿈이 발생합니다.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.StringWriter>  
 <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
 <xref:System.Text.StringBuilder>  
 [파일 및 스트림 I/O](../../../docs/standard/io/index.md)  
 [비동기 파일 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [방법: 디렉터리 및 파일 열거](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [방법: 새로 만든 데이터 파일 읽기 및 쓰기](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [방법: 로그 파일 열기 및 추가](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [방법: 파일의 텍스트 읽기](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [방법: 파일에 텍스트 쓰기](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [방법: 문자열에서 문자 읽기](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
