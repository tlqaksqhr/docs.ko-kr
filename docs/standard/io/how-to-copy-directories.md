---
title: "방법: 디렉터리 복사"
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
- directory copying
- I/O [.NET Framework], copying directories
- subdirectory copying
- copying directories
- directories [.NET Framework], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a5602a4e227f3cd17e4a7c9a086bee69d3e3e506
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-copy-directories"></a>방법: 디렉터리 복사
이 예제에서는 I/O 클래스를 사용하여 디렉터리의 내용을 다른 위치로 동기적으로 복사하는 방법을 보여 줍니다. 이 예제에서는 사용자가 하위 디렉터리도 복사할지 지정할 수 있습니다. 하위 디렉터리를 복사하는 경우 이 예제의 메서드는 더 이상 복사할 항목이 없을 때까지 각 후속 하위 디렉터리에서 자신을 호출하여 재귀적으로 복사합니다.  
  
 비동기적인 파일 복사의 예제는 [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.FileInfo>  
 <xref:System.IO.DirectoryInfo>  
 <xref:System.IO.FileStream>  
 [파일 및 스트림 I/O](../../../docs/standard/io/index.md)  
 [공통적인 I/O 작업](../../../docs/standard/io/common-i-o-tasks.md)  
 [비동기 파일 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)
