---
title: "Exception 클래스 및 속성 | Microsoft Docs"
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
  - "Exception 클래스"
  - "예외, Exception 클래스"
ms.assetid: e2e1f8c4-e7b4-467d-9a66-13c90861221d
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Exception 클래스 및 속성
<xref:System.Exception> 클래스는 예외에 상속되는 기본 클래스입니다.  대부분의 예외 개체는 **Exception**에서 파생된 일부 클래스의 인스턴스이지만 <xref:System.Object> 클래스에서 파생된 모든 개체를 예외로 throw할 수 있습니다.  **Exception**으로부터 파생되지 않은 개체를 throw하거나 catch할 수 없는 언어도 있습니다.  대부분의 경우 **Exception** 개체만 throw하거나 catch하는 것이 좋습니다.  
  
 **Exception** 클래스에는 예외를 더 쉽게 이해할 수 있도록 해주는 속성이 몇 개 있습니다.  이러한 속성에는 다음과 같은 것이 있습니다.  
  
-   <xref:System.Exception.StackTrace%2A> 속성  
  
     이 속성에는 오류 발생 위치를 결정하는 데 사용할 수 있는 스택 추적이 포함됩니다.  디버깅 정보를 사용할 수 있는 경우 스택 추적에는 소스 파일 이름과 프로그램 줄 번호가 포함됩니다.  
  
-   <xref:System.Exception.InnerException%2A> 속성  
  
     이 속성을 사용하면 예외를 처리할 때 일련의 예외를 만들어 보존할 수 있습니다.  이 속성을 사용하면 이전에 catch한 예외를 포함하는 새 예외를 만들 수 있습니다.  **InnerException** 속성에서 원래 예외를 두 번째 예외가 캡처할 수 있으며, 이렇게 하면 두 번째 예외를 처리하는 코드에서 추가 정보를 검사할 수 있습니다.  
  
     예를 들어, 파일을 읽고 읽은 데이터의 서식을 지정하는 메서드가 있다고 가정합니다.  이 코드에서 파일을 읽으려고 시도하지만 FileException이 throw됩니다.  이 메서드는 FileException을 catch한 다음 BadFormatException을 throw합니다.  이 경우, FileException을 BadFormatException의 **InnerException** 속성에 저장할 수 있습니다.  
  
     예외가 throw된 이유를 결정하는 호출자의 기능을 향상시키기 위해서는 때때로 메서드에서 도우미 루틴이 throw한 예외를 catch한 다음 발생한 오류를 더 자세히 나타내도록 예외를 throw하는 것이 좋습니다.  좀 더 의미 있는 새 예외를 만들 수 있습니다. 이러한 경우 내부 예외 참조를 원래의 예외로 설정할 수 있습니다.  이제 좀 더 의미 있는 이 예외를 호출자에 throw할 수 있습니다.  이러한 기능을 사용하면 제일 먼저 throw된 예외로 끝나는 일련의 연결된 예외를 만들 수 있습니다.  
  
-   <xref:System.Exception.Message%2A> 속성  
  
     이 속성으로 예외의 원인에 대한 자세한 내용을 알 수 있습니다.  **Message**는 예외를 throw하는 스레드의 <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=fullName> 속성에서 지정한 언어로 표시됩니다.  
  
-   <xref:System.Exception.HelpLink%2A> 속성  
  
     이 속성에는 예외의 원인에 대한 광범위한 정보를 제공하는 도움말 파일의 URL 또는 URN이 보관될 수 있습니다.  
  
-   <xref:System.Exception.Data%2A> 속성  
  
     이 속성은 키 값 쌍에 임의의 데이터를 저장할 수 있는 IDictionary입니다.  
  
 **Exception**으로부터 상속 받는 대부분의 클래스는 추가 멤버를 구현하거나 추가 기능을 제공하지 않습니다. 단지 **Exception**으로부터 상속 받기만 합니다.  따라서, 예외에 대한 대부분의 중요한 정보는 예외 계층, 예외 이름, 예외에 포함된 정보에 들어 있습니다.  
  
## 참고 항목  
 [예외 계층](../../../docs/standard/exceptions/exception-hierarchy.md)   
 [예외 처리 기본 사항](../../../docs/standard/exceptions/exception-handling-fundamentals.md)   
 [최선의 예외 구현 방법](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [예외](../../../docs/standard/exceptions/index.md)