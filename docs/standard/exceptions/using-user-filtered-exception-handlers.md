---
title: "사용자 필터 예외 처리기 사용 | Microsoft Docs"
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
  - "예외, 사용자 필터"
  - "사용자 필터 예외"
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# 사용자 필터 예외 처리기 사용
Visual Basic은 현재 사용자 필터 예외를 지원합니다.  사용자 필터 예외 처리기는 사용자가 예외에 대해 정의한 요구 사항을 기반으로 예외를 catch하고 처리합니다.  이러한 처리기는 **Catch** 문에 **When** 키워드를 사용합니다.  
  
 이러한 기술은 특정 예외 개체가 여러 오류에 해당할 때 유용합니다.  이 경우, 개체에는 대개 해당 오류와 관련된 특정 오류 코드가 포함된 속성이 있습니다.  이 오류 코드 속성을 식에 사용하여 해당 **Catch** 절에서 처리할 특정 오류만 선택할 수 있습니다.  
  
 다음 Visual Basic 예제에서는 **Catch\/When** 문을 보여 줍니다.  
  
```  
Try  
      'Try statements.  
   Catch When Err = VBErr_ClassLoadException  
      'Catch statements.  
End Try  
```  
  
 사용자 필터 절 식은 어떤 방법으로도 제한할 수 없습니다.  사용자 필터 예외를 실행하는 동안 예외가 발생하면 이 예외는 무시되며 필터 식의 계산 결과가 false인 것으로 간주됩니다.  이 경우 공용 언어 런타임에서는 현재 예외에 대한 처리기를 계속 검색합니다.  
  
## 특정 예외 및 사용자 필터 절 결합  
 catch 문에는 특정 예외 및 사용자 필터 절을 사용할 수 있습니다.  런타임에서는 이 특정 예외가 먼저 테스트됩니다.  이 특정 예외가 발생하면 런타임에서 사용자 필터를 실행합니다.  일반 필터에는 클래스 필터에 정의된 변수에 대한 참조가 포함될 수 있습니다.  이 두 필터 절의 순서는 바꿀 수 없습니다.  
  
 다음 Visual Basic 예제에서는 **Catch** 문에 사용한 특정 예외인 `ClassLoadException`과 **When** 키워드를 사용하는 사용자 필터 절을 보여 줍니다.  
  
```  
Try  
      'Try statements.  
   Catch cle As ClassLoadException When cle.IsRecoverable()  
      'Catch statements.  
End Try  
```  
  
## 참고 항목  
 [방법: Try\/Catch 블록을 사용하여 예외 catch](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [방법: Catch 블록에 특정 예외 사용](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)   
 [최선의 예외 구현 방법](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [예외 처리 기본 사항](../../../docs/standard/exceptions/exception-handling-fundamentals.md)