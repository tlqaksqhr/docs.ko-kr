---
title: "다중 파일 어셈블리 | Microsoft Docs"
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
  - "어셈블리[.NET Framework], 다중 파일"
  - "어셈블리 매니페스트, 다중 파일 어셈블리"
  - "코드 모듈"
  - "명령줄 컴파일러"
  - "어셈블리 컴파일"
  - "어셈블리의 진입점"
  - "다중 파일 어셈블리"
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 다중 파일 어셈블리
명령줄 컴파일러나 Visual C\+\+가 포함된 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]를 사용하여 다중 파일 어셈블리를 만들 수 있습니다.  어셈블리의 한 파일에는 어셈블리 매니페스트가 들어 있어야 합니다.  응용 프로그램을 시작하는 어셈블리에는 Main 또는 WinMain 메서드 등의 진입점이 포함되어야 합니다.  
  
 예를 들어, 응용 프로그램에 두 코드 모듈 Client.cs와 Stringer.cs가 포함되어 있는 것으로 가정합니다.  Stringer.cs는 `myStringer`라는 네임스페이스를 만들며, 이 네임스페이스는 Client.cs의 코드에 의해 참조됩니다.  Client.cs에는 응용 프로그램의 진입점인 `Main` 메서드가 포함됩니다.  이 예제에서 사용자는 두 모듈을 컴파일한 다음 어셈블리 매니페스트가 포함된 세 번째 파일을 만들며, 이 파일에 의해 응용 프로그램이 시작됩니다.  어셈블리 매니페스트는 `Client` 모듈과 `Stringer` 모듈을 모두 참조합니다.  
  
> [!NOTE]
>  어셈블리에 여러 개의 코드 모듈이 있더라도 다중 파일 어셈블리는 단 하나의 진입점만 포함할 수 있습니다.  
  
 다중 파일 어셈블리을 만들어야 하는 이유는 다음과 같습니다.  
  
-   다른 언어로 작성된 모듈을 결합할 수 있습니다.  이는 다중 파일 어셈블리를 만드는 가장 일반적인 이유입니다.  
  
-   자주 사용되지 않는 형식은 필요한 경우에만 다운로드되는 모듈에 저장되므로 응용 프로그램 다운로드를 최적화할 수 있습니다.  
  
    > [!NOTE]
    >  Microsoft Internet Explorer에서 `<object>` 태그를 사용하여 다운로드할 응용 프로그램을 만드는 경우, 다중 파일 어셈블리를 만드는 것이 중요합니다.  이 시나리오에서 사용자는 어셈블리 매니페스트만 포함된 코드 모듈과는 별도의 파일을 만듭니다.  Internet Explorer는 어셈블리 매니페스트를 먼저 다운로드한 다음, 작업자 스레드를 만들어 추가로 필요한 모듈이나 어셈블리를 다운로드합니다.  어셈블리 매니페스트가 포함된 파일을 다운로드하는 동안, Internet Explorer는 사용자 입력에 응답하지 않습니다.  어셈블리 매니페스트가 포함된 파일의 크기가 작을수록 Internet Explorer에서 반응하지 않는 시간이 짧아집니다.  
  
-   여러 개발자가 작성한 코드 모듈을 결합할 수 있습니다.  각 개발자는 개별 코드를 하나의 어셈블리로 컴파일할 수 있습니다. 하지만 이 경우, 모든 모듈을 다중 파일 어셈블리로 컴파일한 경우에는 노출되지 않았던 일부 형식이 공개적으로 노출될 수 있습니다.  
  
 어셈블리가 만들어지면 사용자는 어셈블리 매니페스트와 어셈블리를 서명할 수 있습니다. 또한, 이 어셈블리에 강력한 이름을 지정하여 전역 어셈블리 캐시에 저장할 수 있습니다.  
  
## 참고 항목  
 [방법: 다중 파일 어셈블리 빌드](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)