---
title: "방법: 사용자 정의 예외 만들기 | Microsoft Docs"
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
  - "예외, 예제"
  - "예외, 사용자 정의"
  - "사용자 정의 예외"
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 사용자 정의 예외 만들기
사용자가 프로그래밍 방식으로 일부 오류 조건을 구분할 수 있도록 하기 위해 사용자 고유의 정의 예외를 만들 수 있습니다.  .NET Framework에서는 궁극적으로 기본 클래스인<xref:System.Exception>에서 파생되는 예외 클래스의 계층 구조를 사용할 수 있습니다.  이러한 각 클래스는 특정 예외를 정의하므로 대부분의 경우 사용자는 예외를 catch하기만 하면 됩니다.  또한 <xref:System.Exception> 클래스에서 예외 클래스를 파생시켜 사용자 고유의 예외 클래스를 만들 수 있습니다.  
  
 고유한 예외를 만들 때 사용자 정의 예외 클래스 이름 뒤에 "Exception"을 붙이는 것이 좋습니다. 다음 예제에서 보여 주는 세 개의 공통 생성자를 구현하는 것도 바람직합니다.  
  
> [!NOTE]
>  원격으로 사용하는 경우에는 사용자 정의 예외에 대한 메타데이터를 서버\(수신자\)와 클라이언트\(프록시 개체 또는 호출자\)에서 사용할 수 있도록 만들어야 합니다.  예를 들면, 별도의 응용 프로그램 도메인에 있는 메서드를 호출하는 코드는 원격 호출에서 throw한 예외가 포함된 어셈블리를 찾을 수 있어야 합니다.  자세한 내용은 [최선의 예외 처리 구현 방법](../../../docs/standard/exceptions/best-practices-for-exceptions.md)을 참조하십시오.  
  
 다음 예제에서는 새 예외 클래스인 `EmployeeListNotFoundException`이 <xref:System.Exception>에서 파생됩니다.  서로 다른 매개 변수를 사용하는 세 개의 생성자가 클래스에 정의됩니다.  
  
## 예제  
 [!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
 [!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
 [!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  
  
## 참고 항목  
 [방법: Try\/Catch 블록을 사용하여 예외 catch](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [방법: Catch 블록에 특정 예외 사용](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)   
 [최선의 예외 구현 방법](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [예외 처리 기본 사항](../../../docs/standard/exceptions/exception-handling-fundamentals.md)