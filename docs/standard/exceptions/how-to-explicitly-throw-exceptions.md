---
title: "방법: 명시적으로 예외 Throw | Microsoft Docs"
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
  - "예외, throw"
  - "예외, try/catch 블록"
  - "FileNotFoundException 클래스"
  - "암시적으로 예외 throw"
  - "try/catch 블록"
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 명시적으로 예외 Throw
`throw` 문을 사용하면 예외를 명시적으로 throw할 수 있으며  catch된 예외를 `throw` 문을 사용하여 다시 throw할 수도 있습니다.  디버깅할 때 더 많은 정보를 제공할 수 있도록 다시 throw한 예외에는 정보를 추가하는 것이 좋은 코드 작성 방법입니다.  
  
 다음 코드 예제에서는 발생 가능한 <xref:System.IO.FileNotFoundException>을 try\/catch 블록을 사용하여 catch합니다.  try 블록의 뒤에는 데이터 파일을 찾지 못할 경우 <xref:System.IO.FileNotFoundException>을 catch하고 콘솔에 메시지를 표시하는 catch 블록이 있습니다.  그 다음 throw 문은 새 <xref:System.IO.FileNotFoundException>을 throw하고 텍스트 정보를 예외에 추가합니다.  
  
## 예제  
 [!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
 [!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  
  
## 참고 항목  
 [방법: Try\/Catch 블록을 사용하여 예외 catch](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [방법: Catch 블록에 특정 예외 사용](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)   
 [방법: Finally 블록 사용](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)   
 [예외 처리 기본 사항](../../../docs/standard/exceptions/exception-handling-fundamentals.md)