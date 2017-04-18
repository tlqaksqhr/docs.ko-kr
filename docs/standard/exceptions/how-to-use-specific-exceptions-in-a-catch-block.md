---
title: "방법: Catch 블록에 특정 예외 사용 | Microsoft Docs"
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
  - "catch 블록"
  - "예외, try/catch 블록"
  - "try/catch 블록"
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: Catch 블록에 특정 예외 사용
발생한 예외는 스택으로 전달되므로 각 catch 블록은 예외를 처리할 수 있게 됩니다.  catch 문의 순서는 중요합니다.  일반적인 예외 catch 블록 앞에 특정 예외를 대상으로 하는 catch 블록을 지정하지 않으면 컴파일러에서 오류가 발생할 수 있습니다.  적합한 catch 블록이 결정되는 방식은 예외 유형을 catch 블록에 지정된 예외의 이름과 대응시키는 것입니다.  특정 catch 블록이 없으면 예외는 일반적인 catch 블록\(있는 경우\)에 의해 catch됩니다.  
  
 다음 코드 예제에서는 try\/catch 블록을 사용하여 <xref:System.InvalidCastException>을 catch합니다.  이 예제에서는 직급\(`Emlevel`\) 속성 하나만을 가지는 `Employee`라는 클래스를 만듭니다.  `PromoteEmployee` 메서드는 개체를 받아서 직급을 증가시킵니다.  <xref:System.DateTime> 인스턴스가 `PromoteEmployee` 메서드로 전달되면 **InvalidCastException**이 발생합니다.  
  
## 예제  
 [!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
 [!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
 [!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)]  
  
 공용 언어 런타임에서는 catch 블록으로 catch되지 않는 예외를 catch합니다.  런타임의 구성 상태에 따라 디버그 대화 상자가 나타나거나 프로그램 실행이 중단되고 예외 정보가 표시된 대화 상자가 나타납니다.  디버깅에 대한 자세한 내용은 [응용 프로그램 디버깅 및 프로파일링](../../../docs/framework/debug-trace-profile/index.md)을 참조하십시오.  
  
## 참고 항목  
 [방법: Try\/Catch 블록을 사용하여 예외 catch](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [방법: 명시적으로 예외 Throw](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)   
 [방법: 사용자 정의 예외 만들기](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)   
 [방법: Finally 블록 사용](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)   
 [Exception 클래스 및 속성](../../../docs/standard/exceptions/exception-class-and-properties.md)   
 [예외 처리 기본 사항](../../../docs/standard/exceptions/exception-handling-fundamentals.md)