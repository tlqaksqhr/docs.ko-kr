---
title: "예외 처리 기본 사항 | Microsoft Docs"
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
  - "공용 언어 런타임, 예외"
  - "예외, 예제"
  - "런타임, 예외"
ms.assetid: e865d48c-b862-4448-833e-09fcd48adf6b
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# 예외 처리 기본 사항
공용 언어 런타임에서는 예외 개체 및 보호된 코드 블록 개념을 기반으로 하는 예외 처리 모델을 지원합니다.  런타임에서는 발생한 예외를 나타내기 위해 개체를 만듭니다.  해당 기본 예외에서 클래스를 파생시켜 사용자 고유의 예외 클래스를 만들 수도 있습니다.  
  
 런타임을 사용하는 모든 언어는 비슷한 방식으로 예외를 처리합니다.  각 언어는 try\/catch\/finally 구조의 예외 처리 형태를 사용합니다.  이 단원에서는 몇 개의 기본적인 예외 처리 예제를 제공합니다.  
  
## 단원 내용  
 [방법: Try\/Catch 블록을 사용하여 예외 catch](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)  
 try\/catch 블록을 사용하여 예외를 처리하는 방법을 설명합니다.  
  
 [방법: Catch 블록에 특정 예외 사용](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)  
 특정 예외를 catch하는 방법을 설명합니다.  
  
 [방법: 명시적으로 예외 Throw](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)  
 예외를 throw하는 방법과 예외를 catch하여 다시 throw하는 방법을 설명합니다.  
  
 [방법: 사용자 정의 예외 만들기](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)  
 사용자 고유의 예외 클래스를 만드는 방법을 설명합니다.  
  
 [사용자 필터 처리기 사용](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md)  
 필터링된 예외를 설정하는 방법을 설명합니다.  
  
 [방법: Finally 블록 사용](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)  
 예외 블록에서 finally 문을 사용하는 방법을 설명합니다.  
  
## 관련 단원  
 [예외](../../../docs/standard/exceptions/index.md)  
 공용 언어 런타임 예외를 개략적으로 설명합니다.  
  
 [Exception 클래스 및 속성](../../../docs/standard/exceptions/exception-class-and-properties.md)  
 예외 개체의 각 요소를 설명합니다.