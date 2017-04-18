---
title: "방법: Finally 블록 사용 | Microsoft Docs"
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
  - "ArgumentOutOfRangeException 클래스"
  - "예외, finally 블록"
  - "예외, try/catch 블록"
  - "finally 블록"
  - "try/catch 블록"
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: Finally 블록 사용
예외가 발생하면 실행이 중단되며 가장 가까운 예외 처리기로 제어가 넘어갑니다.  이것은 항상 호출될 것으로 예상되는 일련의 코드가 실행되지 않음을 의미합니다.  파일 닫기와 같은 일부 리소스의 정리는 예외가 throw되어도 항상 실행되어야 합니다.  이렇게 하기 위해 finally 블록을 사용할 수 있습니다.  finally 블록은 예외의 throw 여부에 관계없이 항상 실행됩니다.  
  
 다음 코드 예제에서는 try\/catch 블록을 사용하여 <xref:System.ArgumentOutOfRangeException>을 catch합니다.  `Main` 메서드는 두 개의 배열을 만들어 한 배열을 다른 배열로 복사합니다.  이러한 복사 작업으로 인해 **ArgumentOutOfRangeException**이 생성되며 오류가 콘솔에 표시됩니다.  finally 블록은 복사 작업의 결과에 관계없이 실행됩니다.  
  
## 예제  
 [!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
 [!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
 [!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  
  
## 참고 항목  
 [방법: Try\/Catch 블록을 사용하여 예외 catch](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [방법: 명시적으로 예외 Throw](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)   
 [방법: 사용자 정의 예외 만들기](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)   
 [예외 처리 기본 사항](../../../docs/standard/exceptions/exception-handling-fundamentals.md)