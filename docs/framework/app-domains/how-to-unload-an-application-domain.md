---
title: "방법: 응용 프로그램 도메인 언로드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Unload 메서드"
  - "응용 프로그램 도메인, 언로드"
  - "응용 프로그램 도메인 언로드"
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 응용 프로그램 도메인 언로드
응용 프로그램 도메인을 사용한 후에는[System.AppDomain.Unload](frlrfSystemAppDomainClassUnloadTopic) 메서드를 사용하여 이 도메인을 언로드합니다.  **Unload** 메서드는 지정된 응용 프로그램 도메인을 자동으로 종료합니다.  프로세스를 언로드하는 동안 새 스레드는 응용 프로그램 도메인에 액세스할 수 없습니다. 또한 응용 프로그램 도메인 전용의 모든 데이터 구조가 비워집니다.  
  
 응용 프로그램 도메인에 로드된 어셈블리는 모두 제거되고 더 이상 사용할 수 없습니다.  응용 프로그램 도메인에 있는 어셈블리가 도메인 중립 어셈블리인 경우, 해당 어셈블리의 데이터는 전체 프로세스가 종료될 때까지 메모리에 남아 있습니다.  따라서 도메인 중립 어셈블리를 언로드하려면 전체 프로세스를 종료하는 것이 유일한 방법입니다.  경우에 따라 응용 프로그램 도메인 언로드 요청이 제대로 실행되지 않고 <xref:System.CannotUnloadAppDomainException>이 발생할 수도 있습니다.  
  
 다음 예제는 `MyDomain`이라는 새 응용 프로그램 도메인을 만들고, 일부 정보를 콘솔에 출력한 다음, 응용 프로그램 도메인을 언로드합니다.  이 코드에서는 언로드된 응용 프로그램 도메인의 이름을 콘솔에 출력하려고 합니다.  이 동작에서 예외가 발생하는데, 이 예외는 프로그램 끝에서 try\/catch 문에 의해 처리됩니다.  
  
## 예제  
 [!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)]
 [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)]
 [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]  
  
## 참고 항목  
 [Programming with Application Domains](http://msdn.microsoft.com/ko-kr/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [방법: 응용 프로그램 도메인 만들기](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)   
 [응용 프로그램 도메인 사용](../../../docs/framework/app-domains/use.md)